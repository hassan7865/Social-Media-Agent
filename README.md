# Social Media Agent

AI-assisted social publishing product: FastAPI backend plus a Next.js dashboard for company setup, brand voice, posts, calendar, and analytics.

## Overview

Teams define company context and brand voice, connect platforms, generate and schedule posts, and review performance. The API uses LangChain with Groq for generation, Cloudinary for media, and a background loop that publishes due scheduled posts. Platform publishing is wired through a PostForMe integration and webhooks.

## Features

- Auth and company profile (industry, audience, messaging)
- Brand voice tones (professional, casual, friendly, and more)
- Platform connections and post composer with TipTap editing
- Content calendar (draft → approved → live) and scheduled publish loop
- AI generation jobs and analytics / post performance views
- Admin user routes and PostForMe webhook handling

## Stack

| Layer | Tech |
| --- | --- |
| API (`socialmediaagent-api`) | Python 3.11+, FastAPI, SQLAlchemy async, Alembic, PostgreSQL, LangChain + Groq, Cloudinary, httpx |
| UI (`socialmediaagent-ui`) | Next.js 16, React 19, TypeScript, TanStack Query, TipTap, Recharts, Axios, Tailwind CSS |

## Structure

```
socialmediaagent-api/   # FastAPI routers, services, models, migrations, tests
socialmediaagent-ui/    # Next.js App Router dashboard
```

UI dashboard areas: company, brand-voice, platforms, posts, calendar, jobs, analytics.

## How to run

### API

```bash
cd socialmediaagent-api
# Configure .env: DATABASE_URL, FRONTEND_URL, JWT settings, GROQ_API_KEY, etc.
uv sync
uv run alembic upgrade head
uv run uvicorn main:app --reload
```

### UI

```bash
cd socialmediaagent-ui
npm install
# NEXT_PUBLIC_API_URL=http://localhost:8000
npm run dev
```

Do not commit API keys, OAuth tokens, or `.env` files.
