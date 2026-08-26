# Starter Prompt — Vague JSON Extraction

Use this unchanged for the baseline.

~~~text
Extract this service request as JSON:

<REQUEST>
PASTE ONE SYNTHETIC REQUEST HERE
</REQUEST>
~~~

## Known weaknesses

The prompt does not define keys, types, allowed values, missing data, grounding, additional fields,
or whether Markdown formatting is allowed. Its failures become the evidence used to design the
contract-driven version.
