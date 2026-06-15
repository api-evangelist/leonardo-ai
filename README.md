# Leonardo.AI (leonardo-ai)

Leonardo.AI is an Australian generative-AI company (acquired by Canva in July 2024) offering a Production API for AI image generation, video generation, 3D model creation, custom model and element training, realtime canvas editing, upscaling and variations, and Blueprint workflow execution. The platform supports in-house Leonardo models (Phoenix, Lucid Origin, Lucid Realism) and third-party models (FLUX.1/FLUX.2, Ideogram 3.0, GPT Image, Nano Banana, Seedream, Kling, LTX, Veo, Seedance, Hailuo, Rodin) under a unified pay-as-you-go dollar-denominated API surface with webhook callbacks, MCP server integration, and official Python and TypeScript SDKs.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/leonardo-ai/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/leonardo-ai/refs/heads/main/apis.yml)

## Scope

- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- AI
- Artificial Intelligence
- Image Generation
- Video Generation
- Generative AI
- Creative
- 3D
- Diffusion
- Canva

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-30

## APIs

### Leonardo.AI Image Generation API

Create image generations with FLUX.2 Pro, FLUX Dev, FLUX Schnell, FLUX.1 Kontext, Phoenix, Lucid Origin, Lucid Realism, Ideogram 3.0, GPT Image 2, Nano Banana, Seedream, and other supported models. POST /generations submits a job; results are retrieved via GET /generations/{id} or via the optional webhook callback. Supports PhotoReal, Alchemy, image prompts, image guidance (ControlNet), enhanced prompts, transparency, and per-model knobs.

