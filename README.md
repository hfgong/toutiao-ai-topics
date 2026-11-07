# toutiao-ai-topics

Daily AI hot topics from the Toutiao hot board, as a machine-readable CSV.
Dates are Beijing dates. Updated every 12 hours.

## For a Raspberry Pi (or anything with curl)

```sh
curl -s https://raw.githubusercontent.com/hfgong/toutiao-ai-topics/main/toutiao_ai_latest.csv -o toutiao_ai_latest.csv
```

No login, no key — the repo is public.

## Files

- `toutiao_ai_latest.csv` — latest day's AI topics (one row per topic).
- `README.md` — this file.

## Columns

| column | meaning |
|---|---|
| `date` | Beijing date (YYYY-MM-DD) |
| `title` | hot-board title |
| `categories` | keyword category, e.g. 大模型 / 机器人 / 芯片算力 / AI应用 |
| `ai_score` | keyword match score |
| `peak_hot_wan` | peak HotValue that day, in 万 (10k) |
| `best_rank` | best hot-board rank that day (#1 = top) |
| `snapshots_seen` | how many 3-hour snapshots the topic appeared in (persistence) |
| `first_seen` / `last_seen` | first / last snapshot timestamps (Beijing time, +08:00) |
| `url` | Toutiao trending link |

## Source

Toutiao hot-board API (`hot-event/hot-board`), sampled every 3 hours and
aggregated daily by topic. Rows are keyword-scored candidates, not the
semantically reviewed digest.
