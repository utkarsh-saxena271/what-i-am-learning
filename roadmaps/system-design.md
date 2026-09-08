# 🧠 SYSTEM DESIGN ROADMAP

```text
                         SYSTEM DESIGN
                              │
                ┌─────────────┴─────────────┐
                │                           │
               LLD                         HLD
                │                           │
        Code-level design            System-level design
                │                           │
        ┌───────┴───────┐           ┌───────┴────────┐
        │               │           │                │
       OOP            SOLID      Fundamentals   Distributed Systems
        │               │           │                │
        └───────┬───────┘           └────────┬───────┘
                │                            │
         Design Patterns              Scalability
                │                    Databases
                │                    Caching
                │                    Messaging
                │                    Reliability
                │                    Observability
                │                            │
                └────────────┬───────────────┘
                             │
                      SYSTEM CASE STUDIES
                             │
                    ┌────────┴─────────┐
                    │                  │
                   HLD                LLD
                    │                  │
                    └────────┬─────────┘
                             │
                      MOCK INTERVIEWS
```

---

# PHASE 0 — FOUNDATION

**Goal:** Make sure the underlying backend concepts are solid.

You don't need to relearn everything from scratch.

## Programming

* OOP
* Interfaces
* Composition
* Inheritance
* Polymorphism
* Abstraction
* Generics
* Error handling
* Concurrency basics

## Networking

* Client/server
* TCP/IP
* HTTP
* HTTP/1.1
* HTTP/2
* HTTP/3
* HTTPS/TLS
* DNS
* WebSockets
* SSE
* Long polling
* Reverse proxy
* CDN

## Backend

* REST
* API design
* Authentication
* Authorization
* Sessions
* JWT
* Stateless vs stateful services

## Databases

* SQL
* PostgreSQL
* Indexes
* Transactions
* ACID
* Isolation levels
* Locks
* MVCC
* Connection pooling

## Infrastructure

* Linux basics
* Processes vs threads
* Docker
* Nginx
* AWS basics

### Don't get stuck here.

**~1–2 weeks max** if most of this is already familiar.

---

# PHASE 1 — LLD FUNDAMENTALS

**Goal:** Learn to design maintainable, extensible software.

---

## 1. OOP

Learn properly:

* Classes
* Objects
* Encapsulation
* Abstraction
* Inheritance
* Polymorphism
* Interfaces
* Composition
* Aggregation
* Association

Most important principle:

> **Prefer composition over inheritance.**

---

# 2. SOLID

Master:

```text
S → Single Responsibility
O → Open/Closed
L → Liskov Substitution
I → Interface Segregation
D → Dependency Inversion
```

Don't memorize definitions.

Learn to recognize:

```text
Requirement
    ↓
Bad design
    ↓
Identify problem
    ↓
Apply SOLID
    ↓
Refactor
```

---

# 3. UML / Object Modeling

Learn:

* Class diagrams
* Sequence diagrams
* Associations
* Aggregation
* Composition
* Inheritance
* Dependencies

You don't need UML certification-level knowledge.

You need to turn:

> "Build a parking lot"

into:

```text
ParkingLot
   │
   ├── ParkingFloor
   │      │
   │      └── ParkingSpot
   │
   ├── Vehicle
   └── Ticket
```

---

# PHASE 2 — DESIGN PATTERNS

Don't learn every GoF pattern.

Focus on the ones you'll actually use.

## Creational

* Factory
* Abstract Factory
* Builder
* Singleton

## Structural

* Adapter
* Decorator
* Facade
* Proxy

## Behavioral

* Strategy
* Observer
* Command
* State
* Chain of Responsibility
* Template Method

### Priority

```text
🔥 Strategy
🔥 Factory
🔥 Builder
🔥 Observer
🔥 Decorator
🔥 Adapter
🔥 State
🔥 Command
```

Learn each pattern through a **problem → design → implementation**.

---

# PHASE 3 — LLD PROBLEMS

Now start designing actual systems.

## Beginner

1. Tic Tac Toe
2. Parking Lot
3. Vending Machine
4. ATM
5. Library Management

## Intermediate

6. Elevator
7. Splitwise
8. Movie Ticket Booking
9. Restaurant Management
10. Notification System
11. Logging Framework
12. Cache
13. Rate Limiter

## Advanced

14. Chess
15. File System
16. Task Scheduler
17. Ride Sharing
18. Payment System

### Target

