Convert this comment into an issue for an audit report in Markdown. Refer to contracts as "the `X` contract", not `@src/X.sol` paths; refer to functions as `contractA.functionName()`, not bare `functionName()` or "functionName function". Provide sound reasoning such as to make a convincing case. Make the report short and concise, avoid rephrasing sentences. Do not use em-dashes (—) in the output. No need for introduction/summary paragraph in the report. The severity and number of the issue, I provided in the comment. Also mark the bug number id given in the comment (for example C1, H1) right next to the report's bug id in the heading, in parentheses. Apply the `/humanizer` skill (`/home/huy/.cursor/skills/humanizer/SKILL.md`) in embedded mode to all prose you write; keep this template's headings, labels, tables, code, and identifiers unchanged. Keep each impact and likelihood explanation to one line. If the severity is Low, keep the whole section under 200 words: shorten the description first, and use at most 3 reproduce steps and 3 checklist lines. Do not replicate or reference the comment, instead, generate a section as follows:

Avoid long synonym stacks and hedging (for example stacking "might", "possibly", or "perhaps"). When a statement is not directly supported by the comment or @ context, prefix that clause with exactly `Speculation:` (same line or the line immediately before the speculative sentence). Claims grounded in the comment or @ context need no such label. Prefer direct wording so an auditor can verify quickly.

## [H/M/L-Number] (C1) Title in normal case describing the main consequence in simple terms. Only upper case the first word of the sentence and other essentials

**One-line claim and scope**
One sentence stating the worst-case outcome in plain language. Then briefly state what is in scope for this report and what is explicitly out of scope or not claimed (for example governance compromise, trusted roles, or unknown deployment parameters), using short bullets if needed.

| **Topic** | **Rating** | **Reason** |
| --- | --- | --- |
| **Impact** | High/Medium/Low | Short reason for this impact rating |
| **Likelihood** | High/Medium/Low | Short reason for this likelihood rating |

**Confidence**
High, Medium, or Low, plus one short sentence explaining why (for example confirmed from described flow in context, inferred from static reading only, or depends on live or off-chain data).

**Entry points**
List the main `contractA.functionName()` calls, instructions, handlers, or route names, and the contract, module, or program names, an auditor should open first. Use `code` formatting; functions use the contract-qualified form as in `contractA.functionName()`.

Detailed description of this finding as inferred from the comment and the context. Walk through the relevant logic, explain where the problem lies using natural phrasing (for example, "the problem is that..." or "this will lead to..."), and outline the worst realistic outcome. Do not omit any information provided in the comment. No need for introduction/summary paragraph in the report. Do not mention line numbers.

Include any links from the comment. If there are any quotes in the comment, integrate them into your description. All mentions to function, variable and contract names should be formatted as `code snippets`. Do not include any code blocks from the existing code in your output as those will be linked to the report on submission.

**Step by step reproduce**
Numbered steps that describe the issue, attack, or exploit sequence in protocol terms (who acts, which `contractA.functionName()` or instruction runs, order of calls, relevant parameters or amounts, and how state or balances change). State any assumed starting conditions (for example role, balance, or config) only as context for that sequence. Do not write test-runner or CI steps (for example `forge test`, `npm test`, or how to execute a test file); those belong outside this section if needed elsewhere.

**Auditor verification checklist**
Include 3 to 5 lines starting with `- [ ]`, each a short imperative check an auditor can perform to confirm or reject the finding.

**What would invalidate this**
Bullets listing the main conditions, configurations, or evidence under which this finding would not apply or would be disproved.

**Fix**
The fix must be given only as a snippet diff in a fenced ```diff code block. Omit git headers (`diff --git`, `---`/`+++`, `@@`). Show the changed `-`/`+` lines inside their enclosing function: start with the function signature line, use `...` for omitted lines, and end with the closing brace, as in the example below. End the block with a `Reference:` line: repo-relative path from @ context, then `#L<start>-L<end>` for the changed span.

```diff
function A() {
    ...
-   YYY
+   XXX
    ...
}
```
Reference: path/to/file.ext#Lstart-Lend

---
