# Academy Piratemaxx

Learning platform: **Next.js** (`lms-app`) + **Express** + **MongoDB** (`lms-backend`), with Clerk, Stripe, Mux, and UploadThing.

**Basis:** [bemnet16/Learning-management-system](https://github.com/bemnet16/Learning-management-system). This repo tracks your product; use `git fetch upstream` / `git merge upstream/main` when you want upstream changes.

## Layout

| Path | Role |
|------|------|
| `lms-app/` | Next.js 13 UI and API routes |
| `lms-backend/` | REST API, Mongoose models |

## Prerequisites

- Node.js 18+
- MongoDB (local or Atlas)
- Clerk, Stripe, Mux, UploadThing accounts (as you enable features)

## Environment

Copy [.env.example](.env.example) and fill values. Use one file for backend (`lms-backend/.env`) and `lms-app/.env.local` for the Next app (see comments in `.env.example`).

## Run locally

**API (terminal 1)**

```bash
cd lms-backend
npm install
npm run dev
```

Set `URL` (Mongo connection string) and `PORT` in `lms-backend/.env`.

**App (terminal 2)**

```bash
cd lms-app
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000). Point `BACK_END_URL` at your API (e.g. `http://localhost:<PORT>`).

## Deploy

Host **frontend** and **backend** separately (e.g. Vercel + Railway). Set production URLs in env vars. Update backend CORS in `lms-backend/app.js`: replace `http://localhost:3000` with your real app origin.

## Upstream

```bash
git fetch upstream
git merge upstream/main
```

Resolve conflicts if any, then commit.
