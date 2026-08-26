# Starter Prompt — Indiscriminate Context Dump

This prompt is intentionally weak. Use it for Variant B without removing stale, unauthorized, or
instruction-like material.

~~~text
Answer the QUESTION based on all the documents below. Give a confident recommendation.

<DOCUMENTS>
PASTE THE ENTIRE SYNTHETIC POLICY PACK HERE
</DOCUMENTS>

<QUESTION>
PASTE QUESTION 1 HERE
</QUESTION>
~~~

## Known weaknesses

- It assumes all documents are equally relevant and authoritative.
- It has no effective-date, version, or permission rule.
- It requests confidence even when evidence is missing.
- It does not separate source text from instructions.
- It does not require citations or expose uncertainty.
