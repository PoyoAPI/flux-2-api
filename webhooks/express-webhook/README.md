# FLUX.2 API Express Webhook Receiver

This is a minimal webhook receiver for PoYo async generation callbacks.

```bash
cp ../../.env.example ../../.env
npm install
npm start
```

Set `POYO_CALLBACK_URL` in your submit request to your public webhook URL, for example:

```text
https://example.com/api/poyo/webhook
```

Production notes:

- Accept only task IDs your system created.
- Reconcile callback status by calling `/api/generate/status/{task_id}`.
- Make callback handling idempotent.
- Keep `POYO_API_KEY` on the server.
