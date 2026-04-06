# Database Setup for Supabase

This project uses Supabase as the backend database. To make the project fully use your Supabase instance:

1. Open your Supabase project dashboard.
2. Go to `SQL Editor`.
3. Copy and run the SQL in `db/migrations/001_initial_schema.sql`.

This creates:
- `profiles`
- `devices`
- `telemetry`
- `commands`
- `device_pairing_sessions`
- `command_status` enum type
- row-level security policies
- realtime publication for the required tables

## After schema creation

- Confirm your tables appear under `Table Editor`.
- Confirm that `profiles` is linked to `auth.users`.
- Confirm `realtime` publication includes: `telemetry`, `commands`, `devices`, `device_pairing_sessions`.

## If you want a one-step deploy using Supabase CLI

```bash
supabase db push --project-ref zvhjdbyaejjytcdbzxec
```

> Only use the CLI if your Supabase project is already linked and you have the CLI installed.
