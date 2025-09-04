# supabase-usage-watch

Environment variables (GitHub Actions Secrets) overview:

- SUPABASE_URL: Supabase project URL
- SUPABASE_SERVICE_ROLE_KEY: Service role key used to call PostgREST/RPC
- GMAIL_*: Gmail API credentials for sending mail
- DB_FREE_MB, ST_FREE_MB, MONTHLY_EGRESS_FREE_MB: Free tier caps for % calculations
- USAGE_SNAPSHOT_RETENTION_DAYS: Retention (days) for `usage_snapshots` table. Optional; defaults to 90.

Notes:
- The daily digest workflow optionally inserts one snapshot via `take_usage_snapshot` and then prunes rows in `usage_snapshots` older than `USAGE_SNAPSHOT_RETENTION_DAYS` using the Supabase REST API.
