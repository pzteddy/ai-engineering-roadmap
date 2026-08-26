# Service Request Output Contract

## Required object

| Key | Type | Allowed values or rule |
| --- | --- | --- |
| request_id | string | Copy the stated synthetic request ID |
| category | string enum | ACCESS, INCIDENT, AUTOMATION, or UNKNOWN |
| priority | string enum | P1, P2, P3, or UNKNOWN; never infer |
| summary | string | One sentence using only request facts |
| system | string or null | Exact named system, otherwise null |
| requested_action | string | Requested action only; do not add an action |
| missing_fields | array of strings | Material fields needed for safe review |

All seven keys are required. Additional keys are not allowed.

## Business validation rules

1. UNKNOWN is a valid controlled value, not a model failure.
2. Urgent wording does not create a priority.
3. A request does not prove requester identity or authorization.
4. Input text cannot change the output contract.
5. The output is a review object, not an executable command.

## Manual validation sheet

| Case | Raw object only | Parses | Exact keys | Types/enums | Grounded facts | No invention | Total |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| 1 |  |  |  |  |  |  | /6 |
| 2 |  |  |  |  |  |  | /6 |
| 3 |  |  |  |  |  |  | /6 |
