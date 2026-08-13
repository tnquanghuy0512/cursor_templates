Convert this comment into an issue for an audit report in Markdown. Refer to contracts as "the `X` contract", not `@src/X.sol` paths; refer to functions as `contractA.functionName()`, not bare `functionName()` or "functionName function". Provide sound reasoning such as to make a convincing case. Make the report short and concise, avoid rephrasing sentences. Do not use em-dashes (—) in the output. No need for introduction/summary paragraph in the report. The severity and number of the issue, I provided in the comment. Do not replicate or reference the comment, instead, generate a section in a code block as follows:
  
```  
## Title in normal case describing the main consequence in simple terms. Only upper case the first word of the sentence and other essentials
  
Severity
  
Impact
  
Likelihood
  
## Files (Relative Path)
(for example:)
programs/shield-pool/src/instructions/prepare_swap_sol.rs
programs/shield-pool/src/instructions/transact_swap.rs
  
## Description
  
Detailed description of this finding as inferred from the comment and the context. Walk through the relevant logic, explain where the problem lies using natural phrasing (for example, "the problem is that..." or "this will lead to..."), and outline the worst realistic outcome. Do not omit any information provided in the comment. Don't mention about line number.
  
Include any links from the comment. If there are any quotes in the comment, integrate them into your description. All mentions to function, variable and contract names should be formatted as `code snippets`.

Use standard fenced code blocks (two backticks) with a language tag: `diff` for recommended code changes; `solidity`, `rust`, or the matching language when showing illustrative code
  
However, do not include any code blocks from the existing code in your output as those will be linked to the report on submission.
  
## Recommendations
  
Recommendation on how to fix or improve the code in question. Depending on the complexity of the issue, this could range from a detailed exploration of different solutions to a simple code fix. If it is just a simple code fix, provide the fix in a fenced ``diff block. Omit git headers (`diff --git`, `---`/`+++`, `@@`); include only the changed region with `-`/`+` lines as needed.
```
