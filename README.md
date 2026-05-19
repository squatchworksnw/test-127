# MOW Facilities Command

A mobile-first operations command center for facilities, fleet, work orders, documents, review intake, and contractor workflows.

The app is intentionally static on the frontend and uses Supabase as the source of truth.

## Pilot Status

This repository is prepared for controlled pilot testing, not broad production rollout.

Start here:

- `LIVE_PILOT_DEPLOYMENT_STEPS.md`
- `PILOT_TEST_CHECKLIST.md`
- `SECURITY_TRUST_REVIEW.md`
- `sql/rls_verification.sql`

## GitHub Pages Runtime Files

The live app is served from:

- `index.html`
- `styles.css`
- `app.js`
- `auth/`
- `components/`
- `data/`
- `services/`
- `state/`
- `styles/`
- `sync/`
- `views/`

Do not publish local scratch folders or secret files.

## Folder Structure

- `auth/`, `components/`, `services/`, `state/`, `sync/`, `views/`: active app code.
- `data/`: bundled import preview data, including the controlled master calendar bundle.
- `styles/` and `styles.css`: active visual system.
- `sql/`: Supabase setup, verification, and policy scripts.
- `tests/`: local QA and architecture checks.
- `docs/`: planning, audit, and architecture notes.
- `dist/`: generated upload zips.
- `archive/`: older generated builds kept for safety. Do not upload this folder to GitHub Pages.

## Supabase

Supabase remains the source of truth.

- Frontend code may contain the public publishable/anon key.
- Never commit a Supabase service-role key.
- Browser storage is only for temporary pending retry state, not as the database.
- Run `sql/rls_verification.sql` before live pilot testing.

## Deployment

1. Upload this app to a GitHub repository.
2. In GitHub, open Settings > Pages.
3. Set Source to `Deploy from a branch`.
4. Select the main branch and root folder.
5. Save.
6. Add the GitHub Pages URL to Supabase Auth redirect URLs.
7. Follow `LIVE_PILOT_DEPLOYMENT_STEPS.md`.

