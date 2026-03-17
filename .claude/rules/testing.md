When writing tests:
- Use Vitest, not Jest
- Integration tests connect to real Postgres in Docker
- Use beforeEach to truncate tables, not afterEach
- Test files live next to source: thing.ts → thing.test.ts
- Use app.inject() for API tests
- Assert on response status AND body
