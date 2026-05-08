# Technology Stack

## Backend

### Core Framework
- **NestJS** - Progressive Node.js framework
- **TypeScript** - Type safety

### Database
- **PostgreSQL** - Primary database
- **Prisma** - ORM and migrations
- **Redis** - Caching and sessions

### Real-time
- **Socket.IO** - WebSocket communication
- **BullMQ** - Background job processing

### Authentication
- **JWT** - Token-based auth
- **Passport** - Auth strategies

### API
- **REST API** - Primary API
- **GraphQL** (future) - Flexible queries

---

## Frontend

### Dashboard
- **Next.js 14** - React framework (App Router)
- **TypeScript** - Type safety
- **TailwindCSS** - Utility-first CSS
- **Shadcn UI** - Component library
- **React Query** - Data fetching
- **Zustand** - State management

### Widget
- **React** - UI library
- **Vite** - Build tool
- **TailwindCSS** - Styling

---

## AI & ML

- **OpenAI API** - GPT models
- **LangChain** - AI orchestration
- **Pinecone / Qdrant** - Vector database
- **Embeddings** - Semantic search

---

## DevOps

### Containerization
- **Docker** - Containerization
- **Docker Compose** - Local development

### CI/CD
- **GitHub Actions** - Automation
- **Docker Hub** - Image registry

### Monitoring (future)
- **Prometheus** - Metrics
- **Grafana** - Visualization
- **Sentry** - Error tracking

---

## Development Tools

- **pnpm** - Package manager (monorepo)
- **Turborepo** - Build system
- **ESLint** - Linting
- **Prettier** - Code formatting
- **Husky** - Git hooks

---

## Testing

- **Jest** - Unit testing
- **Supertest** - API testing
- **Playwright** - E2E testing

---

## External Services

### Integrations
- **Facebook Graph API** - Messenger
- **Instagram Graph API** - Direct messages
- **Zalo OA API** - Zalo messaging

### Future
- **TikTok API**
- **Telegram Bot API**
- **WhatsApp Business API**

---

## Infrastructure Requirements

### Minimum
- **CPU:** 2 cores
- **RAM:** 4GB
- **Storage:** 20GB SSD

### Recommended
- **CPU:** 4 cores
- **RAM:** 8GB
- **Storage:** 50GB SSD
- **Network:** 100Mbps

---

## Environment Variables

```env
# Database
DATABASE_URL=postgresql://user:pass@localhost:5432/omnisupport

# Redis
REDIS_URL=redis://localhost:6379

# JWT
JWT_SECRET=your-secret-key

# OpenAI
OPENAI_API_KEY=sk-...

# Facebook
FACEBOOK_APP_ID=...
FACEBOOK_APP_SECRET=...

# Zalo
ZALO_APP_ID=...
ZALO_APP_SECRET=...
```
