# FLUX.2 API cURL Quickstart

Submit a backend-safe async generation task. Keep `POYO_API_KEY` out of browser code.

```bash
export POYO_API_KEY="YOUR_POYO_API_KEY_HERE"

curl https://api.poyo.ai/api/generate/submit \
  -H "Authorization: Bearer $POYO_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "model": "flux-2-pro",
  "input": {
    "prompt": "High-end editorial product photo of a compact translucent desk speaker on a clean workspace, precise reflections, realistic shadows, no text, no logo, no watermark.",
    "size": "16:9",
    "resolution": "1K"
  }
}'
```

The submit response includes `data.task_id`. Store that value, then poll while testing:

```bash
curl https://api.poyo.ai/api/generate/status/TASK_ID_FROM_SUBMIT \
  -H "Authorization: Bearer $POYO_API_KEY"
```

For production, pass `callback_url` in the submit payload and handle webhooks on your server.

Model page: https://poyo.ai/models/flux-2
