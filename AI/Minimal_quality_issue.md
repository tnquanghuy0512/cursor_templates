Convert this comment into an issue for an audit report in Markdown. Use @filename_or_url for context. Provide sound reasoning such as to make a convincing case. Make the report short and concise, avoid rephrasing sentences. Do not use em-dashes (—) in the output. No need for introduction/summary paragraph in the report. Note that the issue will not be severe so don't bluff it. The severity and number of the issue, I provided in the comment. Make it short and compact. MAXIMUM 200-250 words for the entire generated section inside the code block. Do not replicate or reference the comment, instead, generate a section in a code block as follows:

Avoid long synonym stacks and hedging (for example stacking "might", "possibly", or "perhaps"). When a statement is not directly supported by the comment or @ context, prefix that clause with exactly `Speculation:` (same line or the line immediately before the speculative sentence). Claims grounded in the comment or @ context need no such label. If the word limit conflicts with full prose, shorten the narrative description first; keep **One-line claim and scope**, **Expected vs actual**, **Auditor verification checklist**, and **What would invalidate this** usable and non-empty.

```  
## [Q-Number] Title in normal case stating the highest impact in simple terms. Only upper case the first word of the sentence and other essentials

**One-line claim and scope**
One sentence for outcome, then at most two short bullets for in scope and not claimed.

| **Topic** | ... |
| --- | --- |
| **Impact** | High/Medium/Low |

**Confidence**
High, Medium, or Low, plus a short phrase for why.

**Entry points**
One line: main `function()` or surface names to open first.

Detailed description of this finding as inferred from the comment and the context. Walk through the part of the logic where the root cause of the issue is located, clearly point out the root cause and finally outline the scenario with the highest impact.  Do not omit any information provided in the comment. No need for introduction/summary paragraph in the report. Do not mention line numbers.

**Step by step reproduce**
At most 5 short numbered steps. Stay within the overall word limit.

**Expected vs actual**
Two lines or a tiny two-column table: **Expected** and **Actual**.

**Auditor verification checklist**
3 lines starting with `- [ ]`, each one short imperative check.

**What would invalidate this**
1 or 2 bullets: conditions that would disprove or narrow the finding.

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
