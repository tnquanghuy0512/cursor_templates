Layout for one abbreviated audit row in Part III (manual verification) or Part IV (mini triage) of a multi-tier report. `bh.py report` reads the block between the `bh-row` markers and fills one copy per row, so edits there change every rendered row. Text outside the markers is not rendered. Do not use em-dashes (—). Do not present the row as a confirmed finding.

Placeholders, filled from `06-ReproChecks-MASTER.json` and the coverage gaps:

- `{id}`, `{title}`: the row's id and title.
- `{status}`: `Manual verification: not reproduced locally` for Part III, `Mini triage: {mini_category}` for Part IV. `mini_category` is one of `needs_evidence`, `c0_high`, `falsified`, `backlog`, `coverage_gap`.
- `{confidence}`: C0 to C2, or `n/a`.
- `{severity}`: the severity hypothesis, or `not assessed`.
- `{verification}`: the verification status and a one-line result.
- `{anchors}`: each anchor as `` `symbol` (path:lines) ``, separated by semicolons.
- `{attack_path}`, `{next_step}`: the first line of the attack path and of the first falsification step or manual-verifier note.
- `{found_by}`: the `Found by:` line, plus one `Also found by:` line per extra discoverer.

Blockers, missing artifacts, and attempted fixes are rendered as one row with id `NEEDS-EVIDENCE` and title `Environment and artifact blockers`: blockers and missing artifacts go in `{attack_path}`, attempted fixes in `{next_step}`.

<!-- bh-row-start -->
### [{id}] {title}

**Status:** {status}

| **Field** | **Value** |
| --- | --- |
| **Confidence** | {confidence} |
| **Severity hypothesis** | {severity} |
| **Verification** | {verification} |

**Anchors**
{anchors}

**Attack path**
{attack_path}

**Next step**
{next_step}

{found_by}

*Not a confirmed finding. Requires manual verification or additional evidence.*
<!-- bh-row-end -->