**12–18 problems properly.**

Don't solve 50 by memorizing class diagrams.

For every problem:

```text
Requirements
     ↓
Entities
     ↓
Responsibilities
     ↓
Relationships
     ↓
Interfaces
     ↓
Patterns
     ↓
Class diagram
     ↓
Implementation
     ↓
Refactor
```

---

# PHASE 4 — HLD FUNDAMENTALS

Now move from:

> **How is the code structured?**

to:

> **How is the entire system structured?**

This is the biggest part of the roadmap.

---

# 4.1 Scalability

Learn:

### Vertical scaling

```text
More CPU
More RAM
Bigger machine
```

### Horizontal scaling

```text
          ┌── Server
LB ───────┼── Server
          └── Server
```

Understand:

* Stateless services
* Horizontal scaling
* Load balancing
* Auto scaling
* Replication
* Partitioning
* Sharding

---

# 4.2 Load Balancing

Learn:

* L4 vs L7
* Round robin
* Least connections
* IP hash
* Health checks
* Sticky sessions
* Failover

Understand:

> Why should application servers ideally be stateless?

---

# 4.3 Caching

**Very important.**

Learn:

* Cache-aside
* Read-through
* Write-through
* Write-back
* TTL
* Eviction
* LRU
* LFU
* Cache invalidation
* Cache stampede
* Cache penetration
* Cache avalanche

Then:

## Redis

Learn:

* Strings
* Lists
* Sets
* Sorted sets
* Hashes
* Streams
* Pub/Sub
* TTL
* Persistence
* Replication
* Sentinel
* Cluster
* Distributed locks

---

# 4.4 Databases

This should become one of your strongest areas.

## SQL

Learn deeply:

* Indexes
* Composite indexes
* B-tree
* Query planning
* Transactions
* ACID
* Isolation levels
* Locks
* MVCC
* Deadlocks
* Connection pooling
* Read replicas

## NoSQL

Understand:

* Key-value
* Document
* Wide-column
* Graph

Examples:

* Redis
* MongoDB
* Cassandra
* DynamoDB

The key question:

> **Why this database?**

Not:

> "Which database is better?"

---

# 4.5 Database Scaling

Understand the evolution:

```text
Single DB
   ↓
Indexes
   ↓
Query optimization
   ↓
Caching
   ↓
Read replicas
   ↓
Partitioning
   ↓
Sharding
```

Learn:

* Horizontal partitioning
* Vertical partitioning
* Sharding
* Consistent hashing
* Hot partitions
* Rebalancing
* Replication

---

# 4.6 Messaging

Learn the fundamental model:

```text
Producer
    ↓
 Message Broker
    ↓
Consumer
```

Then:

## RabbitMQ

* Exchanges
* Queues
* Routing
* ACK
* Retry
* DLQ

## Kafka

* Brokers
* Topics
* Partitions
* Offsets
* Consumer groups
* Replication
* Ordering
* Rebalancing

And understand:

> **RabbitMQ vs Kafka**

---

# 4.7 Async Processing

Understand:

```text
Synchronous

Client
 ↓
API
 ↓
DB
 ↓
Response
```

vs

```text
Asynchronous

Client
 ↓
API
 ↓
Queue
 ↓
Worker
 ↓
DB
```

Learn:

* Background jobs
* Workers
* Retries
* Exponential backoff
* Dead-letter queues
* Idempotency
* At-most-once
* At-least-once
* Exactly-once semantics

---

# 4.8 Distributed Systems

Now we go deeper.

Learn:

### Consistency

* Strong consistency
* Eventual consistency
* Causal consistency

### CAP

Understand:

* Consistency
* Availability
* Partition tolerance

And more importantly:

> **What tradeoff am I actually making?**

### Replication

* Leader/follower
* Multi-leader
* Leaderless
* Quorum

### Distributed coordination

* Leader election
* Distributed locks
* Consensus
* Raft basics

### Distributed transactions

* 2PC
* Saga pattern
* Transactional outbox

---

# 4.9 Reliability

Learn:

* Timeouts
* Retries
* Exponential backoff
* Circuit breakers
* Bulkheads
* Health checks
* Failover
* Redundancy
* Graceful degradation
* Disaster recovery

Think:

> "What happens when this component dies?"

For every architecture.

---

# 4.10 Rate Limiting

Learn:

* Fixed window
* Sliding window
* Sliding window counter
* Token bucket
* Leaky bucket

