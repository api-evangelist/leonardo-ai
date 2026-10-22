---
generated: '2026-10-21'
method: generated
name: train-a-custom-model
title: Train a custom model from a dataset
description: Create a dataset, upload training images, start a custom model training job and check its status.
api: openapi/leonardo-ai-models-api-openapi.yml
operations:
- createDataset
- uploadDatasetImage
- uploadDatasetImageFromGen
- getDatasetById
- createModel
- getModelById
source: Grounded in openapi/leonardo-ai-models-api-openapi.yml and the related specs named in the steps; auth, webhook,
  error and rate-limit rules from docs.leonardo.ai pages cited below.
---

# Train a custom model from a dataset

Create a dataset, upload training images, start a custom model training job and check its status.

## Steps
1. `createDataset` (POST /datasets, openapi/leonardo-ai-dataset-api-openapi.yml) and keep the dataset id.
2. For each image: `uploadDatasetImage` (POST /datasets/{datasetId}/upload) with `extension`, then upload to the returned presigned `url` with `fields`; or `uploadDatasetImageFromGen` (POST /datasets/{datasetId}/upload/gen) to reuse a generated image.
3. `getDatasetById` (GET /datasets/{id}) to confirm the images landed.
4. `createModel` (POST /models) with `name`, `datasetId` and `instance_prompt` (required). Read `sdTrainingJob.customModelId`.
5. Poll `getModelById` (GET /models/{id}) until training finishes, then use the model id in `createGeneration`.

## Rules
- Auth: `Authorization: Bearer <API key>` (bearerAuth in every spec; see ../authentication/leonardo-ai-authentication.yml).
- Generation jobs are asynchronous: the create call returns a job id. Prefer the webhook callback configured on the production API key (https://docs.leonardo.ai/docs/guide-to-the-webhook-callback-feature) over polling; if polling, back off between calls.
- Concurrency and queue limits apply (https://docs.leonardo.ai/docs/guide-to-concurrency-queue-and-rate-limit, ../rate-limits/leonardo-ai-rate-limits.yml). No idempotency keys are documented, so do not blindly retry a create call: it spends API credits again.
- Errors such as content-moderation 403s, invalid dimensions and prompt-length limits are listed at https://docs.leonardo.ai/docs/api-error-messages.
- Each job response reports `apiCreditCost`; check cost first with `pricingCalculator` when spend matters.
