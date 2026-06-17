Render one abbreviated audit row for Part III (manual verification) or Part IV (mini triage) of a multi-tier report. Use candidate fields from `06-ReproChecks.json` or the handoff. Refer to contracts as "the `X` contract", not `@src/X.sol` paths; refer to functions as `contractA.functionName()`, not bare `functionName()` or "functionName function". Do not use em-dashes (—). Do not present the row as a confirmed finding.

For Part III use status `Manual verification — not reproduced locally`. For Part IV set status to `Mini triage — {mini_category}` where `mini_category` is one of: `needs_evidence`, `c0_high`, `falsified`, `backlog`, `coverage_gap`.

Output exactly one fenced markdown code block per row (four backticks outer fence as below). Keep the entire block under 120 words.

````
### [{id}] {title}

**Status:** {Manual verification — not reproduced locally | Mini triage — {mini_category}}

| **Field** | **Value** |
| --- | --- |
| **Confidence** | {C0|C1|C2} |
| **Severity hypothesis** | {severity_hypothesis} |
| **Verification** | {verification_status}: {one-line result} |

**Anchors**
{the `Contract` contract; `Contract.functionName()` — one line}

**Attack path**
{one sentence}

**Next step**
{first falsification step or notes_for_manual_verifier; one line}

*Not a confirmed finding. Requires manual verification or additional evidence.*
````

When `mini_category` is `needs_evidence` and there is no candidate id, use id `NEEDS-EVIDENCE` and title `Environment and artifact blockers`; put blockers in **Attack path** and attempted fixes in **Next step**.
