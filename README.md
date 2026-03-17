# agentlinks

Paste links, AI handles the rest — summarize, tag, organize, and generate weekly reading digests.

## Stack

- **API:** Fastify + TypeScript
- **Frontend:** Next.js + Tailwind + shadcn/ui
- **Database:** Postgres + Drizzle ORM + pgvector
- **AI:** Claude API + Instructor
- **Queue:** BullMQ + Redis
- **Auth:** WorkOS
- **Payments:** Stripe
- **Deploy:** AWS ECS (API) + Vercel (frontend) + Cloudflare (DNS/CDN)

## Development
```bash
docker compose up
```

## License

MIT
