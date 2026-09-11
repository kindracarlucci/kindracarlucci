Software Engineer building ingestion pipelines, schemas, and reliable worker systems.
## Iris Schaefer
I build data ingestion systems around queues, schemas, caches, and workers, with an emphasis on recoverable failures and bounded operational load.
I own the boundaries between upstream APIs, normalization pipelines, persistence, and downstream RPCs.
I prefer simple deployments, clear failure modes, and trade-offs that make recovery understandable under pressure.
### 🛠 Tech & Infrastructure
- **Core:** TypeScript, Node.js, Fastify
- **Data:** PostgreSQL, Kafka, Redis
- **Infra:** Docker, OpenTelemetry, GitHub Actions
- **Tooling:** Vitest, Docker Compose, jq
### ⚙️ Engineering Areas
- Idempotent ingestion with schema validation, queue replay, and replay-safe deduplication.
- Backpressure and bounded concurrency across RPC clients, workers, and database pools.
- Trace-based diagnosis of cross-service failures with structured logs and explicit spans.
- Versioned migrations for schemas, indexes, and queue payloads.
### 🔭 Current Focus
- Adding a compact dead-letter queue for poison messages without delaying healthy records.
- Moving hot lookup paths to Redis while retaining PostgreSQL as the source of truth.
- Testing migrations against large indexes without making rollout windows unpredictable.
- Measuring retry saturation before increasing backoff to avoid synchronized replay storms.
### 📌 Engineering Notes
- Tests should exercise queue ordering, duplicate delivery, and partial failures together.
- Boundaries belong at schemas, RPCs, and persistence; internal helpers should not invent more of them.
- Migrations need a rollback path, not only a forward path.
- Retry budgets and circuit breakers are error-handling requirements, not deployment polish.
### 🧭 How I Work
- Keep the common path small and make failure recovery explicit.
- Prefer measurable trade-offs over generalized abstractions.
- Document the assumptions that affect operations.
*Systems should fail in a way I can explain from the next morning.*
[Email](mailto:kindracarlucci@gmail.com)