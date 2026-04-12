# MemPalace Issue Tracker

> Synced from [MemPalace/mempalace](https://github.com/MemPalace/mempalace/issues) on 2026-04-12
> Total: **172 open issues**, **115 open PRs**

## Sync Delta (2026-04-10 → 2026-04-12)

| Metric | Previous | Current | Change |
|---|---|---|---|
| Open issues | 155 | 172 | **+17** |
| Open PRs | 192 | 115 | **-77** |
| Merged PRs (rolling 2wk) | — | 30 | — |
| Closed issues (rolling 2wk) | 75 | 53 | -22 |

**Notable:** Repo org renamed from `milla-jovovich` to `MemPalace`. Significant merge wave — 30 PRs merged since 2026-03-29, including critical fixes for mtime dedup (#610), HNSW bloat (#544), MCP ping (#600), security hardening (#647), and silent exceptions (#371). VitePress docs site (#439) merged. 55 PRs closed unmerged (duplicates, superseded). New issues continue at ~20/day, many from bot/AI-generated PRs (#615, #680).

Previously-tracked items closed since 2026-04-10: #525, #534, #535, #536, #524, #514, #511, #506, #397, #396, #395, #339, #338, #333, #404, #528, #646, #602, #672, #671.

---

## CRITICAL / SECURITY (Open)

Hand-picked by severity (crash, data-loss, corruption, security) regardless of label state.

| # | Title | Labels | PR |
|---|---|---|---|
| **688** | `list_wings` returns empty when collection has >100K records (SQLite variable limit) | — | — |
| **686** | v3.1.0 incompatible with chromadb 1.x — dependency pinned to <0.7 | — | #581 |
| **654** | `convo_miner` re-processes files every run + `drawers_added` counter always 0 | — | — |
| **619** | `mempalace repair` fails with `InvalidCollectionException` on large palace | — | #632 |
| **608** | `mempalace_search` returns stale results after mid-session CLI mine — cached HNSW client not invalidated | — | #620, #663 |
| **585** | Corrupt `chroma.sqlite3` header leaves palace unrecoverable; repair can't salvage HNSW data | bug | — |
| **538** | MCP server stdio transport: `add_drawer` and `kg_add` write to WAL but not to ChromaDB/SQLite | bug | — |
| **526** | MCP tools `diary_write` and `kg_add` return internal error -32000 | bug | — |
| **521** | hnswlib `updatePoint` race on modified-file re-mine: EXC_BAD_ACCESS (macOS ARM64, Python 3.13) | — | #523 |
| **503** | MCP server fails with surrogate error on Windows when writing CJK content | — | #512, #631 |
| **487** | `chromadb<0.7` pin breaks MCP server on Python 3.14 | — | #581, #302 |
| **469** | Palace data gone after upgrade to v3.1.0 | bug | #502 (merged) |
| **445** | v3.1.0 ChromaDB pin breaks existing palace created with Chroma 1.x | — | #581, #426 |
| **444** | Global palace is a single point of failure — one corrupted project destroys all data | — | #446 |
| **357** | Parallel mining corrupts ChromaDB HNSW index — no warning, silent failure | — | — |
| **344** | HNSW index bloat: `link_lists.bin` grows to 441GB when mining >10K drawers | — | #346 |
| **326** | mempalace.tech serving malicious JavaScript — ad injection and redirect chain | bug | — |

### Resolved since last sync (moved to CLOSED)

| # | Title | Fix |
|---|---|---|
| ~~525~~ | HNSW `link_lists.bin` grows to terabytes | #544 (merged 2026-04-10) |
| ~~479~~ | Duplicate `_client_cache`/`_collection_cache` declarations | #449 (merged 2026-04-12) |
| ~~475~~ | Float mtime comparison breaks file deduplication | #610 (merged 2026-04-11) |
| ~~397~~ | ARM64 segfault mitigation is a no-op | #653 (merged 2026-04-12) |
| ~~396~~ | OOM crash on large transcript files | #399 (merged 2026-04-09) |
| ~~395~~ | `cmd_repair` infinite recursion on trailing-slash paths | #399 (merged 2026-04-09) |
| ~~339~~ | Silent `except Exception: pass` in MCP tools | #371 (merged 2026-04-11) |
| ~~338~~ | `list_wings`/`list_rooms`/`get_taxonomy` return empty on large collections | #371 (merged 2026-04-11) |
| ~~333~~ | System prompt context drops retrieval from 89.8% to 1.0% | #385 (merged 2026-04-11) |

---

## BUGS — Labeled `bug` (Open, 27)

| # | Title | Author | Filed |
|---|---|---|---|
| 649 | Hidden network dependency violates offline-first guarantees | — | 2026-04-11 |
| 618 | POSSIBLE SCAM REPO | — | 2026-04-11 |
| 603 | `mempalace status` count less | — | 2026-04-11 |
| 599 | There are too few rooms | — | 2026-04-11 |
| 586 | `mempalace mine --dry-run` crashes with TypeError on files with room=None | — | 2026-04-10 |
| 585 | Corrupt `chroma.sqlite3` header leaves palace unrecoverable | — | 2026-04-10 |
| 584 | MCP server does not implement `ping` method — breaks AnythingLLM v1.12.0 | — | 2026-04-10 |
| 561 | Can't install from pip on macOS Sequoia 15.7.5 | — | 2026-04-10 |
| 545 | Hook scripts should use venv python | — | 2026-04-10 |
| 541 | Contributing page mentions discussions | nanoscopic | 2026-04-10 |
| 538 | MCP server stdio transport: `add_drawer` and `kg_add` write to WAL but not to ChromaDB/SQLite | duha887b | 2026-04-10 |
| 531 | README chromadb version differs from actual | nanoscopic | 2026-04-10 |
| 526 | MCP tools `diary_write` and `kg_add` return internal error -32000 | bmaltais | 2026-04-10 |
| 469 | Palace data gone after upgrade to v3.1.0 | R0uter | 2026-04-10 |
| 412 | Discord link impossible to verify | CodeAKrome | 2026-04-09 |
| 411 | `mine` step not clear, unrelated results found | jchronowski | 2026-04-09 |
| 378 | Windows: `plugin.json` and hook scripts use `python3` — no Windows-compatible hooks | JefffromNJ | 2026-04-09 |
| 377 | Hook scripts call `mempalace hook run` command that doesn't exist in PyPI v3.0.0 | JefffromNJ | 2026-04-09 |
| 368 | `mempalace plugin install` fails | jerrythomas | 2026-04-09 |
| 359 | `json.dumps(response)` does not set `ensure_ascii=False` | janzwang666555 | 2026-04-09 |
| 330 | ChatGPT mapping imports can silently ingest the wrong branch | GaosCode | 2026-04-09 |
| 326 | mempalace.tech serving malicious JavaScript — ad injection and redirect chain | nhumphreys | 2026-04-09 |
| 303 | Split command fails with all argument formats on Windows 11 | JefffromNJ | 2026-04-08 |
| 284 | `pip install` requires `--break-system-packages` | flundstrom2 | 2026-04-08 |
| 263 | Website quiz results don't show UTF-8 check mark | cm-tramcase | 2026-04-08 |
| 247 | `mempalace_check_duplicate` misses existing text at default threshold 0.9 | lzhuojun251 | 2026-04-08 |
| 210 | Init in documentation has no dir, but it is required | scottp | 2026-04-08 |

### Labeled `bug` closed since last sync

| # | Title | Closed |
|---|---|---|
| ~~646~~ | `_try_claude_ai_json` parser produces 0 drawers on claude.ai export | 2026-04-12 |
| ~~524~~ | "Remove Baldfaced Lies Please" (README/claims discrepancy) | 2026-04-11 |
| ~~404~~ | `detect_room` called with empty content in `miner.py` | 2026-04-11 |
| ~~347~~ | Codex hook message counting does not match Codex transcript schema | 2026-04-10 |
| ~~339~~ | Silent `except Exception: pass` in MCP tools hides errors | 2026-04-11 |

---

## BUGS — Unlabeled but clearly bugs (Open)

These are filed without the `bug` label but are unambiguous defects. Upstream labeling has fallen behind.

| # | Title | Filed |
|---|---|---|
| 688 | `list_wings` returns empty when collection has >100K records (SQLite variable limit) | 2026-04-12 |
| 686 | v3.1.0 incompatible with chromadb 1.x — dependency pinned to <0.7 | 2026-04-12 |
| 677 | `conversations.json` from Claude.ai data export not parsed — mined as single drawer | 2026-04-12 |
| 655 | KG edge duplication in Knowledge Graph | 2026-04-12 |
| 654 | `convo_miner` re-processes files every run + `drawers_added` counter always 0 | 2026-04-12 |
| 650 | Windows setup failures: unversioned `python3` calls break ChromaDB, MCP, and hooks | 2026-04-11 |
| 619 | `mempalace repair` fails with `InvalidCollectionException` on large palace | 2026-04-11 |
| 608 | `mempalace_search` returns stale results after mid-session CLI mine | 2026-04-11 |
| 590 | Claude Code JSONL mining silently drops all tool output (49% content loss) | 2026-04-11 |
| 554 | Stop hook MCP tool calls clutter terminal every 15 messages | 2026-04-10 |
| 549 | Save hook counts `tool_result` messages as human messages, inflating exchange count | 2026-04-10 |
| 521 | hnswlib `updatePoint` race on re-mine: EXC_BAD_ACCESS (macOS ARM64, Python 3.13) | 2026-04-10 |
| 503 | MCP server fails with surrogate error on Windows when writing CJK content | 2026-04-10 |
| 487 | `chromadb<0.7` pin breaks MCP server on Python 3.14 | 2026-04-10 |
| 479 | Duplicate `_client_cache`/`_collection_cache` declarations reset state in `mcp_server.py` | 2026-04-10 |
| 478 | Status/taxonomy MCP tools silently truncate at 10,000 drawers | 2026-04-10 |
| 477 | MCP `tool_search` has no upper bound on `limit` — potential memory exhaustion | 2026-04-10 |
| 476 | Entity detector flags common code terms as projects (Handler, Node, One, Service) | 2026-04-10 |
| 475 | Float mtime comparison breaks file deduplication — every file re-mined on each run | 2026-04-10 |
| 458 | ChromaDB 0.6.3 telemetry spam on every operation | 2026-04-10 |
| 455 | KG object field too restrictive: `sanitize_name` rejects commas and common punctuation | 2026-04-09 |
| 445 | v3.1.0 ChromaDB pin breaks existing palace created with Chroma 1.x | 2026-04-09 |
| 444 | Global palace is a single point of failure — one corrupted project destroys all data | 2026-04-09 |
| 408 | Plugin assumes `python3 -m mempalace` — breaks on modern Linux (PEP 668) and with uv/pipx | 2026-04-09 |
| 398 | Stop hook fails: `hook` is not a valid CLI subcommand | 2026-04-09 |
| 390 | Chunk size (800) exceeds embedding model token limit (256 tokens / ~512 chars) | 2026-04-09 |
| 369 | v3.0.14 not on PyPI — hook command missing | 2026-04-09 |
| 363 | Windows: `mempalace_search` fails with "TextInputSequence must be str" on non-ASCII | 2026-04-09 |
| 357 | Parallel mining corrupts ChromaDB HNSW index — no warning, silent failure | 2026-04-09 |
| 355 | pip package does not include `mcp` subcommand — Claude Desktop setup fails | 2026-04-09 |
| 344 | HNSW index bloat: `link_lists.bin` grows to 441GB | 2026-04-09 |
| 327 | `normalize.py`: Claude Code JSONL parser doesn't match `type: "user"` messages | 2026-04-09 |
| 323 | `mempal-stop-hook.sh` calls nonexistent `hook` subcommand | 2026-04-09 |
| 295 | Codex JSONL normalization quality and test coverage | 2026-04-08 |
| 275 | Windows compatibility gaps in tests and CI | 2026-04-08 |
| 225 | `mempalace mcp` writes startup text to stdout instead of stderr | 2026-04-08 |
| 218 | Collection created without `hnsw:space=cosine` causes negative similarity scores | 2026-04-08 |
| 196 | SQLite connection leak in `KnowledgeGraph` methods | 2026-04-08 |
| 195 | `IndexError` when ChromaDB query returns empty results | 2026-04-08 |
| 185 | `mempalace init` writes `entities.json` + `mempalace.yaml` to project dir instead of `~/.mempalace/` | 2026-04-08 |
| 184 | Hook scripts not included in pip package | 2026-04-08 |
| 171 | MCP server: `list_wings` and `get_taxonomy` return empty despite data in palace | 2026-04-07 |
| 97 | Entity detection ignores directory names, surfaces generic words from READMEs | 2026-04-07 |

---

## FEATURES / ENHANCEMENTS — Labeled (Open, 30)

| # | Title | Filed |
|---|---|---|
| 669 | [RFC] TiDB Cloud / TiDB Zero as optional backend | 2026-04-12 |
| 652 | Local "Claude Code" install | 2026-04-12 |
| 648 | Documentation site? | 2026-04-11 |
| 639 | Stop Hook utility for automated Claude Code conversation mining | 2026-04-11 |
| 637 | Unicode / diacritics rejected in `sanitize_name()` for KG + MCP writes | 2026-04-11 |
| 595 | [RFC] Synapse Advanced Retrieval — MMR, Pinned Memory, Query Expansion, Supersede, Consolidation | 2026-04-11 |
| 587 | Default-exclude runtime-state files + per-file drawer cap | 2026-04-10 |
| 565 | Cognition Engine — REM cycle, semantic wormholes, topology & ambient RAG | 2026-04-10 |
| 557 | Support `init` with empty palace | 2026-04-10 |
| 537 | [RFC] `scoring_mode`: weighted-sum model for RetrievalProfile | 2026-04-10 |
| 533 | Centralized Skill Management (Agentic Skills Library) | 2026-04-10 |
| 498 | [SPEC] RLM Context Handle Protocol + LCM Heat Scoring | 2026-04-10 |
| 496 | MemPalace Lite — zero-inference fallback mode | 2026-04-10 |
| 495 | Claude desktop session integration via browser-tab-as-proxy | 2026-04-10 |
| 494 | "Silent Mode" / background processing for the Stop hook | 2026-04-10 |
| 489 | [RFC] Synapse Phase 1-2 — biologically-inspired scoring layer + co-retrieval | 2026-04-10 |
| 474 | TLDR | 2026-04-10 |
| 420 | MemPalace as hoarder cleanup! | 2026-04-09 |
| 401 | Octocode — MemPalace security hardening | 2026-04-09 |
| 383 | new issue | 2026-04-09 |
| 348 | Entity detector false positives — programming keywords detected as projects | 2026-04-09 |
| 341 | Clarification: current implementation role of closets | 2026-04-09 |
| 332 | Soft-archive wings — exclude from search without deleting data | 2026-04-09 |
| 331 | Time-decay scoring for search results | 2026-04-09 |
| 292 | Per-user isolation for shared remote ChromaDB | 2026-04-08 |
| 271 | WSL2: GPU detection failure causes slow `mempalace init` (CPU fallback) | 2026-04-08 |
| 255 | Allow `.rst` files | 2026-04-08 |
| 231 | Add multilingual support | 2026-04-08 |
| 215 | Remote MCP | 2026-04-08 |
| 213 | Test performance execution and token measurement | 2026-04-08 |

---

## FEATURES / ENHANCEMENTS — Unlabeled (notable, Open)

Selected from unlabeled open issues. These are framed as features but lack the `enhancement` label.

| # | Title | Filed |
|---|---|---|
| 645 | Add `--refresh` flag to re-mine files whose content has changed | 2026-04-11 |
| 636 | Dumb orchestrator POC — evolving agents via self-written plugins | 2026-04-11 |
| 634 | MCP tool to archive raw conversation excerpts | 2026-04-11 |
| 622 | Stop hook auto-save conflicts with Claude Code's built-in auto-memory | 2026-04-11 |
| 516 | Improve Chinese semantic search quality | 2026-04-10 |
| 515 | GPU-accelerated embeddings via optional sentence-transformers | 2026-04-10 |
| 504 | Add lock/kill-switch guidance for autosave and MCP hook wrappers | 2026-04-10 |
| 467 | Add `SessionStart` hook to load memory protocol on wake-up | 2026-04-10 |
| 466 | Make AAAK opt-in (not default) in `diary_write` and save flows | 2026-04-10 |
| 465 | Include `created_at` timestamp in search results | 2026-04-10 |
| 464 | Automatic deduplication on `add_drawer` | 2026-04-10 |
| 463 | Add date/time filtering to `mempalace_search` | 2026-04-10 |
| 462 | Add `mempalace setup-hooks` command for one-step hook installation | 2026-04-10 |
| 452 | Cross-device sync — export/import palace for multi-PC workflows | 2026-04-09 |
| 448 | Add backup command + auto-backup before mine | 2026-04-09 |
| 430 | Hybrid search to replace hand-tuned boosts in hybrid_v4 | 2026-04-09 |
| 422 | [RFC] AAAK Static Dictionary, Positional Schema, and The Fifth Element | 2026-04-09 |
| 421 | Rust-accelerated embedding + search backend | 2026-04-09 |
| 391 | Memory-librarian skill + stuck-detector hook for Claude Code | 2026-04-09 |
| 376 | `search` and `kg_query` are completely disconnected | 2026-04-09 |
| 358 | MemPalace as memory substrate for decentralized agent network | 2026-04-09 |
| 352 | Add "Era" metadata — temporal axis for the palace | 2026-04-09 |
| 342 | Native OpenCode integration for MemPalace | 2026-04-09 |
| 318 | Smart wing auto-detection when mining conversations | 2026-04-09 |
| 283 | Vocabulary map to improve NL search | 2026-04-08 |
| 278 | `.al` extension support + wing-aware duplicate detection | 2026-04-08 |
| 274 | Native Cursor SQLite ingestion support | 2026-04-08 |
| 273 | Domain-scoped collections + local embedding model for retrieval at scale | 2026-04-08 |
| 269 | Hybrid retrieval direction | 2026-04-08 |
| 266 | Pluggable storage/backend layer | 2026-04-08 |
| 258 | "Singularity Equation" (A* + Stigmergy) for knowledge graph navigation | 2026-04-08 |
| 245 | Opt-in Cursor source filtering for `mempalace_search` | 2026-04-08 |
| 242 | Benchmark adapters discard assistant turns, causing 0% recall | 2026-04-08 |
| 237 | No storage-limit handling or disk-full graceful degradation | 2026-04-08 |
| 224 | Stale drawer retrieval injects contradictory memory | 2026-04-08 |
| 211 | Scaling fixes for large vaults (40k+ drawers) | 2026-04-08 |
| 189 | Secure Git-friendly export/import for specific wings (team sync) | 2026-04-08 |
| 122 | Enforcement Rules layer + typed memory with Why/How structure | 2026-04-07 |
| 118 | PII Guard | 2026-04-07 |
| 117 | PT-BR support for AAAK | 2026-04-07 |
| 101 | Multipass — multi-hop paths through the Mem Palace | 2026-04-07 |
| 92 | Multilingual support: French (100+ languages) via Ollama BGE-M3 | 2026-04-07 |
| 73 | Separate recall vs brief retrieval modes | 2026-04-07 |
| 59 | Import support for more AI tool session formats | 2026-04-07 |
| 46 | Support XDG base directory for configuration | 2026-04-07 |
| 37 | 简体中文用户看过来 (Simplified Chinese users) | 2026-04-07 |
| 11 | Knowledge graph: auto-resolve conflicting triples | 2026-04-07 |
| 10 | Episodic memory: track retrieval outcomes | 2026-04-07 |

---

## QUESTIONS / DISCUSSION / THANKS / LOW-SIGNAL (Open)

~20 low-actionable items. Highlights:

| # | Title |
|---|---|
| 680 | Community guidelines: no promotional content in PR reviews |
| 615 | AI bots are filling the repo with noise |
| 606 | Showcase: Truth Palace of Atlantis — autonomous discovery visualization |
| 583 | Docs: MCP client compatibility notes (uvx vs direct Python path) |
| 552 | Example: complete MemPalace setup + structured usage pattern |
| 532 | Architecture that makes harm structurally impossible — not by policy |
| 485 | A Large Thank You |
| 447 | Consider listing in awesome-ai-plugins |
| 437 | Thank you |
| 418 | Works with LM Studio as an MCP client — suggest adding to docs |
| 386 | Why is this starting at v3? |
| 367 | Benchmark methodology review + complementary approach |
| 366 | [SECURITY] Missing T-Virus containment protocols (satirical) |
| 362 | How does the vector DB work when storing only raw text |
| 335 | Community Feedback Request: MemPalace-AGI Dashboard |
| 301 | Has anyone tried to use it to manage knowledge base? |
| 125 | BEAM 100K benchmark results |
| 50 | Multilingual search support question |
| 39 | Independent benchmark reproduction on M2 Ultra |

---

## CLOSED (recent 2 weeks, top by number)

| # | Title | Labels | Closed |
|---|---|---|---|
| 672 | `init --yes` flag doesn't bypass interactive prompt | — | 2026-04-12 |
| 671 | Status command hides wings at scale (hardcoded limit=10000) | — | 2026-04-12 |
| 658 | DUPLICATE (Please Ignore) | — | 2026-04-12 |
| 646 | `_try_claude_ai_json` parser produces 0 drawers on claude.ai export | bug | 2026-04-12 |
| 624 | Inner Sanctum — Immersive Binaural Journey App | — | 2026-04-11 |
| 602 | `mine --mode convos` silently skips claude.ai exports | — | 2026-04-11 |
| 536 | `--extract general` dumps bold content into `emotional` room | — | 2026-04-11 |
| 535 | `UnicodeEncodeError` on Windows cp1251/cp1252 | — | 2026-04-11 |
| 534 | `SKILL.md` uses nonexistent `mempalace --version`; init omits `--yes` | — | 2026-04-11 |
| 528 | 谢谢 (thanks) | — | 2026-04-11 |
| 525 | HNSW `link_lists.bin` grows to terabytes | — | 2026-04-10 |
| 524 | Remove Baldfaced Lies Please | bug | 2026-04-11 |
| 514 | Feedback from production use: the weight of memory itself | — | 2026-04-11 |
| 511 | Observation: LLM sessions lasting longer since starting MemPalace | — | 2026-04-11 |
| 506 | Is `mempalace.tech` a hacked website? | — | 2026-04-11 |
| 472 | Null (no content) | — | 2026-04-10 |
| 460 | Hook scripts missing from pip package | — | 2026-04-10 |
| 457 | 3.1.0 upgrade silently breaks MCP servers (ChromaDB downgrade) | — | 2026-04-10 |
| 443 | Staff Engineer Review: Postgres/Prisma Railway Wiring Plan | — | 2026-04-09 |
| 441 | [RFC] Synapse: biologically-inspired memory scoring layer | enhancement | 2026-04-10 |
| 407 | Discord invite invalid | — | 2026-04-09 |
| 404 | `detect_room` called with empty content | bug | 2026-04-11 |
| 397 | ARM64 segfault mitigation is a no-op | — | 2026-04-12 |
| 396 | OOM crash on large transcript files | — | 2026-04-11 |
| 395 | `cmd_repair` infinite recursion on trailing-slash | — | 2026-04-11 |
| 394 | MCP server hangs on null arguments | — | 2026-04-09 |
| 375 | Cursor MCP integration failed | bug | 2026-04-10 |
| 374 | How does MemPalace fit in Entertainment AI Chatbots? | — | 2026-04-09 |
| 347 | Codex hook message counting mismatch | bug | 2026-04-10 |
| 345 | Codex hook message counting (dup of #347) | bug | 2026-04-09 |
| 339 | Silent `except Exception: pass` in MCP tools | bug | 2026-04-11 |
| 338 | `list_wings`/`list_rooms`/`get_taxonomy` return empty on large collections | — | 2026-04-11 |
| 333 | System prompt context drops retrieval to 1.0% | — | 2026-04-11 |
| 314 | Benchmark Design Issues in LongMemEval | bug | 2026-04-09 |
| 312 | Related project: SophionMem | — | 2026-04-09 |
| 296 | Invalid command `mcp` not recognized | bug | 2026-04-09 |
| 290 | Inconsistent versions between pip and Claude plugin | bug | 2026-04-09 |
| 267 | Malicious entities on mempalace.tech | — | 2026-04-08 |
| 257 | chromadb version pin on PyPI differs from main | — | 2026-04-09 |
| 253 | Does this MCP make any off-box connections? | — | 2026-04-09 |
| 250 | Missing input validation across file processing pipeline | bug | 2026-04-09 |
| 249 | Potential API key exposure in multiple file paths | bug | 2026-04-08 |
| 248 | Missing input validation on LLM API requests/responses | bug | 2026-04-08 |
| 241 | Alignment between claims and capability | bug | 2026-04-09 |
| 233 | Add support for `.gitignore` files | enhancement | 2026-04-09 |
| 228 | Just wanted to say thank you | — | 2026-04-08 |
| 227 | Are u real Milla Jovovich? | bug | 2026-04-08 |
| 214 | Benchmarks do not exercise MemPalace | bug | 2026-04-09 |
| 209 | Index does not respect config | bug | 2026-04-09 |
| 206 | Add OpenClaw/ClawHub skill | — | 2026-04-10 |

---

## Audit Findings vs Issue Coverage (2026-04-12 update)

Cross-reference of validated findings from `docs/r1.md` and `docs/r2.md` against existing issues and open PRs.

### Covered by existing issues/PRs

| Finding | Issue | PR | Status |
|---|---|---|---|
| SQLite connection leaks in `knowledge_graph.py` | #196 | **#450** (merged) | **FIXED** — test fixtures close connections |
| Path traversal / shell injection in hooks | #110 (closed) | **#387** (merged) | **FIXED** — security hardening landed |
| ChatGPT parser follows first child only (data loss) | #330 | **#329** | PR open |
| Thread-unsafe ChromaDB client / ARM64 segfault | #521 | **#523** | PR open |
| MCP error hardening (partial coverage) | #394 (closed) | **#181** | PR open; null-args fixed by #647 (merged) |
| Security hardening (auth, input validation) | — | **#647** (merged) | **FIXED** — input validation, arg whitelisting, concurrency |
| Silent exceptions in MCP tools | #339 (closed) | **#371** (merged) | **FIXED** |
| System prompt contamination in queries | #333 (closed) | **#385** (merged) | **FIXED** |
| Float mtime dedup regression | #475 | **#610** (merged) | **FIXED** — epsilon comparison |
| HNSW bloat from duplicate add() | #525 (closed) | **#544** (merged) | **FIXED** |
| Duplicate cache declarations in mcp_server.py | #479 | **#449** (merged) | **FIXED** |
| ARM64 no-op env var | #397 (closed) | **#653** (merged) | **FIXED** |

### Remaining critical findings (still open)

| Finding | Severity | Issue | PR |
|---|---|---|---|
| MCP stdio transport drops writes (WAL only) | CRITICAL | #538 | — |
| hnswlib `updatePoint` race on re-mine | CRITICAL | #521 | #523 |
| Corrupt chroma.sqlite3 unrecoverable | CRITICAL | #585 | — |
| `list_wings` empty at >100K records | CRITICAL | #688 | — |
| ChromaDB version incompatibility (1.x vs <0.7 pin) | CRITICAL | #686, #445 | #581, #426 |
| Global palace single point of failure | HIGH | #444 | #446 |
| MCP `tool_search` no limit upper bound | HIGH | #477 | — |
| CJK surrogate error on Windows in MCP | HIGH | #503 | #512, #631 |
| `chromadb<0.7` pin breaks Python 3.14 | HIGH | #487 | #581, #302 |
| Stale search results after CLI mine | HIGH | #608 | #620, #663 |
| `convo_miner` re-processes every run | HIGH | #654 | — |

### Low-priority findings (no issue needed)

| Finding | Severity | Reason |
|---|---|---|
| Unauthenticated `delete_drawer` MCP tool | MEDIUM | Local-only; partial coverage by #647 (merged) |
| Precompact hook unsanitized SESSION_ID | MEDIUM | Covered by #387 (merged) security hardening |
| `--palace` path not sandboxed | MEDIUM | Local CLI tool, user controls their own paths |
| Unexpanded `~` in `hooks_cli.py` `MEMPAL_DIR` | MEDIUM | Niche env var usage |
| `_entity_id` collision ("O'Neil" vs "oneil") | LOW | Edge case |
| Dual env var names (`MEMPALACE` vs `MEMPAL`) | LOW | Convenience, not a bug |
| Temporal invalidation allows contradictions | LOW | No user reports |

---

## Summary by Category

| Category | Open | Notes |
|---|---|---|
| Bugs — labeled `bug` | 27 | +1 since last sync |
| Bugs — unlabeled but clearly bugs | ~43 | Upstream label debt continues |
| Features — labeled `enhancement` | 30 | Same count |
| Features — unlabeled (notable) | ~47 | |
| Questions / Discussion / Thanks | ~19 | |
| **Total open issues** | **172** | |
| **Total open PRs** | **115** | Down from 192 (merge wave) |

---

## Recently Merged PRs (2026-03-29 → 2026-04-12, 30 total)

| PR | Branch | Title | Merged |
|---|---|---|---|
| **#679** | `docs/fix-stale-org-refs` | docs: fix stale org URLs and PR branch target | 2026-04-12 |
| **#675** | `fix/ruff-format` | style: ruff format all Python files | 2026-04-12 |
| **#674** | `fix/ci-develop-trigger` | ci: trigger tests on develop branch | 2026-04-12 |
| **#667** | `merge/635-resolved` | feat: new MCP tools — get/list/update drawer, hook settings, export | 2026-04-12 |
| **#666** | `fix/hook-reason-ambiguity-and-contributing-docs` | fix: disambiguate hook block reasons | 2026-04-12 |
| **#664** | `fix/blob-seq-id-migration` | fix: auto-repair BLOB seq_ids from chromadb 0.6→1.5 migration | 2026-04-12 |
| **#653** | `fix/ort-disable-coreml-noop` | fix: remove no-op ORT_DISABLE_COREML env var (#397) | 2026-04-12 |
| **#647** | `fix/security-hardening-mcp-kg` | Security hardening: input validation, arg whitelisting, concurrency | 2026-04-12 |
| **#610** | `fix/mtime-float-comparison` | fix: epsilon comparison for mtime dedup | 2026-04-11 |
| **#609** | `fix/compress-token-count` | fix: correct token count in compress summary | 2026-04-11 |
| **#600** | `codex/issue-584-mcp-ping` | fix: implement MCP ping health checks | 2026-04-11 |
| **#598** | `fake_websites_warning_v1` | docs: README warning about fake MemPalace websites | 2026-04-11 |
| **#569** | `fix/compress-stats-keys` | fix: align cmd_compress dict keys | 2026-04-11 |
| **#558** | `fix/windows-reparse-point-oserror` | fix: skip unreachable reparse points on Windows | 2026-04-11 |
| **#544** | `fix/525-hnsw-bloat-dedup` | fix: prevent HNSW index bloat from duplicate add() | 2026-04-10 |
| **#502** | `fix/chromadb-version-migration` | feat: mempalace migrate — recover palaces from different ChromaDB versions | 2026-04-10 |
| **#497** | `ben/droid-readiness` | chore: improve agent readiness — AGENTS.md, dependabot, CODEOWNERS | 2026-04-10 |
| **#491** | `ben/openclaw-skill` | feat: add OpenClaw/ClawHub skill | 2026-04-10 |
| **#450** | `fix/close-kg-sqlite-in-tests` | fix: close KnowledgeGraph SQLite connections in test fixtures | 2026-04-12 |
| **#449** | `fix/remove-duplicate-cache-declarations` | fix: remove duplicate cache declarations in mcp_server.py | 2026-04-12 |
| **#439** | `docs/vitepress-site` | docs: add VitePress documentation site | 2026-04-12 |
| **#414** | `chore/disable-bump-version-workflow` | chore: disable broken auto-bump workflow | 2026-04-09 |
| **#413** | `codex/mempalace-backend-seam` | mempalace backend seam | 2026-04-11 |
| **#409** | `chore/bump-v3.1.0` | chore: bump version to 3.1.0 | 2026-04-09 |
| **#399** | `ben/critical-bugfixes` | fix: MCP null args hang, repair recursion, OOM on large files | 2026-04-09 |
| **#392** | `fix/windows-mtime-test` | fix: Windows mtime test compatibility | 2026-04-09 |
| **#387** | `ben/security-hardening` | security: harden inputs, fix shell injection, optimize DB access | 2026-04-09 |
| **#385** | `fix/query-sanitizer-prompt-contamination` | fix: mitigate system prompt contamination in search queries | 2026-04-11 |
| **#373** | `fix/issue-347-codex-hook-message-counting` | fix: count Codex user_message turns | 2026-04-10 |
| **#371** | `fix/issue-339-338-silent-exceptions-pagination` | fix: paginate large collection reads and surface errors | 2026-04-11 |
| **#361** | `fix/split-dir-tilde-expansion` | fix: expand ~ in split command directory argument | 2026-04-12 |

---

## Open PRs Addressing Bugs / Audit Findings

| PR | Branch | Addresses | State |
|---|---|---|---|
| #687 | `fix/dry-run-room-none` | TypeError on `--dry-run` with room=None (#586) | OPEN |
| #685 | `fix/claude-ai-export-parsing` | Claude.ai export not parsed (#677) | OPEN |
| #684 | `fix/kwargs-var-keyword` | Skip arg whitelist for `**kwargs` handlers (#572) | OPEN |
| #683 | `fix/sanitize-unicode` | Allow Unicode in `sanitize_name()` (#637) | OPEN |
| #682 | `fix/init-yes-flag` | Add `--yes` flag to init instructions (#534) | OPEN |
| #681 | `fix/unicode-checkmark` | Replace Unicode checkmark with ASCII for Windows (#535) | OPEN |
| #676 | `fix/claude-ai-export-mining` | Handle large claude.ai exports (#677) | OPEN |
| #673 | `feat/deterministic-hook-save` | Deterministic hook saves — zero data loss | OPEN |
| #670 | `fix/windows-python-resolution` | Resolve Python interpreter in hooks (#378, #650) | OPEN |
| #668 | `fix/mcp-unicode-ping-taxonomy-metadata` | MCP unicode + remove remaining read caps | OPEN |
| #663 | `fix/mcp-mtime-reconnect-v2` | Stale HNSW index detection (#608) | OPEN |
| #632 | `pr/maintenance` | Repair nuke-rebuild, purge command, --version (#619) | OPEN |
| #631 | `fix/windows-unicode-encoding-v2` | Windows CJK encoding crash in MCP (#503) | OPEN |
| #620 | `fix/add-drawer-stale-cache-and-silent-exceptions` | Cache invalidation + error logging | OPEN |
| #617 | `fix/mine-config-dir` | Add `--config` flag to mine (#14) | OPEN |
| #613 | `chore/remove-dead-code` | Remove duplicate cache declarations + no-op handler | OPEN |
| #581 | `fix/upgrade-chromadb-1x` | Upgrade chromadb to >=1.5.4 for Python 3.13/3.14 (#487, #686) | OPEN |
| #563 | `fix/navigation-limit-10000` | Replace hardcoded limit=10000 with dynamic `col.count()` | OPEN |
| #523 | `fix/hnswlib-update-path-race` | Purge stale drawers before re-mine (#521) | OPEN |
| #512 | `fix/windows-cjk-encoding` | Comprehensive Windows CJK support for MCP (#503) | OPEN |
| #346 | `fix/hnsw-index-bloat` | Prevent HNSW index bloat from resize+persist (#344) | OPEN |
| #340 | `fix/mcp-pipx-compat` | Add `mempalace-mcp` entry point for pipx/uv (#355) | OPEN |
| #329 | `fix/chatgpt-mapping-active-branch` | ChatGPT parser data loss (#330) | OPEN |
| #181 | `fix/mcp-error-hardening` | MCP error messages + read-only mode | OPEN |
