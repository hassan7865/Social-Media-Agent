# SocialMediaAgent

AI social media agent with a Python API and a Next.js UI.

## Overview

SocialMediaAgent supports AI-assisted social media workflows — content/agent logic on the API side and a dashboard on the UI side.

## Stack

- **API** (`socialmediaagent-api`): Python, Alembic, PostgreSQL
- **UI** (`socialmediaagent-ui`): Next.js, React, TypeScript

## Structure

```
socialmediaagent-api/   # Backend API, models, routers, services, tests
socialmediaagent-ui/    # Next.js frontend
```

## Getting started

### API

```bash
cd socialmediaagent-api
# Install deps from pyproject.toml
# Set database and provider credentials via env
# Run migrations, then start the API
```

### UI

```bash
cd socialmediaagent-ui
npm install
npm run dev
```

## Notes

Do not commit API keys, OAuth tokens, or `.env` files.
