# OmniSupport Backend

NestJS backend API for OmniSupport platform.

## Setup

```bash
# Install dependencies
pnpm install

# Run development server
pnpm dev

# Build for production
pnpm build

# Start production server
pnpm start
```

## API Endpoints

### Health Check
```
GET /api/health
```

Response:
```json
{
  "status": "ok",
  "timestamp": "2026-05-09T00:00:00.000Z",
  "service": "OmniSupport Backend",
  "version": "0.1.0"
}
```

## Environment Variables

Create `.env` file in root directory:

```env
PORT=3000
NODE_ENV=development
```

## Project Structure

```
src/
├── modules/          # Feature modules
├── infrastructure/   # Database, external services
├── shared/          # Shared utilities
├── app.module.ts    # Root module
└── main.ts          # Entry point
```
