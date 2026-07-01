# 6-Month Syllabus — Advance Dev + DevOps

Structure: Alternate days (Day A = Advance Dev, Day B = DevOps), DSA every day (separate, not in this doc).
6 months ≈ 26 weeks ≈ 13 Day-A sessions/month + 13 Day-B sessions/month.

Each phase below is meant to span roughly 3-4 weeks of alternate-day sessions. Adjust pace based on how deep you go — better to run over than rush.

---

## TRACK 1: ADVANCE DEV CONCEPTS

### Phase 1 — Concurrency & Systems Foundations (Weeks 1-4)
**Goal:** Be able to reason about concurrent code, not just write it.

- Go concurrency primitives: goroutines, channels (buffered/unbuffered), select
- sync package: Mutex, RWMutex, WaitGroup, Once
- context package: cancellation, timeouts, propagation
- Race conditions — detect with `go run -race`, understand why they happen
- Deadlocks — classic causes, how to avoid
- Memory models — happens-before relationship (conceptual)
- **Applied:** Refactor a part of your Redis clone or auth system to use goroutines/channels properly (e.g. concurrent connection handling)

### Phase 2 — Database Internals (Weeks 5-8)
**Goal:** Answer "why is this query slow" and "why did we pick this DB" with real reasoning.

- Indexing: B-tree vs LSM-tree, when each wins
- Transaction isolation levels (Read Uncommitted → Serializable) + what anomalies each prevents
- MVCC — how Postgres does it
- Query optimization — reading EXPLAIN/EXPLAIN ANALYZE output
- Connection pooling — why it matters, pool sizing tradeoffs
- N+1 query problem — spotting and fixing (relevant to your Prisma/Chamber schema)
- Redis internals: data structures (skip lists, hash tables), persistence (RDB vs AOF), eviction policies
- **Applied:** Run EXPLAIN ANALYZE on a query from your car-rental or Chamber project, optimize it

### Phase 3 — Distributed Systems (Weeks 9-12)
**Goal:** Understand tradeoffs well enough to defend a design decision in an interview.

- CAP theorem — not just the triangle, but real examples of what breaks
- Consistency models: strong, eventual, causal
- Replication: leader-follower vs leaderless, sync vs async replication
- Partitioning/sharding strategies (range, hash, consistent hashing)
- Consensus (conceptual): Raft — leader election, log replication
- Idempotency — why it matters, idempotency keys
- Delivery guarantees: at-least-once, at-most-once, exactly-once
- Distributed locking, leader election basics

### Phase 4 — API & Backend Design (Weeks 13-15)
**Goal:** Design APIs that don't fall over in production.

- REST vs gRPC vs GraphQL — real tradeoffs, not syntax
- Rate limiting algorithms: token bucket, leaky bucket, sliding window
- Caching strategies: cache-aside, write-through, write-behind + invalidation problems
- Auth patterns beyond basic JWT: OAuth2 flows, refresh token rotation, session vs token tradeoffs
- Webhooks — design and reliability (retries, signature verification)
- **Applied:** Add refresh token rotation + rate limiting to your MERN+TS auth system

### Phase 5 — Message Queues & Event-Driven Architecture (Weeks 16-18)
- Kafka: topics, partitions, consumer groups, offsets
- RabbitMQ: exchanges, queues, routing keys
- When to use event-driven vs request-response
- Dead letter queues, retry/backoff strategies
- **Applied:** Prototype a small pub/sub feature (even a toy notification system)

### Phase 6 — Microservices & Resilience Patterns (Weeks 19-21)
- Service discovery, API gateway pattern
- Saga pattern for distributed transactions
- Circuit breakers, bulkheads, timeouts
- Monolith vs microservices — when NOT to split (interview favorite)

### Phase 7 — Security (Weeks 22-23)
- OWASP Top 10 — each one, with a code-level example
- SQLi, XSS, CSRF — prevention at the code level
- Password hashing: bcrypt/argon2 — why, mechanics
- CORS — what it protects, common misconfig
- **Applied:** Security-audit your own auth system against this list

