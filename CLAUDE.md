# agentlinks

AI-powered link organizer. Paste a URL, AI summarizes it, auto-tags it, and organizes it. Generate weekly reading digests.

## Architecture

- Monorepo: apps/api (Fastify), apps/web (Next.js), packages/db (Drizzle), packages/shared (Zod schemas)
- Postgres 16 + pgvector for storage and semantic search
- Redis for caching, rate limiting, BullMQ job queue
- Claude API + Instructor for AI summarization and tagging
- Docker Compose for local dev

## Tech Stack

- TypeScript strict mode everywhere
- Fastify (not Express) for the API
- Drizzle ORM (not Prisma) for database
- Zod for validation (shared between API and frontend)
- Vitest for testing (not Jest)
- Pino for logging (structured JSON)

## Code Style

- Use async/await, never callbacks
- Use const over let, never var
- Explicit return types on all functions
- No any types — use unknown and narrow
- Errors as values where possible, throw only for unexpected failures
- Early returns over nested if/else

## API Conventions

- All routes under /api/v1/
- Fastify plugins for route groups
- Zod type provider for request/response validation
- Consistent error format: { error: string, statusCode: number }
- Use app.inject() for integration tests (no HTTP overhead)

## Database Conventions

- Drizzle schema in packages/db/src/schema.ts
- Migrations via drizzle-kit generate + migrate
- Use transactions for multi-table writes
- snake_case for column names, camelCase in TypeScript

## Testing

- Vitest for unit and integration tests
- Integration tests use real Postgres (not mocks)
- beforeEach truncates tables
- Test files next to source: thing.ts → thing.test.ts
