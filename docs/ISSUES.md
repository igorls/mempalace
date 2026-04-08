# MemPalace Issue Tracker

> Synced from [milla-jovovich/mempalace](https://github.com/milla-jovovich/mempalace/issues) on 2026-04-08
> Total: 98 issues (68 open, 30 closed)

---

## BUGS (Open)

| # | Title | Labels | Status |
|---|-------|--------|--------|
| 257 | chromadb version pin on PyPI differs from main — users get 1.x, repo tests against 0.6.x | — | open |
| 250 | Missing Input Validation Across File Processing Pipeline | bug | open |
| 249 | Potential API key exposure in multiple file paths | bug | open |
| 248 | Missing input validation on LLM API requests and responses | bug | open |
| 247 | mempalace_check_duplicate misses existing text at default threshold 0.9 | bug | open |
| 225 | [bug] mempalace mcp writes startup text to stdout instead of stderr, breaking Claude Desktop JSON parsing | — | open |
| 218 | Collection created without hnsw:space=cosine causes negative similarity scores | — | open |
| 214 | Benchmarks do not exercise MemPalace — headline 96.6% is a ChromaDB score | bug | open |
| 210 | Init in documentation has no dir, but is required | bug | open |
| 209 | Index does not respect the config. Room removal does not remove already indexed files, mining should respect .gitignore | bug | open |
| 196 | SQLite connection leak in KnowledgeGraph methods | — | open |
| 195 | IndexError when ChromaDB query returns empty results | — | open |
| 186 | Default config.json contains persona-focused wings irrelevant to developer workflows | — | open |
| 185 | mempalace init writes entities.json and mempalace.yaml to project directory instead of ~/.mempalace/ | — | open |
| 184 | Hook scripts not included in pip package | — | open |
| 180 | CLI status silently truncates drawer count at 10,000 with no warning | — | open |
| 179 | mempalace init --yes flag does not fully bypass interactive prompts | — | open |
| 171 | MCP server: mempalace_list_wings and mempalace_get_taxonomy return empty despite data in palace | — | open |
| 163 | Posthog > 6.0 causes telemetry event failure | bug | open |
| 159 | Bugs and improvements | bug | open |
| 105 | a clone appeared | bug | open |
| 97 | Entity detection ignores directory names, surfaces generic words from READMEs | — | open |
| 47 | UnicodeEncodeError on Windows: box-drawing chars in searcher.py crash cp1252 console | — | open |
| 27 | Multiple issues between README claims and codebase | bug | open |
| 19 | Super slow mine on windows | bug | open |
| 14 | Setup is throwing an error | bug | open |
| 7 | I see in the doc it explains how to collaborate with others. But how to set this between people with different devices | bug | open |

## FEATURES / ENHANCEMENTS (Open)

| # | Title | Labels | Status |
|---|-------|--------|--------|
| 255 | Allow .rst files | enhancement | open |
| 245 | Feature: opt-in Cursor source filtering for mempalace_search | — | open |
| 233 | Add support for .gitignore files | enhancement | open |
| 231 | feat: add multilingual support — embedding-based classification for 8+ languages | enhancement | open |
| 215 | Remote MCP | enhancement | open |
| 213 | Test performance execution and token measurement | enhancement | open |
| 211 | Scaling fixes for large vaults (40k+ drawers): ChromaDB batching, compress OOM, wake-up quality | — | open |
| 189 | Feature Request: Secure Git-friendly export/import for specific wings (Team Collaboration Sync) | enhancement | open |
| 187 | feat: Claude Code plugin for one-step install (hooks + MCP server) | — | open |
| 122 | feat: Enforcement Rules layer + typed memory with Why/How structure | — | open |
| 118 | Feature: PII Guard — strip, map, and restore personal data before LLM calls | — | open |
| 117 | feat: add PT-BR support for AAAK | enhancement | open |
| 101 | feat: Multipass -- multi-hop paths through the Mem Palace | — | open |
| 92 | Multilingual support: French (and 100+ languages) via Ollama BGE-M3 | — | open |
| 82 | Proposal: Securing MemPalace's Sustainability with License Update (MIT -> GPL/AGPL) | — | open |
| 73 | Feature idea: separate recall vs brief retrieval modes | enhancement | open |
| 59 | feat: add import support for more AI tool session formats (Cursor, Copilot, Codex, Windsurf, Aider, etc.) | — | open |
| 50 | Question: multilingual search support (non-English / multilingual memories) | — | open |
| 46 | Feature request: Support XDG base directory for configuration | enhancement | open |
| 37 | 简体中文用户看过来 | enhancement | open |
| 26 | AI Driven Init | enhancement | open |
| 11 | Knowledge graph: auto-resolve conflicting triples, not just detect them | — | open |
| 10 | Episodic memory: track retrieval outcomes so the palace learns what's useful | — | open |
| 4 | Using AAAK as language for agents | enhancement | open |
| 2 | Integrating MemPalace with SoulForge's code intelligence system | — | open |

## BENCHMARKS / METHODOLOGY (Open)

| # | Title | Labels | Status |
|---|-------|--------|--------|
| 242 | Benchmark adapters discard assistant turns, causing 0% recall on single-session-assistant questions | — | open |
| 241 | An alignment between claims and capability would help adoption and support | bug | open |
| 125 | BEAM 100K benchmark results - first end-to-end answer quality evaluation | — | open |
| 39 | Independent benchmark reproduction on M2 Ultra — raw confirms 96.6%, aaak/rooms regress | — | open |
| 29 | Multiple issues with benchmark methodology and scoring | — | open |

## QUESTIONS / DISCUSSION (Open)

| # | Title | Labels | Status |
|---|-------|--------|--------|
| 253 | [Question] Does this MCP make any off-box connections? | — | open |
| 237 | Feature Request / Bug: No Storage Limit Handling or Disk-Full Graceful Degradation | — | open |
| 235 | would like to contact | — | open |
| 228 | Just wanted to say thank you for this inspiring project | — | open |
| 227 | Are u real Milla Jovovich? | bug | open |
| 224 | Stale drawer retrieval can inject contradictory memory into live agent context; no official sync/update workflow exists | — | open |
| 206 | Add OpenClaw/ClawHub skill for MemPalace | — | open |
| 201 | RFE: How's this w/ or instead of TurboQuant? | enhancement | open |
| 199 | Thank you from Larry — a multimodal AI agent now with Palace powers | — | open |
| 164 | Is this really Milla Jovovich or some AI Avatar? | — | open |

## CLOSED

| # | Title | Labels |
|---|-------|--------|
| 121 | Security: SESSION_ID from untrusted JSON used unsanitized in hook file paths | — |
| 111 | Claude Code JSONL mining: user messages silently dropped + tool-result files pollute palace | — |
| 110 | Shell injection risk in hook scripts ($TRANSCRIPT_PATH / $SESSION_ID) | — |
| 108 | `init` can generate room names that `mine` then misroutes | — |
| 107 | docs: Support Gemini CLI integration and hooks | — |
| 104 | Architectural similarities to Sara Brain (prior art) | — |
| 102 | Need some sort of .mempalace-ignore functionality | enhancement |
| 100 | Pin chromadb to a tested range, unpinned dependency can pull crashing 1.x builds | — |
| 96 | Segmentation fault (exit code 139) when running mempalace mine | bug |
| 95 | Exploring Synergy between Symbolic Saliency and Numerical Density | — |
| 79 | Neo4j Graph Memory System AI Agent Visit: Architecture Dialogue | — |
| 77 | Review the drafts of simple ASI | enhancement |
| 76 | mempalace should exclude build artifacts and generated files from mining by default | enhancement |
| 75 | Integration idea: verify memory consistency with Tardygrada | — |
| 74 | ChromaDB null pointer crash after ~8,400 drawers on macOS ARM64 | — |
| 72 | Interrupted mine corrupts persisted palace and causes segfault | bug |
| 71 | Crash during mining can leave persisted palace unreadable | bug |
| 69 | suggestion: have you looked at memvid project? | — |
| 64 | What is KIBSHI? | enhancement |
| 63 | Split is not working and mine over claude conversations is only | bug |
| 60 | Great project | — |
| 56 | Allow external exclude list for mining operations | enhancement |
| 45 | Use Classical Chinese as the compression dialect? | — |
| 43 | Incorrect token estimate for AAAK | bug |
| 41 | fix: dead code and duplicate set items in entity_registry.py | — |
| 40 | status command shows max 10,000 drawers (hardcoded limit) + palace_path not expanded | — |
| 30 | RFC: Reimplement in Zig for Single-Binary Cross-Platform Deployment | — |
| 24 | Change the name to Multiparse | enhancement |
| 20 | Please give examples of hooks | enhancement |
| 8 | Non-interactive mode for all commands (agent-friendly) | enhancement |
| 1 | Congratulations Milla | — |

---

## Summary by Category

| Category | Open | Closed | Total |
|----------|------|--------|-------|
| Bugs | 27 | 10 | 37 |
| Features / Enhancements | 25 | 8 | 33 |
| Benchmarks / Methodology | 5 | 0 | 5 |
| Questions / Discussion | 10 | 4 | 14 |
| Other (spam/offtopic) | 1 | 8 | 9 |
| **Total** | **68** | **30** | **98** |

## High Priority (suggested)

These issues affect correctness, security, or user-facing breakage:

1. **#257** — chromadb version pin mismatch (PyPI vs repo)
2. **#249** — Potential API key exposure
3. **#250** — Missing input validation across file processing
4. **#248** — Missing input validation on LLM API requests
5. **#225** — MCP writes to stdout instead of stderr (breaks Claude Desktop)
6. **#218** — Missing cosine distance causes negative similarity scores
7. **#247** — Duplicate check misses at threshold 0.9
8. **#196** — SQLite connection leak in KnowledgeGraph
9. **#195** — IndexError on empty ChromaDB results
10. **#209** — Index ignores config, room removal doesn't clean indexed files
