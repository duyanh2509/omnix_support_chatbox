# Contributing Guide

## Getting Started

### Prerequisites
- Node.js 20+
- pnpm 8+
- Docker & Docker Compose
- PostgreSQL 15+
- Redis 7+

### Setup Development Environment

1. Clone the repository:
```bash
git clone https://github.com/duyanh2509/omnix_support_chatbox.git
cd omnix_support_chatbox
```

2. Install dependencies:
```bash
pnpm install
```

3. Setup environment variables:
```bash
cp .env.example .env
```

4. Start infrastructure:
```bash
docker compose up -d
```

5. Run migrations:
```bash
pnpm --filter backend prisma:migrate
```

6. Start development servers:
```bash
pnpm dev
```

---

## Project Structure

```
omnix_support_chatbox/
├── apps/
│   ├── backend/       # NestJS API
│   ├── dashboard/     # Next.js admin dashboard
│   └── widget/        # React chat widget
├── packages/
│   ├── sdk/          # JavaScript SDK
│   ├── shared/       # Shared utilities
│   ├── ui/           # Shared UI components
│   └── types/        # TypeScript types
└── docs/             # Documentation
```

---

## Development Workflow

### 1. Create a Branch
```bash
git checkout -b feature/your-feature-name
```

### 2. Make Changes
- Follow the code style
- Write tests
- Update documentation

### 3. Run Tests
```bash
pnpm test
```

### 4. Commit Changes
```bash
git add .
git commit -m "feat: add new feature"
```

We follow [Conventional Commits](https://www.conventionalcommits.org/):
- `feat:` - New feature
- `fix:` - Bug fix
- `docs:` - Documentation
- `refactor:` - Code refactoring
- `test:` - Tests
- `chore:` - Maintenance

### 5. Push and Create PR
```bash
git push origin feature/your-feature-name
```

---

## Code Style

### TypeScript
- Use TypeScript strict mode
- Prefer interfaces over types
- Use explicit return types

### Naming Conventions
- **Files:** kebab-case (`user-service.ts`)
- **Classes:** PascalCase (`UserService`)
- **Functions:** camelCase (`getUserById`)
- **Constants:** UPPER_SNAKE_CASE (`MAX_RETRY_COUNT`)

### Module Structure
```
module/
├── domain/
├── application/
├── infrastructure/
└── presentation/
```

---

## Testing

### Unit Tests
```bash
pnpm test:unit
```

### Integration Tests
```bash
pnpm test:integration
```

### E2E Tests
```bash
pnpm test:e2e
```

---

## Pull Request Guidelines

1. **Title:** Use conventional commit format
2. **Description:** Explain what and why
3. **Tests:** Include relevant tests
4. **Documentation:** Update if needed
5. **Breaking Changes:** Clearly document

---

## Questions?

- Open an issue
- Join our Discord (coming soon)
- Email: support@omnix.com
