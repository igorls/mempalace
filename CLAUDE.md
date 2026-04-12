# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

MemPalace — a local AI memory system that stores conversations and projects in a searchable palace backed by ChromaDB. No API keys required. Two runtime dependencies: `chromadb` and `pyyaml`.

## Commands

```bash
# Install (dev)
pip install -e ".[dev]"

# Run tests (excludes benchmarks/slow/stress by default via pyproject.toml addopts)
python -m pytest tests/ -v --ignore=tests/benchmarks

# Run tests with coverage
python -m pytest tests/ -v --ignore=tests/benchmarks --cov=mempalace --cov-report=term-missing

# Run a single test
python -m pytest tests/test_cli.py::test_cmd_status_default_palace -v

# Run benchmarks only
python -m pytest tests/benchmarks/ -v -m benchmark

# Lint and format
ruff check .
ruff format .

# CI lint check (no changes)
ruff format --check .
```

## CI

GitHub Actions on push/PR to `main`: tests on Linux (3.9, 3.11, 3.13), Windows (3.9), macOS (3.9) + lint (3.11). Coverage threshold: 80% in CI, 85% locally. Tests must pass without network access or API keys.

## Architecture

```
User → CLI (cli.py) / MCP Server (mcp_server.py)
         ↓
    ChromaDB (vector store) + SQLite (knowledge graph)
```

**Palace hierarchy** — three-level data model that drives retrieval:
- **Wing** — person or project
- **Room** — topic within a wing
- **Drawer** — verbatim text chunk (800 chars, 100-char overlap)

**Memory layers** (`layers.py`) — context stack for LLM wake-up:
- L0: Identity (~100 tokens from `~/.mempalace/identity.txt`)
- L1: Essential story (auto-generated, ~500-800 tokens)
- L2: On-demand room recall (filtered by wing/room)
- L3: Deep semantic search (full ChromaDB query)

**Knowledge graph** (`knowledge_graph.py`) — temporal entity-relationship triples in SQLite with `valid_from`/`valid_to` dates for fact invalidation.

### Key modules

| Module | Responsibility |
|--------|---------------|
| `palace.py` | ChromaDB access seam (`get_collection`, `file_already_mined`) |
| `miner.py` | Project file ingestion (scan → detect room → chunk → file) |
| `convo_miner.py` | Conversation transcript ingestion (5 chat formats) |
| `searcher.py` | Semantic search with optional wing/room filtering |
| `mcp_server.py` | 19 MCP tools (read/write) with WAL at `~/.mempalace/wal/` |
| `config.py` | Configuration + input sanitization (`sanitize_name`, `sanitize_content`) |
| `normalize.py` | Chat format detection/conversion (Claude, ChatGPT, Slack, plain text) |
| `dialect.py` | AAAK lossy compression dialect |
| `palace_graph.py` | Room traversal graph, cross-wing tunnels (BFS) |
| `hooks_cli.py` | Auto-save hook system (JSON stdin/stdout protocol) |
| `version.py` | Single source of truth for package version |

### Where to make changes

- **Add MCP tool**: `mcp_server.py` — add handler function + entry in `TOOLS` dict
- **Change search**: `searcher.py`
- **Modify mining**: `miner.py` (project files) or `convo_miner.py` (transcripts)
- **Input validation**: `config.py` — `sanitize_name()` / `sanitize_content()`
- **Add tests**: `tests/test_<module>.py`, fixtures in `tests/conftest.py`

## Conventions

- **Style**: `snake_case` functions/variables, `PascalCase` classes, double quotes
- **Linter**: ruff (E/F/W/C901 rules, line-length 100, `E501` ignored)
- **Commits**: conventional commits (`feat:`, `fix:`, `test:`, `docs:`, `bench:`, `ci:`)
- **Dependencies**: minimize — don't add new deps without discussion
- **Architecture principles**: verbatim first (never summarize user content), local first (no cloud), zero API by default, palace structure matters (wings/rooms drive 34% retrieval improvement)

## Test markers

- `@pytest.mark.benchmark` — scale/performance tests
- `@pytest.mark.slow` — tests > 30 seconds
- `@pytest.mark.stress` — destructive scale tests (100K+ drawers)

All three are excluded by default via `addopts` in `pyproject.toml`.

## Config paths

| Path | Purpose |
|------|---------|
| `~/.mempalace/config.json` | Main configuration |
| `~/.mempalace/palace/` | Default ChromaDB + SQLite storage |
| `~/.mempalace/identity.txt` | L0 identity (plain text) |
| `~/.mempalace/people_map.json` | Entity name canonicalization |
| `~/.mempalace/wal/write_log.jsonl` | MCP write-ahead log |
| `MEMPALACE_PALACE_PATH` env var | Override palace location |
