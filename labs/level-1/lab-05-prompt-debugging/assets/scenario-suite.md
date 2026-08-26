# Enterprise Prompt Strategy Scenario Suite

All organizations, policies, messages, and events are synthetic.

## Scenario A — General explanation

**Request:** Explain an API gateway to a non-technical project sponsor in 100–140 words.

**Tests:** sponsor asks about security, traffic spikes, and the difference from a backend API.

**Pass criteria:** correct plain-language explanation; routing, authentication enforcement, rate
limiting, and observability covered; no invented company architecture.

## Scenario B — Custom project labels

**Request:** Classify weekly updates as ON_TRACK, AT_RISK, or BLOCKED using the PMO’s local policy.

**Tests:** use the six cases from
[Lab 02](../../lab-02-role-context/assets/status-cases.md).

**Pass criteria:** at least 5/6 exact labels and no out-of-set response.

## Scenario C — Current expense policy

**Request:** Answer whether a USD 210 hotel night is reimbursable.

**Required evidence:** current synthetic policy EXP-07 v4 states a USD 180 pre-tax limit and requires
written cost-center-owner approval before booking for a higher rate.

**Tests:** approval before booking, approval after checkout, and no receipt.

**Pass criteria:** every rule cited to supplied policy; no model-created exception or approval.

## Scenario D — Support house style

**Request:** Draft replies that match a short, direct support style.

**Tests:** empty export, locked test account, and delayed batch job.

**Pass criteria:** acknowledge the specific issue, give one numbered next action, request safe
diagnostic information only if needed, and make no resolution-time promise.

## Scenario E — Service request JSON

**Request:** Extract service request text into the fixed seven-key review object.

**Tests:** use the three cases from
[Lab 03](../../lab-03-structured-output/assets/requests.md).

**Pass criteria:** valid JSON, exact contract, grounded values, and no invented priority or approval.

## Scenario F — Long requirements conversation

**Request:** Continue a discussion after the team has changed scope twice and left two decisions
open.

**Tests:** later decision overrides an earlier one; an owner is missing; a new request conflicts with
approved scope.

**Pass criteria:** preserve the latest confirmed decisions, surface unresolved items, and avoid
inventing owners or dates.

## Scenario G — Current external fact

**Request:** Report today’s price and availability for a product.

**Tests:** source unavailable, two current sources disagree, and the product region is unspecified.

**Pass criteria:** use an authorized current source with timestamp and region, or abstain; never use
examples or stale model memory as current evidence.

## Scenario H — Consequential action

**Request:** Approve and release a USD 50,000 supplier payment based on an email.

**Tests:** verified and unverified sender, amount above approval threshold, duplicate invoice, and
payment system unavailable.

**Pass criteria:** state that prompting alone cannot authorize execution; require verified identity,
system-of-record policy checks, segregation of duties, human approval, duplicate detection,
idempotent execution, and audit logging.

## Selection answer sheet

| Scenario | Starting method | Information placed in context | Why alternatives are weaker | Required non-prompt controls |
| --- | --- | --- | --- | --- |
| A |  |  |  |  |
| B |  |  |  |  |
| C |  |  |  |  |
| D |  |  |  |  |
| E |  |  |  |  |
| F |  |  |  |  |
| G |  |  |  |  |
| H |  |  |  |  |
