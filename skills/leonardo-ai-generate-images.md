---
generated: '2026-10-21'
method: generated
name: generate-images
title: Generate images from a prompt
description: Estimate cost, optionally improve the prompt, create an image generation job, retrieve the generated
  images, and clean up.
api: openapi/leonardo-ai-image-api-openapi.yml
operations:
- pricingCalculator
- promptImprove
- createGeneration
- getGenerationById
- deleteGenerationById
source: Grounded in openapi/leonardo-ai-image-api-openapi.yml and the related specs named in the steps; auth, webhook,
  error and rate-limit rules from docs.leonardo.ai pages cited below.
---

# Generate images from a prompt

Estimate cost, optionally improve the prompt, create an image generation job, retrieve the generated images, and clean up.

## Steps
1. (Optional) `pricingCalculator` (POST /pricing-calculator) to estimate API credits for the planned generation.
2. (Optional) `promptImprove` (POST /prompt/improve) to rewrite a short prompt.
3. `createGeneration` (POST /generations) with `prompt` (required) plus model, `width`/`height`, `num_images` etc. Read `sdGenerationJob.generationId` and `apiCreditCost`.
4. Wait for the webhook callback, or poll `getGenerationById` (GET /generations/{id}) until the generation is complete; image URLs are under `generations_by_pk.generated_images`.
5. (Optional) `deleteGenerationById` (DELETE /generations/{id}) to remove it.
The v2 API (openapi/leonardo-ai-v2-api-openapi.yml) exposes its own `createGeneration` (POST /v2/generations) returning `generationId` for newer models; the hosted MCP tool `generate-image` covers this flow for agents.

## Rules
- Auth: `Authorization: Bearer <API key>` (bearerAuth in every spec; see ../authentication/leonardo-ai-authentication.yml).
- Generation jobs are asynchronous: the create call returns a job id. Prefer the webhook callback configured on the production API key (https://docs.leonardo.ai/docs/guide-to-the-webhook-callback-feature) over polling; if polling, back off between calls.
- Concurrency and queue limits apply (https://docs.leonardo.ai/docs/guide-to-concurrency-queue-and-rate-limit, ../rate-limits/leonardo-ai-rate-limits.yml). No idempotency keys are documented, so do not blindly retry a create call: it spends API credits again.
- Errors such as content-moderation 403s, invalid dimensions and prompt-length limits are listed at https://docs.leonardo.ai/docs/api-error-messages.
- Each job response reports `apiCreditCost`; check cost first with `pricingCalculator` when spend matters.
