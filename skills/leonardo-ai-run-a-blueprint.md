---
generated: '2026-10-21'
method: generated
name: run-a-blueprint
title: Execute a Blueprint
description: Find a Blueprint, choose a version, execute it with inputs, and collect the generations it produced.
api: openapi/leonardo-ai-blueprints-api-openapi.yml
operations:
- listBlueprints
- getBlueprintById
- getBlueprintVersionsByBlueprintId
- executeBlueprint
- getBlueprintExecution
- getBlueprintExecutionGenerations
source: Grounded in openapi/leonardo-ai-blueprints-api-openapi.yml and the related specs named in the steps; auth,
  webhook, error and rate-limit rules from docs.leonardo.ai pages cited below.
---

# Execute a Blueprint

Find a Blueprint, choose a version, execute it with inputs, and collect the generations it produced.

## Steps
1. `listBlueprints` (GET /blueprints) and `getBlueprintById` (GET /blueprints/{id}) to pick a Blueprint.
2. `getBlueprintVersionsByBlueprintId` (GET /blueprints/{id}/versions) to get a `blueprintVersionId` and its expected inputs.
3. `executeBlueprint` (POST /blueprint-executions) with `blueprintVersionId` and `input` (both required). Read `executeBlueprint.akUUID`.
4. Poll `getBlueprintExecution` (GET /blueprint-executions/{id}) until done.
5. `getBlueprintExecutionGenerations` (GET /blueprint-executions/{id}/generations) for the outputs.

## Rules
- Auth: `Authorization: Bearer <API key>` (bearerAuth in every spec; see ../authentication/leonardo-ai-authentication.yml).
- Generation jobs are asynchronous: the create call returns a job id. Prefer the webhook callback configured on the production API key (https://docs.leonardo.ai/docs/guide-to-the-webhook-callback-feature) over polling; if polling, back off between calls.
- Concurrency and queue limits apply (https://docs.leonardo.ai/docs/guide-to-concurrency-queue-and-rate-limit, ../rate-limits/leonardo-ai-rate-limits.yml). No idempotency keys are documented, so do not blindly retry a create call: it spends API credits again.
- Errors such as content-moderation 403s, invalid dimensions and prompt-length limits are listed at https://docs.leonardo.ai/docs/api-error-messages.
- Each job response reports `apiCreditCost`; check cost first with `pricingCalculator` when spend matters.
