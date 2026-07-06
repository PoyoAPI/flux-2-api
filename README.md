# FLUX.2 API Examples for PoYo

[![Model page](https://img.shields.io/badge/Model%20page-flux--2-84cc16)](https://poyo.ai/models/flux-2)
[![API docs](https://img.shields.io/badge/API%20docs-docs.poyo.ai-22d3ee)](https://docs.poyo.ai/api-manual/image-series/flux-2)
[![License: MIT](https://img.shields.io/badge/License-MIT-111827)](LICENSE)
[![Main examples](https://img.shields.io/badge/Main%20examples-PoyoAPI%2Fpoyo--examples-0f172a?logo=github)](https://github.com/PoyoAPI/poyo-examples)

Focused server-side examples for building FLUX.2 image generation and editing workflows on PoYo.

FLUX.2 is useful for high-quality image generation, precise creative control, image editing, and production visual drafts that need pro or flex variants.

[Try on PoYo](https://poyo.ai/models/flux-2) | [Get API Key](https://poyo.ai/dashboard/api-key) | [Docs](https://docs.poyo.ai/api-manual/image-series/flux-2) | [Pricing](https://poyo.ai/pricing) | [Main Examples](https://github.com/PoyoAPI/poyo-examples)

## What This Repo Covers

- Text-to-image with `flux-2-pro`
- Edit paths with FLUX.2 edit variants
- Size and resolution controls
- Async task flow with polling and webhooks
- cURL and Node.js backend examples

## Quick Start

```bash
cp .env.example .env
export POYO_API_KEY="your-api-key"
```

Run the Node.js example:

```bash
cd node
npm start
```

Keep `POYO_API_KEY` on the server. Do not expose it in browser code, mobile apps, screenshots, or public logs.

## Production Pattern

- Keep `POYO_API_KEY` on the server
- Submit a generation task
- Store `data.task_id`
- Poll status while testing
- Use `callback_url` webhooks in production

## Models

This repo uses `flux-2-pro`, `flux-2-pro-edit`, `flux-2-flex`, `flux-2-flex-edit`.

## Examples

| Path | What it covers |
| --- | --- |
| [`curl/generate.md`](curl/generate.md) | Copy-paste async submit request. |
| [`node/`](node/) | Native Node.js backend example with polling. |
| [`docs/prompt-examples.md`](docs/prompt-examples.md) | Practical prompts for product workflows and creative tests. |
| [`docs/production-notes.md`](docs/production-notes.md) | Security and reliability notes before launch. |
| [`webhooks/express-webhook/`](webhooks/express-webhook/) | Minimal Express receiver for PoYo callbacks. |

## Run Checks

```bash
make check
```

On Windows:

```powershell
./scripts/check.ps1
```

## License

MIT