Then understand:

> How do I make rate limiting work across 50 API servers?

That's where Redis/distributed systems come in.

---

# 4.11 Storage

Understand:

* Block storage
* File storage
* Object storage
* S3
* CDN

Architecture:

```text
Client
   ↓
API
   ↓
Object Storage
   ↓
CDN
   ↓
Client
```

Understand why large media shouldn't flow through your application servers unnecessarily.

---

# 4.12 Search

Learn:

* Inverted indexes
* Full-text search
* Elasticsearch/OpenSearch
* Search vs database queries
* Ranking basics
* Sharding

---

# 4.13 Observability

Learn:

### Logs

"What happened?"

### Metrics

"How much/how often?"

### Traces

"Where did it happen?"

Understand:

* Prometheus
* Grafana
* OpenTelemetry
* Distributed tracing
* Correlation IDs
* SLIs
* SLOs
* SLAs

---

# PHASE 5 — SYSTEM DESIGN BUILDING BLOCKS

At this point you should be able to recognize these:

```text
              SYSTEM
                 │
     ┌───────────┼────────────┐
     │           │            │
   Traffic      Data        Async
     │           │            │
    LB          DB          Queue
    CDN        Cache        Kafka
     │        Replica       Worker
     │        Sharding        │
     └───────────┼────────────┘
                 │
             Reliability
                 │
        ┌────────┼────────┐
        │        │        │
     Retry     Timeout   Circuit
                           │
                       Observability
```

Now start combining them.

---

# PHASE 6 — HLD CASE STUDIES

Don't immediately jump into YouTube.

Go progressively.

## Level 1

### 1. URL Shortener

Learn:

* ID generation
* Hashing
* Database
* Cache
* Read/write ratio

### 2. Pastebin

Learn:

* Object storage
* TTL
* Metadata
* Caching

### 3. Rate Limiter

Learn:

* Redis
* Algorithms
* Distributed state

### 4. Web Crawler

Learn:

* Queue
* Workers
* Deduplication
* Distributed processing

---

# Level 2 — Real-time

### 5. Chat System

Learn:

* WebSockets
* Presence
* Message ordering
* Delivery guarantees
* Offline messages
* Message storage

### 6. Notification System

```text
Event
 ↓
Queue
 ↓
Workers
 ├── Email
 ├── SMS
 └── Push
```

Learn:

* Fan-out
* Retries
* DLQ
* Idempotency

---

# Level 3 — Social

### 7. Twitter/X

Learn:

* Feed generation
* Fan-out
* Celebrity problem
* Caching
* Sharding

### 8. Instagram

Learn:

* Media processing
* Object storage
* CDN
* Feed
* Fan-out

### 9. YouTube

Learn:

* Upload
* Transcoding
* Object storage
* CDN
* Metadata
* Streaming

---

# Level 4 — Marketplace / Real World

### 10. Uber

Learn:

* Geospatial systems
* Location tracking
* Matching
* Real-time updates
* Event streaming

### 11. Food Delivery

Learn:

* Orders
* Restaurants
* Delivery partners
* Tracking
* Payments
* Notifications

### 12. Amazon

Learn:

* Catalog
* Search
* Cart
* Inventory
* Orders
* Payments

---

# PHASE 7 — BACKEND / INFRASTRUCTURE SYSTEMS

This is where I'd give **extra attention** given your career direction.

Design:

1. Distributed Cache
2. Distributed Rate Limiter
3. Message Queue
4. Job Scheduler
5. API Gateway
6. File Storage
7. Logging System
8. Metrics System
9. Webhook Delivery System
10. Distributed ID Generator
11. Notification Platform
12. Search System

These systems teach you more backend engineering than simply doing ten social-media clones.

---

# PHASE 8 — ADVANCED DISTRIBUTED SYSTEMS

Only after the previous phases.

Learn:

### Distributed databases

* Replication models
* Quorum
* Consistent hashing
* Vector clocks
* Conflict resolution

### Consensus

* Raft
* Leader election
* Log replication

### Architecture patterns

* Event-driven architecture
* CQRS
* Event sourcing
* Saga
* Transactional outbox
* CDC

### Advanced infrastructure

* Service discovery
* API gateways
* Service mesh
* Kubernetes architecture
* Distributed tracing

**This is advanced material.**

Don't make it your starting point.

---

# 🧪 HOW TO STUDY EVERY CONCEPT

This is your **fixed learning methodology**.