- **Human URL:** [https://docs.leonardo.ai/reference/creategeneration](https://docs.leonardo.ai/reference/creategeneration)

#### Tags

- AI
- Image Generation
- Generations

#### Properties

- [Documentation](https://docs.leonardo.ai/reference/creategeneration)
- [Getting Started](https://docs.leonardo.ai/docs/getting-started)
- [OpenAPI](openapi/leonardo-ai-image-generation-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/leonardo-ai-image-generation.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/leonardo-ai-image-generation.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [AsyncAPI](asyncapi/leonardo-ai-webhooks-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [JSON Schema](json-schema/leonardo-ai-generation-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/leonardo-ai-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)

### Leonardo.AI Video Generation API

Generate videos from text or images via Kling 2.x/3.x, LTX 2.x, Veo 3.x, Seedance, Hailuo, and Stable Video Diffusion motion models. Three endpoints cover image-to-video, text-to-video, and SVD motion. Jobs are asynchronous; poll the variation/motion endpoints or use a webhook for completion.

- **Human URL:** [https://docs.leonardo.ai/reference/createimagetovideogeneration](https://docs.leonardo.ai/reference/createimagetovideogeneration)

#### Tags

- AI
- Video Generation
- Motion

#### Properties

- [Documentation](https://docs.leonardo.ai/reference/createimagetovideogeneration)
- [OpenAPI](openapi/leonardo-ai-video-generation-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/leonardo-ai-video-generation.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/leonardo-ai-video-generation.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Leonardo.AI Variation and Upscale API

Apply post-generation transformations to existing images including unzoom (outpainting), creative upscale, background removal, and the Universal Upscaler. Retrieve variation job status by ID.

- **Human URL:** [https://docs.leonardo.ai/reference/createvariationupscale](https://docs.leonardo.ai/reference/createvariationupscale)

#### Tags

- AI
- Upscale
- Variation
- Image Editing

#### Properties

- [Documentation](https://docs.leonardo.ai/reference/createvariationupscale)
- [OpenAPI](openapi/leonardo-ai-variation-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/leonardo-ai-variation.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/leonardo-ai-variation.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Leonardo.AI Realtime Canvas API

Real-time Latent Consistency Model (LCM) endpoints for sub-second iterative generation, inpainting, instant refine, and Alchemy upscale — backing the Leonardo Realtime Canvas product surface.

- **Human URL:** [https://docs.leonardo.ai/reference/createlcmgeneration](https://docs.leonardo.ai/reference/createlcmgeneration)

#### Tags

- AI
- Realtime
- LCM
- Canvas

#### Properties

- [Documentation](https://docs.leonardo.ai/reference/createlcmgeneration)
- [OpenAPI](openapi/leonardo-ai-realtime-canvas-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/leonardo-ai-realtime-canvas.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/leonardo-ai-realtime-canvas.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Leonardo.AI Models API

List Leonardo platform models (Phoenix, Lucid, FLUX, Ideogram, etc.) and manage custom fine-tuned models. Includes model catalog, custom model training, retrieval, and deletion by user.

- **Human URL:** [https://docs.leonardo.ai/reference/getplatformmodels](https://docs.leonardo.ai/reference/getplatformmodels)

#### Tags

- AI
- Models
- Custom Models
- Training

#### Properties

- [Documentation](https://docs.leonardo.ai/reference/getplatformmodels)
- [OpenAPI](openapi/leonardo-ai-models-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/leonardo-ai-models.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/leonardo-ai-models.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/leonardo-ai-model-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Leonardo.AI Elements API

Create and manage Custom Elements — LoRA-style style adapters trainable on user datasets and reusable across image generations to enforce visual identity, style, or character consistency.

- **Human URL:** [https://docs.leonardo.ai/reference/createelement](https://docs.leonardo.ai/reference/createelement)

#### Tags

- AI
- Elements
- LoRA
- Fine Tuning

#### Properties

- [Documentation](https://docs.leonardo.ai/reference/createelement)
- [OpenAPI](openapi/leonardo-ai-elements-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/leonardo-ai-elements.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/leonardo-ai-elements.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Leonardo.AI Datasets API

Create, upload to, and delete training datasets used as input to custom model and element training. Upload images directly or from existing generations.

- **Human URL:** [https://docs.leonardo.ai/reference/createdataset](https://docs.leonardo.ai/reference/createdataset)

#### Tags

- AI
- Datasets
- Training

#### Properties

- [Documentation](https://docs.leonardo.ai/reference/createdataset)
- [OpenAPI](openapi/leonardo-ai-datasets-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/leonardo-ai-datasets.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/leonardo-ai-datasets.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Leonardo.AI Init Images API

Upload, retrieve, and delete init images used for image-to-image, image-prompt, canvas, and image-guidance workflows. Returns presigned upload URLs.

- **Human URL:** [https://docs.leonardo.ai/reference/uploadinitimage](https://docs.leonardo.ai/reference/uploadinitimage)

#### Tags

- AI
- Image Upload
- Init Images

#### Properties

- [Documentation](https://docs.leonardo.ai/reference/uploadinitimage)
- [OpenAPI](openapi/leonardo-ai-init-images-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/leonardo-ai-init-images.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/leonardo-ai-init-images.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Leonardo.AI Media API

Upload, retrieve, and delete general-purpose media (images, video frames, reference assets) used across generation endpoints.

- **Human URL:** [https://docs.leonardo.ai/reference/uploadmedia](https://docs.leonardo.ai/reference/uploadmedia)

#### Tags

- AI
- Media
- Upload

#### Properties

- [Documentation](https://docs.leonardo.ai/reference/uploadmedia)
- [OpenAPI](openapi/leonardo-ai-media-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/leonardo-ai-media.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/leonardo-ai-media.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Leonardo.AI 3D Model Assets API

Upload, retrieve, and delete 3D model assets — used with Rodin V2 and other 3D-capable workflows for texturing and generation.

- **Human URL:** [https://docs.leonardo.ai/reference/upload3dmodelasset](https://docs.leonardo.ai/reference/upload3dmodelasset)

#### Tags

- AI
- 3D
- Models
- Assets

#### Properties

- [Documentation](https://docs.leonardo.ai/reference/upload3dmodelasset)
- [OpenAPI](openapi/leonardo-ai-3d-model-assets-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/leonardo-ai-3d-model-assets.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/leonardo-ai-3d-model-assets.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Leonardo.AI Blueprints API

Execute Leonardo Blueprints — pre-packaged multi-step image and video workflows authored in the Leonardo App — and retrieve their executions, generations, and version history. List the blueprint catalog for the authenticated user.

- **Human URL:** [https://docs.leonardo.ai/reference/listblueprints](https://docs.leonardo.ai/reference/listblueprints)

#### Tags

- AI
- Blueprints
- Workflows

#### Properties

- [Documentation](https://docs.leonardo.ai/reference/listblueprints)
- [OpenAPI](openapi/leonardo-ai-blueprints-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/leonardo-ai-blueprints.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/leonardo-ai-blueprints.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Leonardo.AI Prompt API

Improve user-supplied prompts with the Prompt Improvement endpoint and generate random prompts for inspiration. Used to bootstrap and refine generation requests.

- **Human URL:** [https://docs.leonardo.ai/reference/promptimprove](https://docs.leonardo.ai/reference/promptimprove)

#### Tags

- AI
- Prompts
- Prompt Engineering

#### Properties

- [Documentation](https://docs.leonardo.ai/reference/promptimprove)
- [OpenAPI](openapi/leonardo-ai-prompt-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/leonardo-ai-prompt.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/leonardo-ai-prompt.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Leonardo.AI Pricing Calculator API

Pre-calculate the API credit cost (in USD) of a generation request before submitting it. Mirrors the cost estimation logic of the in-app Pricing Calculator.

- **Human URL:** [https://docs.leonardo.ai/reference/pricingcalculator](https://docs.leonardo.ai/reference/pricingcalculator)

#### Tags

- AI
- Pricing
- Cost
- FinOps

#### Properties

- [Documentation](https://docs.leonardo.ai/reference/pricingcalculator)
- [OpenAPI](openapi/leonardo-ai-pricing-calculator-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/leonardo-ai-pricing-calculator.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/leonardo-ai-pricing-calculator.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Leonardo.AI User API

Retrieve the authenticated user's profile, subscription info, and remaining API credit balance via GET /me. Used as the canonical balance-check endpoint for FinOps reporting.

- **Human URL:** [https://docs.leonardo.ai/reference/getuserself](https://docs.leonardo.ai/reference/getuserself)

#### Tags

- AI
- User
- Account

#### Properties

- [Documentation](https://docs.leonardo.ai/reference/getuserself)
- [OpenAPI](openapi/leonardo-ai-user-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/leonardo-ai-user.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/leonardo-ai-user.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Portal](https://leonardo.ai)
- [Portal](https://leonardo.ai/api)
- [Documentation](https://docs.leonardo.ai/)
- [Getting Started](https://docs.leonardo.ai/docs/getting-started)
- [Documentation](https://docs.leonardo.ai/reference)
- [Documentation](https://docs.leonardo.ai/llms.txt)
- [Documentation](https://docs.leonardo.ai/docs/api-faq)
- [Errors](https://docs.leonardo.ai/docs/api-error-messages)
- [Rate Limits](https://docs.leonardo.ai/docs/concurrency-rate-limits-and-queue)
- [Webhooks](https://docs.leonardo.ai/docs/webhook-callback-feature)
- [Webhooks](https://docs.leonardo.ai/docs/guide-to-the-webhook-callback-feature)
- [AsyncAPI](asyncapi/leonardo-ai-webhooks-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [Pricing](https://docs.leonardo.ai/docs/payg-guide)
- [Pricing](https://docs.leonardo.ai/docs/plan-with-the-pricing-calculator)
- [SDK](https://docs.leonardo.ai/docs/leonardoai-official-sdks)
- [Documentation](https://docs.leonardo.ai/docs/mcp-server)
- [Documentation](https://docs.leonardo.ai/docs/nsfw-handling)
- [GitHub Organization](https://github.com/Leonardo-Interactive)
- [SDK](https://github.com/Leonardo-Interactive/leonardo-python-sdk)
- [SDK](https://github.com/Leonardo-Interactive/leonardo-ts-sdk)
- [Tool](https://github.com/Leonardo-Interactive/agent-browser)
- [Tool](https://github.com/Leonardo-Interactive/background-removal-js)
- [Plugins](https://github.com/Leonardo-Interactive/leonardo-texturing-blender-plugin)
- [SDK](https://pypi.org/project/leonardoai/)
- [SDK](https://www.npmjs.com/package/@leonardo-ai/sdk)
- [Sign Up](https://app.leonardo.ai/api-access)
- [Portal](https://app.leonardo.ai/)
- [Pricing](https://leonardo.ai/pricing/)
- [Blog](https://leonardo.ai/news/)
- [Press](https://leonardo.ai/news/supercharging-leonardo-with-canva/)
- [Press](https://www.canva.com/newsroom/news/leonardo-ai/)
- [Terms of Service](https://leonardo.ai/terms-of-service/)
- [Privacy Policy](https://leonardo.ai/privacy-policy/)
- [Acceptable Use Policy](https://leonardo.ai/legal/acceptable-use-policy/)
- [Support](https://intercom.help/leonardo-ai/)
- [Documentation](https://intercom.help/leonardo-ai/en/articles/8973587-api-reference-and-guides-for-developers)
- [LinkedIn](https://www.linkedin.com/company/leonardo-ai/)
- [X (Twitter)](https://x.com/LeonardoAi_)
- [Plans](plans/leonardo-ai-plans-pricing.yml)
- [Rate Limits](rate-limits/leonardo-ai-rate-limits.yml)
- [Fin Ops](finops/leonardo-ai-finops.yml)
- [Features](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
