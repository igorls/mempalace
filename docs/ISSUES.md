# MemPalace Issue Tracker

> Synced from [milla-jovovich/mempalace](https://github.com/milla-jovovich/mempalace/issues) on 2026-04-09
> Total: 92 open issues, 132 open PRs

---

## CRITICAL / SECURITY (Open)

| # | Title | Labels | PR |
|---|-------|--------|-----|
| **397** | **ARM64 segfault mitigation is a no-op — ORT_DISABLE_COREML not a real ONNX RT env var** | bug | — |
| **396** | **OOM crash on large transcript files — split_mega_files.py and normalize.py load entire file** | bug | — |
| **395** | **cmd_repair infinite recursion when palace_path has trailing slash — fills disk** | bug | — |
| **394** | **MCP server hangs when client sends null arguments — unhandled AttributeError** | bug | — |
| 357 | Parallel mining corrupts ChromaDB HNSW index — no warning, silent failure | — | — |
| 344 | HNSW index bloat: link_lists.bin grows to 441GB when mining >10K drawers | — | #346 |
| 339 | Silent `except Exception: pass` in MCP tools hides errors from callers | bug | #371 |
| 333 | System prompt context prepended to queries drops retrieval from 89.8% to 1.0% | — | — |
| 326 | mempalace.tech serving malicious JavaScript — ad injection and redirect chain | bug | — |
| 296 | Invalid command 'mcp' not recognized | bug | #315 |

## BUGS (Open)

| # | Title | Labels | PR |
|---|-------|--------|-----|
| 390 | Chunk size (800) exceeds embedding model token limit (256 tokens / ~512 chars) | — | — |
| 378 | Windows: plugin.json and hook scripts use "python3" — no Windows-compatible hooks | bug | — |
| 377 | Hook scripts call "mempalace hook run" command that doesn't exist in PyPI v3.0.0 | bug | #328 |
| 369 | v3.0.14 not on PyPI - hook command missing | — | — |
| 368 | mempalace plugin install fails | bug | — |
| 363 | Windows: mempalace_search fails with "TextInputSequence must be str" on non-ASCII | — | #205 |
| 359 | json.dumps(response) does not set ensure_ascii=False | bug | #370 |
| 355 | pip package does not include mcp subcommand — Claude Desktop setup fails | — | #340 |
| 347 | Codex hook message counting does not match Codex transcript schema | bug | — |
| 338 | mempalace_list_wings / list_rooms / get_taxonomy silently return empty on large collections | — | #307, #371 |
| 330 | ChatGPT mapping imports can silently ingest the wrong branch | bug | #329 |
| 327 | normalize.py: Claude Code JSONL parser doesn't match `type: "user"` messages | — | — |
| 323 | mempal-stop-hook.sh calls nonexistent `hook` subcommand | — | #325 |
| 303 | Split command fails with all argument formats on Windows 11 | bug | #308 |
| 290 | inconsistent versions between published pip package and claude plugin | bug | — |
| 284 | pip install requires --break-system-packages | bug | — |
| 275 | Windows compatibility gaps in tests and CI | — | #277 |
| 263 | Website results of the quiz don't show the UTF-8 check mark | bug | — |
| 247 | mempalace_check_duplicate misses existing text at default threshold 0.9 | bug | #299 |
| 225 | mempalace mcp writes startup text to stdout instead of stderr, breaks Claude Desktop | — | #261 |
| 218 | Collection created without hnsw:space=cosine causes negative similarity scores | — | #262 |
| 214 | Benchmarks do not exercise MemPalace — headline 96.6% is a ChromaDB score | bug | — |
| 210 | Init in documentation has no dir, but is required | bug | #220 |
| 209 | Index ignores config; room removal doesn't remove indexed files; mining should respect .gitignore | bug | #229 |
| 196 | SQLite connection leak in KnowledgeGraph methods | — | **#198** |
| 195 | IndexError when ChromaDB query returns empty results | — | **#197** |
| 186 | Default config.json contains persona-focused wings irrelevant to developer workflows | — | — |
| 185 | mempalace init writes entities.json and mempalace.yaml to project dir instead of ~/.mempalace/ | — | — |
| 184 | Hook scripts not included in pip package | — | #265 |
| 180 | CLI status silently truncates drawer count at 10,000 | — | #364 |
| 179 | mempalace init --yes flag does not fully bypass interactive prompts | — | — |
| 171 | MCP server: list_wings and get_taxonomy return empty despite data in palace | — | #307 |
| 163 | Posthog > 6.0 causes telemetry event failure | bug | — |
| 159 | Bugs and improvements | bug | #162 |
| 105 | a clone appeared | bug | — |
| 97 | Entity detection ignores directory names, surfaces generic words from READMEs | — | #349 |
| 47 | UnicodeEncodeError on Windows: box-drawing chars crash cp1252 console | — | #205 |
| 27 | Multiple issues between README claims and codebase | bug | — |
| 19 | Super slow mine on windows | bug | #298 |
| 14 | Setup is throwing an error | bug | #173 |

## FEATURES / ENHANCEMENTS (Open)

| # | Title | Labels | PR |
|---|-------|--------|-----|
| 391 | Memory-librarian skill + stuck detector hook for Claude Code | — | — |
| 383 | new issue | enhancement | — |
| 376 | search and kg_query are completely disconnected | — | — |
| 358 | Integration Idea: MemPalace as memory substrate for decentralized agent network | — | — |
| 352 | Add "Era" metadata — temporal axis for the palace | — | — |
| 348 | Entity detector false positives — programming keywords detected as projects | enhancement | #349 |
| 342 | Native OpenCode integration for MemPalace | — | #297 |
| 341 | Request for clarification: current implementation role of closets | enhancement | — |
| 335 | Community Feedback: MemPalace-AGI Dashboard & Integration Project | — | — |
| 332 | feat: soft-archive wings — exclude from search without deleting data | enhancement | #336 |
| 331 | feat: time-decay scoring for search results | enhancement | #337 |
| 318 | feat: smart wing auto-detection when mining conversations | — | #321 |
| 314 | Benchmark Design Issues in LongMemEval | bug | — |
| 301 | Has anyone tried to use it to manage knowledge base? | — | — |
| 295 | Codex JSONL normalization quality and test coverage | — | #334 |
| 292 | feat: per-user isolation for shared remote ChromaDB | enhancement | #294 |
| 283 | Built a vocabulary map to improve NL search | — | — |
| 278 | Add .al extension support and make duplicate detection wing-aware | — | #300 |
| 274 | feat: Native Cursor SQLite Ingestion Support | — | #287 |
| 273 | Domain-scoped collections + local embedding model = better retrieval at scale | — | — |
| 271 | WSL2: GPU detection failure causes slow mempalace init | enhancement | — |
| 269 | Hybrid retrieval direction | — | — |
| 266 | Pluggable storage/backend layer for MemPalace? | — | — |
| 258 | "Singularity Equation" (A* + Stigmergy) for Knowledge Graph Navigation | — | #279 |
| 255 | Allow .rst files | enhancement | #276 |
| 245 | Feature: opt-in Cursor source filtering for mempalace_search | — | #246 |
| 242 | Benchmark adapters discard assistant turns, causing 0% recall | — | — |
| 237 | No Storage Limit Handling or Disk-Full Graceful Degradation | — | — |
| 231 | Add Multilingual Support | enhancement | — |
| 224 | Stale drawer retrieval injects contradictory memory | — | #256 |
| 215 | Remote MCP | enhancement | #294 |
| 213 | Test performance execution and token measurement | enhancement | — |
| 211 | Scaling fixes for large vaults (40k+ drawers) | — | — |
| 206 | Add OpenClaw/ClawHub skill for MemPalace | — | #207 |
| 189 | Secure Git-friendly export/import for specific wings | enhancement | — |
| 187 | feat: Claude Code plugin for one-step install | — | — |
| 122 | feat: Enforcement Rules layer + typed memory with Why/How structure | — | — |
| 118 | Feature: PII Guard | — | #182 |
| 117 | feat: add PT-BR support for AAAK | enhancement | — |
| 101 | feat: Multipass — multi-hop paths through the Mem Palace | — | — |
| 92 | Multilingual support: French (and 100+ languages) via Ollama BGE-M3 | — | — |
| 73 | Feature: separate recall vs brief retrieval modes | enhancement | #174 |
| 59 | feat: add import support for more AI tool session formats | — | #172, #169, #204 |
| 50 | Question: multilingual search support | — | — |
| 46 | Support XDG base directory for configuration | enhancement | — |
| 37 | 简体中文用户看过来 | enhancement | — |
| 11 | Knowledge graph: auto-resolve conflicting triples | — | #178 |
| 10 | Episodic memory: track retrieval outcomes | — | — |

## BENCHMARKS / METHODOLOGY (Open)

| # | Title | Labels |
|---|-------|--------|
| 367 | Benchmark methodology review + complementary approach from agentmemory | — |
| 242 | Benchmark adapters discard assistant turns, causing 0% recall on single-session-assistant questions | — |
| 214 | Benchmarks do not exercise MemPalace — headline 96.6% is a ChromaDB score | bug |
| 125 | BEAM 100K benchmark results - first end-to-end answer quality evaluation | — |
| 39 | Independent benchmark reproduction on M2 Ultra — raw confirms 96.6%, aaak/rooms regress | — |

## QUESTIONS / DISCUSSION (Open)

| # | Title | Labels |
|---|-------|--------|
| 386 | Why is this starting at v3? | — |
| 366 | [SECURITY] Missing T-Virus containment protocols / Red Queen oversight | — |
| 362 | How does the vector DB work when storing only raw text | — |
| 301 | Has anyone tried to use it to manage knowledge base? | — |
| 237 | No Storage Limit Handling or Disk-Full Graceful Degradation | — |
| 235 | would like to contact | — |
| 228 | Just wanted to say thank you for this inspiring project | — |
| 227 | Are u real Milla Jovovich? | bug |
| 199 | Thank you from Larry — a multimodal AI agent now with Palace powers | — |
| 164 | Is this really Milla Jovovich or some AI Avatar? | — |

## CLOSED (recent)

| # | Title | Labels |
|---|-------|--------|
| 375 | Cursor MCP integration failed | bug |
| 374 | How does MemPalace fit in Entertainment AI Chatbots? | — |
| 345 | Bug: Codex hook message counting does not match Codex transcript schema | bug |
| 312 | Related project: SophionMem — multi-agent encryption complement | — |
| 267 | Malicious entities on website www.mempalace.tech | — |
| 257 | chromadb version pin on PyPI differs from main — users get 1.x, repo tests against 0.6.x | — |
| 253 | Does this MCP make any off-box connections? | — |
| 250 | Missing Input Validation Across File Processing Pipeline | bug |
| 249 | Potential API key exposure in multiple file paths | bug |
| 248 | Missing input validation on LLM API requests and responses | bug |
| 241 | An alignment between claims and capability would help adoption and support | bug |
| 233 | Add support for .gitignore files | enhancement |
| 228 | Just wanted to say thank you | — |
| 227 | Are u real Milla Jovovich? | bug |
| 209 | Index ignores config, mining should respect .gitignore | bug |
| 201 | How's this w/ or instead of TurboQuant? | enhancement |
| 187 | Claude Code plugin for one-step install | — |
| 186 | Default config.json contains persona-focused wings | — |
| 180 | CLI status silently truncates drawer count at 10,000 | — |
| 179 | mempalace init --yes flag does not fully bypass interactive prompts | — |
| 164 | Is this really Milla Jovovich? | — |
| 163 | Posthog > 6.0 causes telemetry event failure | bug |
| 121 | Security: SESSION_ID from untrusted JSON used unsanitized in hook file paths | — |
| 111 | Claude Code JSONL mining: user messages silently dropped | — |
| 110 | Shell injection risk in hook scripts ($TRANSCRIPT_PATH / $SESSION_ID) | — |
| 108 | `init` can generate room names that `mine` then misroutes | — |
| 107 | docs: Support Gemini CLI integration and hooks | — |
| 105 | a clone appeared | bug |
| 104 | Architectural similarities to Sara Brain (prior art) | — |
| 102 | Need some sort of .mempalace-ignore functionality | enhancement |
| 100 | Pin chromadb to a tested range, unpinned dependency can pull crashing 1.x builds | — |
| 96 | Segmentation fault (exit code 139) when running mempalace mine | bug |
| 82 | Proposal: License Update (MIT -> GPL/AGPL) | — |
| 76 | mempalace should exclude build artifacts and generated files from mining | enhancement |
| 74 | ChromaDB null pointer crash after ~8,400 drawers on macOS ARM64 | — |
| 72 | Interrupted mine corrupts persisted palace and causes segfault | bug |
| 71 | Crash during mining can leave persisted palace unreadable | bug |

---

## Audit Findings vs Issue Coverage (2026-04-09)

Cross-reference of validated findings from `docs/r1.md` and `docs/r2.md` against existing issues and open PRs.

### Covered by existing issues/PRs

| Finding | Issue | PR | Status |
|---------|-------|-----|--------|
| SQLite connection leaks in `knowledge_graph.py` | #196 | **#198** | PR open |
| Unpinned `chromadb>=0.5.0,<0.7` | #100 (closed) | **#365** | PR open |
| Path traversal / shell injection in hooks | #110 (closed) | **#320** | PR open |
| ChatGPT parser follows first child only (data loss) | #330 | **#329** | PR open |
| Thread-unsafe ChromaDB client / ARM64 segfault | #74 (closed) | — | No PR (symptom tracked but root cause unfixed) |
| MCP error hardening (partial coverage of null args) | — | **#181** | PR open (read-only mode, not null-arg fix specifically) |
| Security hardening (partial coverage of delete auth) | — | **#175** | PR open (auth/encryption, broad scope) |

### Filed as new issues (2026-04-09)

| Finding | Severity | Issue |
|---------|----------|-------|
| MCP hangs on `null` arguments | CRITICAL | [#394](https://github.com/milla-jovovich/mempalace/issues/394) |
| `cmd_repair` infinite recursion on trailing-slash paths | HIGH | [#395](https://github.com/milla-jovovich/mempalace/issues/395) |
| OOM on large transcript files in `split_mega_files.py` and `normalize.py` | HIGH | [#396](https://github.com/milla-jovovich/mempalace/issues/396) |
| `ORT_DISABLE_COREML` ARM64 mitigation is a no-op | HIGH | [#397](https://github.com/milla-jovovich/mempalace/issues/397) |

### Low-priority findings (no issue needed)

| Finding | Severity | Reason |
|---------|----------|--------|
| Unauthenticated `delete_drawer` MCP tool | MEDIUM | Local-only tool; partially addressed by PR #175 (security hardening) and PR #181 (read-only mode) |
| Precompact hook unsanitized SESSION_ID | MEDIUM | Only used in logging; partially addressed by PR #320 |
| `--palace` path not sandboxed | MEDIUM | Local CLI tool, user controls their own paths |
| Unexpanded `~` in `hooks_cli.py` MEMPAL_DIR | MEDIUM | Niche env var usage |
| `_entity_id` collision ("O'Neil" vs "oneil") | LOW | Edge case |
| Dual env var names (MEMPALACE vs MEMPAL) | LOW | Convenience, not a bug |
| Temporal invalidation allows contradictions | LOW | No user reports |

---

## Summary by Category

| Category | Open | Closed | Total |
|----------|------|--------|-------|
| Bugs / Stability | 40 | 17 | 57 |
| Features / Enhancements | 37 | 8 | 45 |
| Benchmarks / Methodology | 5 | 2 | 7 |
| Questions / Discussion | 10 | 6 | 16 |
| **Total** | **92** | **33** | **125** |

## Open PRs Addressing Audit Findings

| PR | Branch | Addresses |
|----|--------|-----------|
| #198 | `fix/kg-sqlite-connection-leak` | SQLite connection leaks (r1 HIGH, r2 CRITICAL) |
| #365 | `fix/chromadb-version-pin` | ChromaDB version pinning (r1 CRITICAL) |
| #320 | `fix/shell-injection` | Hook shell injection (r1 HIGH) |
| #329 | `fix/chatgpt-mapping-active-branch` | ChatGPT parser data loss (r1/r2 MEDIUM) |
| #181 | `fix/mcp-error-hardening` | MCP error handling (r2 CRITICAL — partial) |
| #175 | `feat/security-hardening` | Auth/encryption hardening (r1 CRITICAL — partial) |
| #346 | `fix/hnsw-index-bloat` | HNSW index corruption (related to concurrency issues) |
| #371 | `fix/issue-339-338-silent-exceptions-pagination` | Silent exceptions + pagination |
