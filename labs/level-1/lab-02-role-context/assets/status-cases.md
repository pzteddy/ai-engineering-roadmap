# Synthetic Project Status Policy and Test Set

## Policy

- **ON_TRACK:** work is progressing and no known issue threatens the committed milestone.
- **AT_RISK:** work can continue, but a known issue makes the committed milestone or objective
  likely to be missed unless corrective action succeeds.
- **BLOCKED:** work required for the committed milestone cannot continue because an unresolved
  dependency, decision, access need, or failure prevents progress.

When multiple labels are supported, use the most severe supported label. The official status still
requires project-owner review.

## Test cases

### Case 1

~~~text
The mobile build is complete, but release packaging cannot start because the required signing
certificate has expired. Security has not provided a replacement date.
~~~

### Case 2

~~~text
Implementation continues. Two developers were reassigned for this sprint, leaving enough capacity
to finish core scope but making the committed 30 September date unlikely without contractor help.
~~~

### Case 3

~~~text
User acceptance testing finished with all critical cases passed. Documentation is on schedule and
no issue currently threatens the 4 October handover.
~~~

### Case 4

~~~text
Load-test tuning continues, but the current p95 latency is above the signed launch criterion. The
team has two fixes in progress; if neither works this week, the launch date will move.
~~~

### Case 5

~~~text
Validation stopped after the synthetic-data warehouse permission was revoked. No approved
alternative data source exists, and the access request has no response date.
~~~

### Case 6

~~~text
The vendor has an open question about optional dashboard colors. All committed API work is complete,
and the question does not affect the approved milestone or its date.
~~~

## Hidden answer key for evaluation

Read this section only after recording predictions:

1. BLOCKED
2. AT_RISK
3. ON_TRACK
4. AT_RISK
5. BLOCKED
6. ON_TRACK

## Results

### Defined zero-shot

| Case | Predicted | Expected | Exact match? | Notes |
| --- | --- | --- | --- | --- |
| 1 |  | BLOCKED |  |  |
| 2 |  | AT_RISK |  |  |
| 3 |  | ON_TRACK |  |  |
| 4 |  | AT_RISK |  |  |
| 5 |  | BLOCKED |  |  |
| 6 |  | ON_TRACK |  |  |

### Few-shot

| Case | Predicted | Expected | Exact match? | Notes |
| --- | --- | --- | --- | --- |
| 1 |  | BLOCKED |  |  |
| 2 |  | AT_RISK |  |  |
| 3 |  | ON_TRACK |  |  |
| 4 |  | AT_RISK |  |  |
| 5 |  | BLOCKED |  |  |
| 6 |  | ON_TRACK |  |  |
