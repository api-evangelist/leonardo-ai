---
generated: '2026-10-21'
method: generated
name: remove-background-and-upscale
title: Remove background or upscale an image
description: Run a no-background, upscale or universal-upscaler variation job on an existing image and fetch the
  output.
api: openapi/leonardo-ai-variation-api-openapi.yml
operations:
- createVariationNoBG
- createVariationUpscale
- CreateUniversalUpscalerJob
- getVariationById
source: Grounded in openapi/leonardo-ai-variation-api-openapi.yml and the related specs named in the steps; auth,
  webhook, error and rate-limit rules from docs.leonardo.ai pages cited below.
---

# Remove background or upscale an image

Run a no-background, upscale or universal-upscaler variation job on an existing image and fetch the output.

## Steps
1. Pick the job: `createVariationNoBG` (POST /variations/nobg, body `id` of a generated image, `isVariation` when it is itself a variation), `createVariationUpscale` (POST /variations/upscale) or `CreateUniversalUpscalerJob` (POST /variations/universal-upscaler).
2. Read the job id from the response (e.g. `sdNobgJob.id`) and its `apiCreditCost`.
3. Poll `getVariationById` (GET /variations/{id}) until the variation is complete and read its URL.
See https://docs.leonardo.ai/docs/migrate-from-the-removebg-api-to-leonardoai.md for the remove.bg migration mapping.

## Rules
- Auth: `Authorization: Bearer <API key>` (bearerAuth in every spec; see ../authentication/leonardo-ai-authentication.yml).
- Generation jobs are asynchronous: the create call returns a job id. Prefer the webhook callback configured on the production API key (https://docs.leonardo.ai/docs/guide-to-the-webhook-callback-feature) over polling; if polling, back off between calls.
- Concurrency and queue limits apply (https://docs.leonardo.ai/docs/guide-to-concurrency-queue-and-rate-limit, ../rate-limits/leonardo-ai-rate-limits.yml). No idempotency keys are documented, so do not blindly retry a create call: it spends API credits again.
- Errors such as content-moderation 403s, invalid dimensions and prompt-length limits are listed at https://docs.leonardo.ai/docs/api-error-messages.
- Each job response reports `apiCreditCost`; check cost first with `pricingCalculator` when spend matters.
