Convert this comment into an issue for an audit report in Markdown. Use @filename_or_url for context. Provide sound reasoning such as to make a convincing case. Make the report short and concise, avoid rephrasing sentences. Do not use em-dashes (—) in the output. No need for introduction/summary paragraph in the report. The severity and number of the issue, I provided in the comment. Do not replicate or reference the comment, instead, generate a section in a code block as follows:

Avoid long synonym stacks and hedging (for example stacking "might", "possibly", or "perhaps"). When a statement is not directly supported by the comment or @ context, prefix that clause with exactly `Speculation:` (same line or the line immediately before the speculative sentence). Claims grounded in the comment or @ context need no such label. Prefer direct wording so an auditor can verify quickly.

```  
## [H/M/L-Number] Title in normal case stating the highest impact in simple terms. Only upper case the first word of the sentence and other essentials

**One-line claim and scope**
One sentence stating the worst-case outcome in plain language. Then briefly state what is in scope for this report and what is explicitly out of scope or not claimed (for example governance compromise, trusted roles, or unknown deployment parameters), using short bullets if needed.

| **Topic** | ... |
| --- | --- |
| **Impact** | High/Medium/Low |
| **Likelihood** | High/Medium/Low |

**Confidence**
High, Medium, or Low, plus one short sentence explaining why (for example confirmed from described flow in context, inferred from static reading only, or depends on live or off-chain data).

**Entry points**
List the main `function()`, instruction, handler, or route names, and the contract, module, or program names, an auditor should open first. Use `code` formatting; functions include parentheses as in `functionName()`.

Detailed description of this finding as inferred from the comment and the context. Walk through the part of the logic where the root cause of the issue is located, clearly point out the root cause and finally outline the scenario with the highest impact.  Do not omit any information provided in the comment. No need for introduction/summary paragraph in the report. Do not mention line numbers.

Include any links from the comment. If there are any quotes in the comment, integrate them into your description. All mentions to function, variable and contract names should be formatted as `code snippets`. Functions must always be formatted with parentheses after their name, as in `functionName()`. Code blocks must be formatted using TWO backticks instead of 3, as in:

``
some function() {
}
``
**Reference: filename**

However, do not include any code blocks from the existing code in your output as those will be linked to the report on submission.

**Step by step reproduce**
Numbered steps from a stated initial state (environment, fork or chain, roles, balances, config). Include setup, calls, parameters, and what to observe after each step when useful.

**Expected vs actual**
A compact two-row table or two labeled lines so verification is binary:

| **Expected** | ... |
| **Actual** | ... |

**Auditor verification checklist**
Include 3 to 5 lines starting with `- [ ]`, each a short imperative check an auditor can perform to confirm or reject the finding.

**What would invalidate this**
Bullets listing the main conditions, configurations, or evidence under which this finding would not apply or would be disproved.

**Fix**
The fix must be given only as a unified diff in a code block fenced with TWO backticks (not three), for example:

``
diff --git a/path/to/file.sol b/path/to/file.sol
--- a/path/to/file.sol
+++ b/path/to/file.sol
@@ -1,3 +1,3 @@
- old line
+ new line
``

---

```
