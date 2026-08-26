# Reference Solution — Prompt Strategy Decision Guide

## The practical distinction

| Method | What you supply | Best starting use | Main trade-off |
| --- | --- | --- | --- |
| Zero-shot | Instructions and new task input, with no completed examples | Familiar, well-defined tasks | Simplest and cheapest, but local patterns may remain ambiguous |
| Few-shot | Instructions plus representative input/output demonstrations | Custom labels, tone, edge cases, or patterns | More consistent pattern following, but more tokens and example maintenance |
| Context-grounded | Instructions plus current/private reference facts | Policy, account, document, or conversation-dependent answers | Better grounding, but access, freshness, retrieval, and injection risks |
| Combined | Reference facts plus demonstrations | Both domain knowledge and response behavior are non-standard | Highest prompt complexity; justify both additions with evaluation |
| External controls | Authorization, deterministic validation, approval, and audit | Consequential actions and high-impact decisions | Engineering work outside prompting is required |

Few-shot and context-grounded prompting both rely on in-context learning. They differ in what the
context is doing: demonstrations teach a pattern; reference context supplies facts.

## Reference decisions for the eight scenarios

| Scenario | Best starting method | Why |
| --- | --- | --- |
| A — Explain an API gateway | Zero-shot | The concept and audience can be described directly; examples add little |
| B — Apply PMO status labels | Few-shot | Local boundary between AT_RISK and BLOCKED is best shown with demonstrations |
| C — Answer the current expense policy | Context-grounded zero-shot | The answer depends on a supplied current company policy, not model memory |
| D — Match support email house style | Few-shot, optionally with policy context | Approved examples convey tone and structure; add facts only if the reply depends on account/policy data |
| E — Extract a service request as JSON | Schema-driven zero-shot first | The contract can be explicit; add examples only for measured semantic failures and prefer Structured Outputs in production |
| F — Continue a long requirements discussion | Conversation context with re-grounding | The task depends on decisions and constraints from earlier turns, not demonstrations |
| G — Report today’s product price | Retrieved current context or abstention | Examples cannot supply a current fact; use an authorized live source |
| H — Approve a USD 50,000 payment | Prompting is insufficient | Identity, policy, deterministic checks, human approval, execution controls, and audit are required |

## Ready-to-run reference patterns

### Scenario A — Zero-shot

~~~text
Explain what an API gateway does to a non-technical project sponsor.

Success criteria:
- 100–140 words;
- explain request routing, authentication enforcement, rate limiting, and observability;
- use one everyday analogy;
- distinguish the gateway from the backend service;
- do not invent company-specific architecture.
~~~

No demonstration is needed unless evaluation shows a specific style failure.

### Scenario B — Few-shot

Use the complete reference prompt from
[Lab 02](../../lab-02-role-context/solution/README.md). The examples earn their place by defining the
observable difference between work that is threatened and work that cannot continue.

### Scenario C — Context-grounded zero-shot

~~~text
You draft expense-policy answers for employee and Finance review.

Use only POLICY_CONTEXT. Cite every rule as [EXP-07 §section].
If the policy does not answer the question, say "Insufficient policy context" and name the missing
rule. Do not approve an expense.

<POLICY_CONTEXT>
EXP-07 v4, effective 2026-08-01
§2: Hotel expenses up to USD 180 per night before tax are reimbursable with an itemized receipt.
§3: A higher rate requires written pre-approval from the cost-center owner before booking.
</POLICY_CONTEXT>

<QUESTION>
May an employee claim a USD 210 hotel night if approval was requested only after checkout?
</QUESTION>

Output: Decision, Policy basis, Missing information, Human reviewer.
~~~

Expected decision: not permitted under the supplied rule unless another current authorized policy
creates an exception; cite §3 and route to the expense owner. The model does not grant approval.

### Scenario D — Few-shot house style

~~~text
Write a support reply that follows the demonstrated house style.

Rules:
- acknowledge the specific problem in the first sentence;
- give one numbered next action;
- state what information is needed if the action fails;
- do not promise a resolution time.

<example>
<customer>My export is empty after I applied a date filter.</customer>
<assistant>
I understand the filtered export is returning no rows.
1. Clear the date filter, select the intended time zone, and run the export again.
If it is still empty, send the filter dates and the displayed time zone; do not send customer data.
</assistant>
</example>

<customer>
PASTE THE SYNTHETIC TEST MESSAGE
</customer>
~~~

Use multiple examples only when they cover genuinely different approved patterns.

### Scenario F — Conversation re-grounding

~~~text
Continue from the conversation context.

Before answering, restate only:
- confirmed objective;
- approved scope;
- unresolved decisions;
- current user question.

If an earlier message conflicts with a later confirmed decision, use the later confirmed decision
and identify the conflict. Do not invent missing owners or dates.
~~~

This uses conversation state as context. It is not few-shot unless completed demonstrations are
also deliberately supplied.

## Debugging order

1. Verify the task and pass criteria.
2. Check whether required facts are present and authorized.
3. Check the output contract.
4. Add examples only for a measured pattern or boundary failure.
5. Retest the same representative cases.
6. Remove instructions, context, or examples that do not improve the pass rate or safety.

## Stop rule

Stop when the smallest prompt meets the declared threshold across representative cases and all
required non-prompt controls are identified. “More detailed” is not itself a quality metric.
