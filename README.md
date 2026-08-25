# OpsPilot

AI-assisted customer support platform. Agents triage tickets faster with
LLM-generated summaries, structured analysis, and a natural-language copilot.

> 🚧 **Status:** Week 1 of 8 — product design phase. Not yet functional.

## Problem

Support agents lose most of their time on two things: reading long ticket
threads to rebuild context, and typing replies that follow the same handful
of patterns. OpsPilot targets both.

## Planned Features

- Ticket management — list, filter, search, assign, resolve
- Role-based access (Agent / Manager / Admin)
- AI ticket analysis — summary, category, priority, sentiment
- AI reply drafts (agent reviews and edits before sending)
- AI copilot with tool calling — query tickets in natural language

## Tech Stack

**Frontend** Next.js, TypeScript, Tailwind, shadcn/ui, TanStack Query, Zod
**Backend** Node.js, Express, TypeScript, JWT
**Database** PostgreSQL, Prisma
**AI** Structured output, tool calling
**Testing** Vitest, Supertest, Playwright

## Structure

    apps/frontend           Next.js app
    apps/backend            Express API
cat > .env.example << 'EOF'
# Database
DATABASE_URL="postgresql://postgres:postgres@localhost:5432/opspilot"

# Auth
JWT_ACCESS_SECRET="change-me"
JWT_REFRESH_SECRET="change-me-too"
ACCESS_TOKEN_TTL="15m"
REFRESH_TOKEN_TTL="7d"

# API
PORT=4000
CORS_ORIGIN="http://localhost:3000"

# Frontend
NEXT_PUBLIC_API_URL="http://localhost:4000"

# AI provider (Week 6)
AI_PROVIDER="gemini"
AI_API_KEY=""