For every topic:

```text
1. WHY?
   ↓
2. WHAT?
   ↓
3. HOW?
   ↓
4. TRADEOFFS
   ↓
5. TOY IMPLEMENTATION
   ↓
6. PRODUCTION IMPLEMENTATION
   ↓
7. USE IN SYSTEM DESIGN
   ↓
8. EXPLAIN FROM MEMORY
```

Example:

## Redis

### 1. Why?

Database is too slow / expensive for repeated reads.

### 2. What?

In-memory data store.

### 3. How?

Understand memory, commands, expiration, eviction.

### 4. Tradeoffs?

Fast, but memory-limited and introduces another dependency.

### 5. Build

Implement a tiny cache.

### 6. Production

Study Redis architecture.

### 7. Design

Use Redis in:

* URL shortener
* Rate limiter
* Chat system

### 8. Explain

Close your notes and explain:

> "Why Redis here instead of PostgreSQL?"

If you can do that, **you actually know it.**

---

# 🛠️ PROJECTS — DON'T STOP THEM

Your projects should run **parallel to this roadmap**.

Think:

```text
                YOUR DEVELOPMENT
                       │
        ┌──────────────┼──────────────┐
        │              │              │
       DSA         SYSTEM DESIGN    PROJECT
        │              │              │
        │         Learn concept      │
        │              │              │
        │              ▼              │
        │         Build toy          │
        │              │              │
        │              ▼              │
        │         Apply to ───────────┘
        │          project
        │
        └─────────────────────────────
```

Your projects are where concepts become real.

Don't stop building just because you're studying system design.

---

# 📅 THE TIMELINE

I'd roughly structure it as:

## Weeks 1–3

**LLD**

```text
OOP
SOLID
UML
Patterns
```

* 5–6 LLD problems

---

## Weeks 4–6

**LLD → HLD transition**

```text
LLD advanced
Concurrency
Networking
Scalability
Load balancing
Caching
Redis
```

* 6–8 LLD problems

---

## Weeks 7–10

**HLD core**

```text
Databases
DB scaling
Replication
Partitioning
Sharding
Messaging
Kafka
Async processing
Rate limiting
```

* 4–5 HLD systems

---

## Weeks 11–13

**Distributed systems**

```text
Consistency
CAP
Quorum
Distributed locks
Consensus basics
Reliability
Fault tolerance
Observability
```

* 4–5 HLD systems

---

## Weeks 14–16

**Interview-level HLD**

```text
Twitter
YouTube
WhatsApp
Uber
Amazon
Netflix
```

* infrastructure systems

---

## After that

Keep improving through:

```text
System design
      +
Projects
      +
Mock interviews
      +
Real engineering problems
```

---

# 🎯 What "DONE" Looks Like

Don't measure progress by:

> "I watched 73 system-design videos."

Measure it like this.

You should eventually be able to receive:

> **"Design WhatsApp."**

and independently go:

```text
Requirements
      ↓
Scale estimation
      ↓
APIs
      ↓
Data model
      ↓
High-level architecture
      ↓
WebSocket architecture
      ↓
Message delivery
      ↓
Storage
      ↓
Caching
      ↓
Partitioning
      ↓
Failures
      ↓
Consistency
      ↓
Tradeoffs
```

And when the interviewer asks:

> "Why Kafka?"

you can answer from understanding.

Not:

> "Because Kafka is scalable." 💀

---

# 🏁 FINAL PRIORITY

If I had to compress the entire roadmap into one hierarchy for you:

```text
                    SYSTEM DESIGN
                         │
             ┌───────────┴───────────┐
             │                       │
            LLD                     HLD
             │                       │
        OOP + SOLID             Scalability
        Patterns                Databases
        UML                     Caching
        Concurrency             Messaging
             │                   Networking
             │                   Storage
             │                   Reliability
             │                   Observability
             │                       │
             └───────────┬───────────┘
                         │
                DISTRIBUTED SYSTEMS
                         │
                         ▼
                  CASE STUDIES
                         │
                         ▼
                  MOCK INTERVIEWS
```

And alongside **all of it**:

```text
DSA ────────────────┐
                    │
System Design ──────┼──→ Backend Engineer
                    │
Projects ───────────┘
                    │
AI / Agentic AI ─────────→ Side Quest
                              │
                              ▼
                       Backend + AI Engineer
                              │
                              ▼
                       AI Systems Engineer
```