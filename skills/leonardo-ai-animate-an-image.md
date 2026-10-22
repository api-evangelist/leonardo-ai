---
generated: '2026-10-21'
method: generated
name: animate-an-image
title: Turn an image into a video
description: Upload a source image, start an image-to-video generation, and retrieve the resulting video.
api: openapi/leonardo-ai-motion-api-openapi.yml
operations:
- uploadInitImage
- getInitImageById
- createImageToVideoGeneration
- getGenerationById
source: Grounded in openapi/leonardo-ai-motion-api-openapi.yml and the related specs named in the steps; auth, webhook,
  error and rate-limit rules from docs.leonardo.ai pages cited below.
---

# Turn an image into a video

Upload a source image, start an image-to-video generation, and retrieve the resulting video.

## Steps
1. `uploadInitImage` (POST /init-image, in openapi/leonardo-ai-init-images-api-openapi.yml) with `extension`. The response `uploadInitImage` holds `id`, `url` and `fields`: upload the file to that presigned URL with the returned fields.
2. (Optional) `getInitImageById` (GET /init-image/{id}) to confirm the upload.
3. `createImageToVideoGeneration` (POST /generations-image-to-video) with `prompt`, `imageId` (the init image id) and `imageType` (required), plus optional `model`, `resolution`, `duration`. Read `motionVideoGenerationJob.generationId`.
4. Retrieve the result with `getGenerationById` (GET /generations/{id}, openapi/leonardo-ai-image-api-openapi.yml) or via the webhook callback.

## Rules
- Auth: `Authorization: Bearer <API key>` (bearerAuth in every spec; see ../authentication/leonardo-ai-authentication.yml).
- Generation jobs are asynchronous: the create call returns a job id. Prefer the webhook callback configured on the production API key (https://docs.leonardo.ai/docs/guide-to-the-webhook-callback-feature) over polling; if polling, back off between calls.
- Concurrency and queue limits apply (https://docs.leonardo.ai/docs/guide-to-concurrency-queue-and-rate-limit, ../rate-limits/leonardo-ai-rate-limits.yml). No idempotency keys are documented, so do not blindly retry a create call: it spends API credits again.
- Errors such as content-moderation 403s, invalid dimensions and prompt-length limits are listed at https://docs.leonardo.ai/docs/api-error-messages.
- Each job response reports `apiCreditCost`; check cost first with `pricingCalculator` when spend matters.
