# Supabase Functions Setup

This folder contains Supabase Edge Functions used by the web app.

## 1. Create the database schema

Open your Supabase project dashboard and go to `SQL Editor`.
Run the SQL from `db/migrations/001_initial_schema.sql`.

## 2. Configure service role key for functions

1. Create a file `apps/supabase/.env` from `.env.example`.
2. Set these values:
   - `SUPABASE_URL=https://zvhjdbyaejjytcdbzxec.supabase.co`
   - `SUPABASE_SERVICE_ROLE_KEY=<your-service-role-key>`

Get the service role key from Supabase Dashboard → Settings → API.

## 3. Deploy Edge Functions

Install the Supabase CLI and log in:

```bash
supabase login
```

Then deploy functions from the `apps/supabase` folder:

```bash
cd apps/supabase
supabase functions deploy create-pairing-session claim-device --project-ref zvhjdbyaejjytcdbzxec
```

If you need local testing, use:

```bash
supabase functions serve --project-ref zvhjdbyaejjytcdbzxec
```

## 4. Notes

- The functions require `SUPABASE_SERVICE_ROLE_KEY` to call secure Supabase APIs.
- Do not commit your `.env` file with the key.
- If you want, after deployment I can help verify the function endpoints.
