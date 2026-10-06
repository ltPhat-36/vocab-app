# Vocab Cloud — GitHub Pages

Upload/replace these items in the root of `ItPhat-36/vocab-app`:

- index.html
- manifest.json
- sw.js
- icons/

Then wait for GitHub Pages to redeploy.

## Supabase
The frontend contains ONLY the Supabase Publishable key.
Do NOT put any `sb_secret_...` or service-role key in this repository.

Required Supabase setup:
- GitHub provider enabled
- Site URL: https://itphat-36.github.io/vocab-app/
- Redirect URL: https://itphat-36.github.io/vocab-app/
- `public.vocab_sync` table + RLS policies already configured

## First login
Click `Đăng nhập GitHub`.
If cloud has no data yet, the current device's local progress becomes the initial cloud state.
After that, devices using the same GitHub account compare modification times and sync the newer state.

The app still saves locally first, so learning works offline. When the connection returns, it syncs again.
