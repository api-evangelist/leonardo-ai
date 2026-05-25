# Leonardo.AI (leonardo-ai)
Leonardo.AI is an Australian generative-AI company (acquired by Canva in July 2024) offering a Production API for AI image generation, video generation, 3D model creation, custom model and element training, realtime canvas editing, upscaling and variations, and Blueprint workflow execution. The platform supports in-house Leonardo models (Phoenix, Lucid Origin, Lucid Realism) and third-party models (FLUX.1/FLUX.2, Ideogram 3.0, GPT Image, Nano Banana, Seedream, Kling, LTX, Veo, Seedance, Hailuo, Rodin) under a unified pay-as-you-go dollar-denominated API surface with webhook callbacks, MCP server integration, and official Python and TypeScript SDKs.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/leonardo-ai/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

- AI, Artificial Intelligence, Image Generation, Video Generation, Generative AI, Creative, 3D, Diffusion, Canva

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## Quick Facts

| | |
|---|---|
| Base URL | `https://cloud.leonardo.ai/api/rest/v1` |
| Auth | HTTP Bearer (Production API key) |
| Auth headers | `Authorization: Bearer <api_key>`, `accept: application/json`, `content-type: application/json` |
| API key dashboard | https://app.leonardo.ai/api-access |
| Max keys per account | 10 |
| Billing | Pay-As-You-Go in USD, prepaid balance, manual or auto top-up |
| Concurrency | Per-key concurrency limit + queue (no public RPM/TPM ceiling) |
| Async pattern | POST → job id → webhook callback (preferred) or GET-poll |
| Official SDKs | Python ([repo](https://github.com/Leonardo-Interactive/leonardo-python-sdk)), TypeScript ([repo](https://github.com/Leonardo-Interactive/leonardo-ts-sdk)) |
| MCP server | https://docs.leonardo.ai/docs/mcp-server |
| llms.txt | https://docs.leonardo.ai/llms.txt |
| Acquired by | Canva (July 2024) |

## Models (selected)

| Family | Examples | Modality | Provider |
|---|---|---|---|
| Phoenix | Phoenix | Image | Leonardo (in-house) |
| Lucid | Lucid Origin, Lucid Realism | Image | Leonardo (in-house) |
| FLUX | FLUX.1 Kontext, FLUX.2 Pro, FLUX Dev, FLUX Schnell | Image | Black Forest Labs |
| Ideogram | Ideogram 3.0 | Image | Ideogram |
| GPT Image | GPT Image 1.5, GPT Image 2 | Image | OpenAI |
| Nano Banana | Nano Banana variants | Image | Third party |
| Seedream | Seedream variants | Image | ByteDance |
| Kling | Kling 2.1 Pro, 2.5 Turbo, 2.6, 3.0, O1, O3 | Video | Kuaishou |
| LTX | LTX 2.0, LTX 2.3 | Video | Lightricks |
| Veo | Veo 3.0, Veo 3.1 | Video | Google |
| Seedance | Seedance variants | Video | ByteDance |
| Hailuo | Hailuo 2.3 | Video | MiniMax |
| Rodin | Rodin V2 | 3D | Hyper3D |
| SVD | Stable Video Diffusion | Video | Stability AI |

Use `GET /platformModels` for the live catalog of usable model UUIDs.

## APIs

### Leonardo.AI Image Generation API
Create image generations with FLUX, Phoenix, Lucid, Ideogram, GPT Image, Nano Banana, Seedream, and other supported models. Supports PhotoReal, Alchemy, image prompts, image guidance (ControlNet), enhanced prompts, transparency, and per-model knobs.

**Human URL:** [https://docs.leonardo.ai/reference/creategeneration](https://docs.leonardo.ai/reference/creategeneration)

- [Documentation](https://docs.leonardo.ai/reference/creategeneration)
- [OpenAPI](openapi/leonardo-ai-image-generation-openapi.json)
- [JSON Schema — Generation](json-schema/leonardo-ai-generation-schema.json)
- [JSON-LD](json-ld/leonardo-ai-context.jsonld)
- [Naftiko Capability — Image Generation](capabilities/image-generation.yaml)

### Leonardo.AI Video Generation API
Generate videos from text or images using Kling, LTX, Veo, Seedance, Hailuo, and Stable Video Diffusion motion models. Image-to-video, text-to-video, and SVD motion endpoints.

**Human URL:** [https://docs.leonardo.ai/reference/createimagetovideogeneration](https://docs.leonardo.ai/reference/createimagetovideogeneration)

- [OpenAPI](openapi/leonardo-ai-video-generation-openapi.json)
- [Naftiko Capability — Video Generation](capabilities/video-generation.yaml)

### Leonardo.AI Variation and Upscale API
Apply variations: unzoom (outpainting), creative upscale, background removal, and Universal Upscaler. Retrieve variation job status by ID.

**Human URL:** [https://docs.leonardo.ai/reference/createvariationupscale](https://docs.leonardo.ai/reference/createvariationupscale)

- [OpenAPI](openapi/leonardo-ai-variation-openapi.json)
- [Naftiko Capability — Variation](capabilities/variation.yaml)

### Leonardo.AI Realtime Canvas API
Real-time LCM endpoints for sub-second iterative generation, inpainting, instant refine, and Alchemy upscale.

**Human URL:** [https://docs.leonardo.ai/reference/createlcmgeneration](https://docs.leonardo.ai/reference/createlcmgeneration)

- [OpenAPI](openapi/leonardo-ai-realtime-canvas-openapi.json)
- [Naftiko Capability — Realtime Canvas](capabilities/realtime-canvas.yaml)

### Leonardo.AI Models API
List Leonardo platform models and manage custom fine-tuned models for users.

**Human URL:** [https://docs.leonardo.ai/reference/getplatformmodels](https://docs.leonardo.ai/reference/getplatformmodels)

- [OpenAPI](openapi/leonardo-ai-models-openapi.json)
- [JSON Schema — Model](json-schema/leonardo-ai-model-schema.json)
- [Naftiko Capability — Models](capabilities/models.yaml)

### Leonardo.AI Elements API
Create and manage Custom Elements — LoRA-style style adapters trainable on user datasets and reusable across image generations.

**Human URL:** [https://docs.leonardo.ai/reference/createelement](https://docs.leonardo.ai/reference/createelement)

- [OpenAPI](openapi/leonardo-ai-elements-openapi.json)
- [Naftiko Capability — Elements](capabilities/elements.yaml)

### Leonardo.AI Datasets API
Create, upload to, and delete training datasets used for custom models and elements.

**Human URL:** [https://docs.leonardo.ai/reference/createdataset](https://docs.leonardo.ai/reference/createdataset)

- [OpenAPI](openapi/leonardo-ai-datasets-openapi.json)
- [Naftiko Capability — Datasets](capabilities/datasets.yaml)

### Leonardo.AI Init Images API
Upload, retrieve, and delete init images used for image-to-image, image-prompt, canvas, and image-guidance workflows.

**Human URL:** [https://docs.leonardo.ai/reference/uploadinitimage](https://docs.leonardo.ai/reference/uploadinitimage)

- [OpenAPI](openapi/leonardo-ai-init-images-openapi.json)
- [Naftiko Capability — Init Images](capabilities/init-images.yaml)

### Leonardo.AI Media API
Upload, retrieve, and delete general-purpose media used across generation endpoints.

**Human URL:** [https://docs.leonardo.ai/reference/uploadmedia](https://docs.leonardo.ai/reference/uploadmedia)

- [OpenAPI](openapi/leonardo-ai-media-openapi.json)
- [Naftiko Capability — Media](capabilities/media.yaml)

### Leonardo.AI 3D Model Assets API
Upload, retrieve, and delete 3D model assets used with Rodin V2 and other 3D-capable workflows.

**Human URL:** [https://docs.leonardo.ai/reference/upload3dmodelasset](https://docs.leonardo.ai/reference/upload3dmodelasset)

- [OpenAPI](openapi/leonardo-ai-3d-model-assets-openapi.json)
- [Naftiko Capability — 3D Model Assets](capabilities/3d-model-assets.yaml)

### Leonardo.AI Blueprints API
Execute Leonardo Blueprints — pre-packaged multi-step image and video workflows — and retrieve executions, generations, and version history.

**Human URL:** [https://docs.leonardo.ai/reference/listblueprints](https://docs.leonardo.ai/reference/listblueprints)

- [OpenAPI](openapi/leonardo-ai-blueprints-openapi.json)
- [Naftiko Capability — Blueprints](capabilities/blueprints.yaml)

### Leonardo.AI Prompt API
Improve user-supplied prompts and generate random prompts.

**Human URL:** [https://docs.leonardo.ai/reference/promptimprove](https://docs.leonardo.ai/reference/promptimprove)

- [OpenAPI](openapi/leonardo-ai-prompt-openapi.json)
- [Naftiko Capability — Prompt](capabilities/prompt.yaml)

### Leonardo.AI Pricing Calculator API
Pre-calculate the API credit cost (in USD) of a generation request before submitting it.

**Human URL:** [https://docs.leonardo.ai/reference/pricingcalculator](https://docs.leonardo.ai/reference/pricingcalculator)

- [OpenAPI](openapi/leonardo-ai-pricing-calculator-openapi.json)
- [Naftiko Capability — Pricing Calculator](capabilities/pricing-calculator.yaml)

### Leonardo.AI User API
Retrieve the authenticated user's profile, subscription info, and remaining API credit balance via GET `/me`.

**Human URL:** [https://docs.leonardo.ai/reference/getuserself](https://docs.leonardo.ai/reference/getuserself)

- [OpenAPI](openapi/leonardo-ai-user-openapi.json)
- [Naftiko Capability — User](capabilities/user.yaml)

## Common Properties

- [Portal — leonardo.ai](https://leonardo.ai)
- [Portal — Leonardo.AI API](https://leonardo.ai/api)
- [Documentation — docs.leonardo.ai](https://docs.leonardo.ai/)
- [Documentation — API Reference](https://docs.leonardo.ai/reference)
- [GettingStarted — Quick Start Guide](https://docs.leonardo.ai/docs/getting-started)
- [llms.txt index](https://docs.leonardo.ai/llms.txt)
- [Documentation — API FAQ](https://docs.leonardo.ai/docs/api-faq)
- [Errors — API Error Messages](https://docs.leonardo.ai/docs/api-error-messages)
- [RateLimits — Concurrency, Queue, and Rate Limiting](https://docs.leonardo.ai/docs/concurrency-rate-limits-and-queue)
- [Webhooks — Webhook Callback Feature](https://docs.leonardo.ai/docs/webhook-callback-feature)
- [Pricing — Pay-As-You-Go (PAYG) Guide](https://docs.leonardo.ai/docs/payg-guide)
- [Pricing — Pricing Calculator Guide](https://docs.leonardo.ai/docs/plan-with-the-pricing-calculator)
- [Pricing](https://leonardo.ai/pricing/)
- [SDK — Official SDKs index](https://docs.leonardo.ai/docs/leonardoai-official-sdks)
- [Documentation — MCP Server](https://docs.leonardo.ai/docs/mcp-server)
- [Documentation — NSFW Handling](https://docs.leonardo.ai/docs/nsfw-handling)
- [GitHubOrganization](https://github.com/Leonardo-Interactive)
- [SDK — Python](https://github.com/Leonardo-Interactive/leonardo-python-sdk)
- [SDK — TypeScript](https://github.com/Leonardo-Interactive/leonardo-ts-sdk)
- [SDK — PyPI leonardoai](https://pypi.org/project/leonardoai/)
- [SDK — npm @leonardo-ai/sdk](https://www.npmjs.com/package/@leonardo-ai/sdk)
- [Tool — agent-browser](https://github.com/Leonardo-Interactive/agent-browser)
- [Tool — background-removal-js](https://github.com/Leonardo-Interactive/background-removal-js)
- [Plugins — Blender Texturing Plugin](https://github.com/Leonardo-Interactive/leonardo-texturing-blender-plugin)
- [SignUp — API Access Dashboard](https://app.leonardo.ai/api-access)
- [Portal — Leonardo App](https://app.leonardo.ai/)
- [Blog — News](https://leonardo.ai/news/)
- [Press — Joining Canva](https://leonardo.ai/news/supercharging-leonardo-with-canva/)
- [Press — Welcome to Canva, Leonardo!](https://www.canva.com/newsroom/news/leonardo-ai/)
- [TermsOfService](https://leonardo.ai/terms-of-service/)
- [PrivacyPolicy](https://leonardo.ai/privacy-policy/)
- [AcceptableUsePolicy](https://leonardo.ai/legal/acceptable-use-policy/)
- [Support — Help Center](https://intercom.help/leonardo-ai/)
- [LinkedIn](https://www.linkedin.com/company/leonardo-ai/)
- [X](https://x.com/LeonardoAi_)

## Artifacts

Machine-readable API specifications organized by format.

### OpenAPI

- [Leonardo.AI Image Generation API](openapi/leonardo-ai-image-generation-openapi.json)
- [Leonardo.AI Video Generation API](openapi/leonardo-ai-video-generation-openapi.json)
- [Leonardo.AI Variation and Upscale API](openapi/leonardo-ai-variation-openapi.json)
- [Leonardo.AI Realtime Canvas API](openapi/leonardo-ai-realtime-canvas-openapi.json)
- [Leonardo.AI Models API](openapi/leonardo-ai-models-openapi.json)
- [Leonardo.AI Elements API](openapi/leonardo-ai-elements-openapi.json)
- [Leonardo.AI Datasets API](openapi/leonardo-ai-datasets-openapi.json)
- [Leonardo.AI Init Images API](openapi/leonardo-ai-init-images-openapi.json)
- [Leonardo.AI Media API](openapi/leonardo-ai-media-openapi.json)
- [Leonardo.AI 3D Model Assets API](openapi/leonardo-ai-3d-model-assets-openapi.json)
- [Leonardo.AI Blueprints API](openapi/leonardo-ai-blueprints-openapi.json)
- [Leonardo.AI Prompt API](openapi/leonardo-ai-prompt-openapi.json)
- [Leonardo.AI Pricing Calculator API](openapi/leonardo-ai-pricing-calculator-openapi.json)
- [Leonardo.AI User API](openapi/leonardo-ai-user-openapi.json)

### JSON Schema

- [Leonardo.AI Generation Schema](json-schema/leonardo-ai-generation-schema.json)
- [Leonardo.AI Model Schema](json-schema/leonardo-ai-model-schema.json)

### JSON Structure

- [Leonardo.AI Generation Structure](json-structure/leonardo-ai-generation-structure.json)

### JSON-LD

- [Leonardo.AI Context](json-ld/leonardo-ai-context.jsonld)

### Capabilities (Naftiko)

- [Image Generation](capabilities/image-generation.yaml)
- [Video Generation](capabilities/video-generation.yaml)
- [Variation and Upscale](capabilities/variation.yaml)
- [Realtime Canvas](capabilities/realtime-canvas.yaml)
- [Models](capabilities/models.yaml)
- [Elements](capabilities/elements.yaml)
- [Datasets](capabilities/datasets.yaml)
- [Init Images](capabilities/init-images.yaml)
- [Media](capabilities/media.yaml)
- [3D Model Assets](capabilities/3d-model-assets.yaml)
- [Blueprints](capabilities/blueprints.yaml)
- [Prompt](capabilities/prompt.yaml)
- [Pricing Calculator](capabilities/pricing-calculator.yaml)
- [User](capabilities/user.yaml)

### Spectral Rules

- [Leonardo.AI Spectral Ruleset](rules/leonardo-ai-rules.yml)

### Vocabulary

- [Leonardo.AI Vocabulary](vocabulary/leonardo-ai-vocabulary.yml)

### Plans, Rate Limits, and FinOps

- [Plans & Pricing (API Commons Plans)](plans/leonardo-ai-plans-pricing.yml)
- [Rate Limits (API Commons Rate Limits)](rate-limits/leonardo-ai-rate-limits.yml)
- [FinOps (FOCUS-aligned)](finops/leonardo-ai-finops.yml)

### Examples

- [Create Generation](examples/leonardo-ai-create-generation-example.json)
- [Get Generation](examples/leonardo-ai-get-generation-example.json)
- [Image-to-Video](examples/leonardo-ai-image-to-video-example.json)
- [Pricing Calculator](examples/leonardo-ai-pricing-calculator-example.json)
- [Get Authenticated User (/me)](examples/leonardo-ai-me-example.json)
