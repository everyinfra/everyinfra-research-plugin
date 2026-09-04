# EveryInfra Research workflow and acceptance criteria

## Intended outcome

A concise claim, scoped conclusion, supporting original links, relevant dates and an explicit uncertainty section. The workflow should make it possible for a reader to inspect why the conclusion follows.

## Execution contract

1. Write the concrete claim or decision question, preserving date, jurisdiction, version and site scope.
2. Discover everyinfra_search and the live crosscheck schema.
3. Keep retrieval mechanisms distinct. Do not count duplicated keyword searches as independent corroboration.
4. Inspect original URLs and source dates; distinguish publication date from event date when relevant.
5. Report agreement, contradictions and gaps, then state a conclusion no stronger than the evidence allows.

## Failure handling

If discovery or catalog access fails, stop before a paid action. Read required fields from the current schema instead of copying a remembered payload. Report unavailable capabilities and denied account scopes as distinct conditions. Do not broaden keys, repeatedly retry a permanent error or substitute an unrelated mechanism without disclosure.

- An unavailable or empty retrieval path is uncertainty, not proof that a claim is false.
- Independent mechanisms do not automatically mean independent publishers or underlying evidence.
- No guarantee that every current claim can be resolved, and no invented confidence percentage.

## Worked request boundaries

### Scenario 1

> Verify this current product claim as of the date I provide. Prefer original documentation and separate confirmed facts from gaps.

Accepted behavior: preserve the stated scope; discover the required contract and stop at the explicit no-action boundary. Any broader operation requires new authority.

### Scenario 2

> These two sources disagree. Compare their dates, scope and original evidence before giving a conclusion.

Accepted behavior: preserve the stated scope; discover the required contract and stop at the explicit no-action boundary. Any broader operation requires new authority.

### Scenario 3

> Cross-check this claim using the live available mechanisms. If crosscheck is unavailable, disclose the fallback and do not describe it as equivalent.

Accepted behavior: preserve the stated scope; discover the required contract and stop at the explicit no-action boundary. Any broader operation requires new authority.


These are illustrative prompts, not captured API responses or claims of successful live execution. They deliberately avoid guessed JSON payloads and fabricated prices. See [prompt acceptance fixtures](../examples/acceptance.json) for the offline safety assertions.

## Result review

A concise claim, scoped conclusion, supporting original links, relevant dates and an explicit uncertainty section. The workflow should make it possible for a reader to inspect why the conclusion follows.

Check original results rather than relying on the agent's summary alone. Preserve response status and evidence only to the extent safe; redact personal or secret fields. If billing is absent from the response, say it is not observable there rather than inferring a charge from HTTP success.

## Related decision

EverySearch retrieves material. Research adds claim definition, source comparison and evidence-calibrated conclusions. It does not replace professional judgment in high-stakes decisions.

Return to [README](../README.md) or [setup](setup.md).