### Phase 8 — System Design Practice (Weeks 24-26)
**Goal:** Convert Phases 1-7 into interview-ready design skill.

- HLD: URL shortener, rate limiter, notification system, chat app, news feed, job scheduler (pick 5-6, go deep)
- LLD: SOLID principles applied, design patterns (Factory, Strategy, Observer, Builder, Singleton)
- Practice explaining designs out loud — record yourself or explain to me

### Testing (weave throughout, not a separate phase)
- Unit vs integration vs e2e — what to test where
- Mocking DB/external services
- Load testing basics (k6 or Apache Bench)
- Apply testing to whichever project you're working on that month

---

## TRACK 2: DEVOPS

### Phase 1 — Docker Deep Dive (Weeks 1-4)
**Goal:** Actually comfortable with Docker, not just `docker run`.

- Images vs containers, layers, caching
- Writing efficient Dockerfiles — multi-stage builds
- Docker Compose — multi-service local setups (e.g. your app + Postgres + Redis together)
- Image size optimization, distroless/alpine images
- Non-root containers, basic container security principles
- **Applied:** Dockerize your auth system (app + Redis + Postgres) with Compose

### Phase 2 — Networking Fundamentals (Weeks 5-7)
- TCP/IP basics — build on your TCP Echo Server project
- HTTP/HTTPS, TLS handshake (conceptual)
- DNS resolution flow
- Reverse proxy vs load balancer vs API gateway — the distinction
- Nginx basics — config for reverse proxy + static serving

### Phase 3 — CI/CD (Weeks 8-11)
**Goal:** Ship changes safely and automatically — directly reusable for Devium Builds clients.

- GitHub Actions — workflows, jobs, secrets
- Build → test → deploy pipeline design
- Environment management: dev/staging/prod config separation
- Secrets management basics
- **Applied:** Set up a real CI/CD pipeline for Devium or a client project (lint + test + deploy on push)

### Phase 4 — Cloud & Infra Basics (Weeks 12-15)
- Core AWS/GCP services: compute (EC2), storage (S3), managed DB (RDS)
- Load balancers in the cloud context
- Environment variables & secrets management in production
- Basic cost-awareness (what makes cloud bills explode)

### Phase 5 — Infrastructure as Code (Weeks 16-18)
**Goal:** Write real Terraform, not just know the word.

- Terraform basics: providers, resources, state
- Write a small Terraform config to provision something you'd actually use (e.g. an EC2 instance + security group)
- Config management concepts (Ansible — conceptual)

### Phase 6 — Observability (Weeks 19-21)
- Structured logging — what to log, what not to
- Health checks: liveness vs readiness probes
- Basic monitoring/alerting: Prometheus + Grafana (conceptual, hands-on if time permits)
- Debugging production issues from logs/metrics (mental model)

### Phase 7 — Orchestration Basics (Weeks 22-24)
- Kubernetes conceptually: pods, deployments, services, ingress
- Why K8s exists (the problems it solves vs plain Docker)
- Not aiming for hands-on mastery — aim to speak to it intelligently

### Phase 8 — Deployment Strategies & GitOps (Weeks 25-26)
- Zero-downtime deployment: blue-green, rolling updates
- GitOps concept (ArgoCD/Flux) — git as source of truth for infra
- Tie together: deploy one of your projects end-to-end using what you've learned (Docker + CI/CD + cloud)

---

## Priority Cut Line (if time gets tight)

**Must go deep (interview + real-world critical):**
Concurrency, DB internals, distributed systems fundamentals, API design, security, Docker, CI/CD, networking

**Conceptual-is-enough (know it, don't need to master it):**
Kubernetes, Terraform (beyond basics), Ansible, Kafka internals (understand, don't need to run a cluster)

---

## How to use this doc
- Pick current phase from each track, tell me which one you're starting
- I'll do first-pass deep dives, quiz you, or review your applied work — your call each session
- Re-order phases if a job description or interview loop points you somewhere specific — this isn't fixed in stone
