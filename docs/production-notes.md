# FLUX.2 API Production Notes

## API Key Safety

- Keep `POYO_API_KEY` on the server.
- Do not place API keys in browser JavaScript, mobile apps, screenshots, analytics, or client logs.
- Store production keys in a secret manager or server environment variables.

## Request Handling

- Validate user input before sending it to PoYo.
- Log model, request type, status, latency, and task outcome.
- Retry network failures with backoff.
- Do not blindly retry model failures without reading the error reason.

## Async Reliability

- Save `data.task_id` immediately after submit.
- Poll status while testing.
- Use `callback_url` webhooks in production.
- Treat failed tasks as inspectable states, not silent errors.
- Retrieve final files from the status response only after the task is finished.

## Cost Controls

- Start with the lowest-cost model path that can answer the product question.
- Promote to higher-quality variants only when the workflow needs it.
- Track usable outputs, failed tasks, retries, and manual cleanup time.

## Links

- Model page: https://poyo.ai/models/flux-2
- API docs: https://docs.poyo.ai/api-manual/image-series/flux-2
