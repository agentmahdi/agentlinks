When creating Fastify API routes:
- Register as plugins with fastify.register()
- Use Zod type provider for request/response schemas
- Return consistent error objects: { error: string, statusCode: number }
- Use preHandler hooks for auth, not middleware
- Test with app.inject(), not supertest
