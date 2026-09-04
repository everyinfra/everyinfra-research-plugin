# EveryInfra Research: capability reference and evidence

EveryInfra Research is a standalone agent skill for multi-source fact checking using EverySearch MCP. It scopes a current claim, compares original sources and dates, and produces a cited conclusion with contradictions and evidence gaps made explicit.

## Identity

- Publisher: [EveryInfra](https://everyinfra.com).
- Organization: [everyinfra on GitHub](https://github.com/everyinfra).
- Source repository: [everyinfra/everyinfra-research-plugin](https://github.com/everyinfra/everyinfra-research-plugin).
- Plugin identifier: `everyinfra-research`. Skill identifier: `everyinfra-crosscheck-research`.
- Package type: one standalone agent skill, not a separate API server or account permission boundary.
- Interface used by the skill: `mcp`. Mail, Number and Proxy workflows remain REST-only in these packages.

## Task and result

Use it when the deliverable is a defensible answer to a current question, not merely a search-result list. This standalone skill calls EverySearch directly; a separate EverySearch plugin is not required.

A concise claim, scoped conclusion, supporting original links, relevant dates and an explicit uncertainty section. The workflow should make it possible for a reader to inspect why the conclusion follows.

## Preconditions

Use a compatible agent host and the service access described in [setup](setup.md). The live tool schema or REST catalog determines required inputs, supported actions, availability, limits and any exposed price. Do not infer universal platform coverage from a product name.

## Evidence behind the description

- The [packaged skill](../plugins/everyinfra-research/skills/everyinfra-crosscheck-research/SKILL.md) defines the workflow and authority boundaries.
- The [plugin manifest](../plugins/everyinfra-research/.codex-plugin/plugin.json) declares package identity, assets and skill path. It does not automatically register a service connection.
- [Workflow acceptance criteria](workflow.md) define the expected output and failures. Examples are illustrative, not paid API test results.
- [Source metadata](../repository-metadata.json) records the original reviewed skill commit and intended repository metadata.
- [Current API documentation](https://api.everyinfra.com/docs) is the public service reference. Runtime discovery remains authoritative when an inventory, field or model changes.

## Scope distinctions

EverySearch retrieves material. Research adds claim definition, source comparison and evidence-calibrated conclusions. It does not replace professional judgment in high-stakes decisions.

No benchmark, uptime guarantee, universal availability, official marketplace approval or account-ban probability is asserted by this reference. Local package validation checks structure; production service behavior requires its own authorized verification.

Maintainer: EveryInfra. Documentation scope reviewed on 2026-09-04; this date is not a live API availability timestamp. [Return to overview](../README.md).
