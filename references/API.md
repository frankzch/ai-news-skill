# InBrief.info Feed API Reference

## Endpoint

```
GET https://inbrief.info/api/feed/
```

## Query Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `include_categories` | string | — | Comma-separated list of categories to include: `news`, `opensource`, `discussion`, `kol` |
| `exclude_categories` | string | — | Comma-separated list of categories to exclude |
| `include_sources` | string | — | Comma-separated list of sources to include |
| `exclude_sources` | string | — | Comma-separated list of sources to exclude |
| `hours` | int | 24 | Time window in hours |
| `limit` | int | — | Optional cap on the total number of items (max 200) |
| `lang` | string | `zh` | Response language: `en` or `zh` |
| `api_key` | string | — | PulseAI API Key from InBrief.info → Settings; determines the tier |

> **Note:** `include_*` takes precedence over `exclude_*` for the same dimension.

### Tier caps (per category)

| Tier | Who | Items per category |
|------|-----|--------------------|
| `guest` | no / invalid `api_key` | top 5 |
| `free` | logged-in, non-member | top 10 |
| `member` | active member | all |

Within each category, items are ranked by importance score, then recency.

## Response Schema

```json
{
  "status": "success",
  "tier": "guest | free | member",
  "tier_limit": 5,
  "count": 20,
  "articles": [
    {
      "title": "Article title",
      "summary": "Short one-line summary",
      "long_summary": "Detailed multi-paragraph summary",
      "category": "news | opensource | discussion | kol",
      "source": "Source platform name (e.g. TechCrunch, Reddit, GitHub)",
      "url": "https://original-article-url.com/...",
      "published_at": "2026-04-07T12:00:00Z"
    }
  ]
}
```

## Error Responses

| Status | Meaning |
|--------|---------|
| 429 | IP rate limit exceeded (anti-spam interval or daily quota). Wait and retry. |
| 5xx | Server error. Retry after a short delay. |

### 429 Response Body

```json
{
  "detail": "Rate limit exceeded. Please wait before making another request."
}
```

## Rate Limiting

- **No API key required** (an API key only raises the per-category tier cap). Rate limits are applied per IP address.
- Two layers: immediate anti-spam interval and daily request quota.
- If rate-limited, the response includes a descriptive `detail` message.
