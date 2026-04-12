# tools/

Personal triage tooling for the MemPalace maintainer workflow.

> **These scripts are local-only.** They stay in the fork clone
> (`/home/igorls/dev/GitHub/mempalace`) and do **not** get pushed to
> `MemPalace/mempalace`.

## `sync_issues.py` — regenerate `docs/ISSUES.md`

Fetches issues + PRs from `MemPalace/mempalace`, enriches with heuristic
classification, and writes `docs/ISSUES.md`.

### Value over a raw `gh` dump

| Enrichment | What it does |
|---|---|
| **Severity classifier** | Regex over title/body keywords (crash, corruption, data-loss, security) → CRITICAL / HIGH. `enhancement`-labeled issues and `[RFC]`-titled proposals are never promoted to CRITICAL from body text alone. |
| **Noise detector** | Flags low-signal issues: `TLDR` / `Thank you` / `new issue` / symbol-only bodies. Titles with bug/error/version signals are excluded. |
| **Suspicious-PR scan** | Checks every open PR's diff for red flags (sensitive paths, `eval`/`exec`, shell pipe from network, raw IPs, unfamiliar domains) plus informational context (first-time contributor, large diff, thin description). Hard flags surface the PR; context alone does not. |
| **Cross-reference** | Matches issue text and PR changed-files against the CLAUDE.md module table (palace.py, miner.py, mcp_server.py, etc). |
| **Duplicate detection** | Open-issue pairs with title similarity > 0.85. |
| **Delta report** | Compares new output against previous `docs/ISSUES.md` for issue/PR count change. |

### Usage

```bash
# Regenerate docs/ISSUES.md from cached fetches (fast)
python tools/sync_issues.py

# Force fresh fetch, bypass cache
python tools/sync_issues.py --no-cache

# Print suspicious-PR report to terminal; don't touch ISSUES.md
python tools/sync_issues.py --audit-prs

# Print noise-candidate list
python tools/sync_issues.py --noise-report

# Skip per-PR diff scans (faster, but no diff-based red flags)
python tools/sync_issues.py --skip-diffs

# Dry-run
python tools/sync_issues.py --dry-run
```

### Cache

Data is cached under `tools/.cache/` with a 6-hour TTL. Delete that directory
or pass `--no-cache` to force a fresh fetch. Cache files:

- `issues.json` — full issue list
- `prs.json` — full PR list
- `author_*.json` — per-author merged-PR count
- `pr_<N>_diff.txt` — per-PR diff (only for open PRs when diff scan is on)

### Tuning the heuristics

All keyword banks and regex patterns are at the top of the file:

- `CRITICAL_KEYWORDS` / `HIGH_KEYWORDS` — severity signals
- `FEATURE_TITLE_PREFIX` / `BUG_TITLE_PREFIX` — issue type markers
- `DEWEIGHT_PHRASES` — "prevent data loss"-style phrasing that shouldn't count
- `NOISE_TITLE_PATTERNS` / `NOISE_BODY_PATTERNS` — junk filters
- `SUBSTANTIVE_TITLE_MARKERS` — protects real bugs from being noise-flagged
- `SENSITIVE_PATHS` — PR path patterns that trigger red flags
- `DIFF_RED_FLAGS` — dangerous diff content (with exclusion patterns for
  common false positives like `re.compile`)
- `MEMPALACE_MODULES` — module names for cross-reference

Tweak and re-run; results are deterministic given the same cache.
