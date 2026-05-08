# Architecture Overview

## System Design

OmniSupport follows a **Modular Monolith** architecture with **Clean Architecture** principles.

## Core Layers

### 1. Domain Layer
- Pure business logic
- No external dependencies
- Entities, Value Objects, Domain Events

### 2. Application Layer
- Use Cases
- Application Services
- DTOs

### 3. Infrastructure Layer
- Database (PostgreSQL)
- External APIs
- Message Queue (BullMQ)
- WebSocket (Socket.IO)

### 4. Presentation Layer
- REST API
- WebSocket Gateway
- GraphQL (future)

## Module Structure

Each module follows this structure:

```
module/
├── domain/
│   ├── entities/
│   ├── value-objects/
│   └── events/
├── application/
│   ├── use-cases/
│   ├── services/
│   └── dtos/
├── infrastructure/
│   ├── repositories/
│   └── adapters/
└── presentation/
    └── controllers/
```

## Event-Driven Communication

Modules communicate via domain events:

```typescript
// Example
MessageReceivedEvent
  → AI Module (generate reply)
  → Analytics Module (track metrics)
  → Notification Module (notify staff)
```

## Integration Architecture

Each platform integration is isolated:

```
integration/
├── facebook/
│   ├── adapter.ts
│   ├── webhook.controller.ts
│   └── message.mapper.ts
├── zalo/
├── instagram/
└── website/
```

## AI Architecture

AI acts as an orchestrator, never directly accessing the database:

```
User Message
  ↓
AI Agent
  ↓
[Inventory Service | Order Service | Product Service]
  ↓
Database
```

## Multi-tenancy

Each tenant has isolated:
- Database schema (row-level security)
- Redis namespace
- WebSocket rooms
- Background jobs

## Scalability Strategy

- Horizontal scaling via Docker
- Redis for session/cache
- BullMQ for async jobs
- PostgreSQL connection pooling
