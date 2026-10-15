# AWS Management Dashboard

Simple, clean, minimal AWS dashboard that translates technical AWS metrics into plain-English insights for management.

## Screens

- `/` Overview — spend, forecast, health, top attention items
- `/billing` — spend by service, budget bar, plain-English breakdown
- `/resources` — EC2 / RDS / S3 inventory with search, filter, inline rename (demo)
- `/resources/[id]` — CPU, RAM, storage utilization + recommendation
- `/users` — IAM users in plain words, MFA + stale access risks
- `/monitoring` — CloudWatch simplified to 4 decision charts
- `/alerts` — High usage vs Normal alerts with recommended actions

## Run

```bash
npm install
npm run dev
```

Open http://localhost:3003 (port is pinned in the `dev` script — always 3003).

## Mock-first

All data lives in `lib/mock-data.ts`. Insight rules (jargon → English) live in `lib/insights.ts`.
Swap the mock module for AWS SDK adapters later (Cost Explorer, CloudWatch, IAM) without changing the UI.

## Notes

- Rename on Resources is a local demo. Live mapping: EC2 Name tag, RDS instance identifier; S3 buckets cannot be renamed (app will suggest new-bucket flow).
- No AWS credentials needed for v1.
