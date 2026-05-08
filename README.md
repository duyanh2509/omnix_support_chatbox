# OmniSupport

Open-source AI-native omnichannel customer communication platform for ecommerce.

---

## 🎯 Vision

OmniSupport helps ecommerce businesses manage customer conversations from multiple platforms in one unified inbox.

### Supported Channels:
- ✅ Website Live Chat
- ✅ Facebook Messenger
- ✅ Instagram
- ✅ Zalo
- 🔜 TikTok, Telegram, WhatsApp

### Design Principles:
- Clean Architecture
- Multi-tenant
- AI-ready
- Easy to self-host
- Easy to integrate

---

## ✨ Core Features

### 📥 Unified Inbox
Collect messages from multiple platforms into one dashboard.

### ⚡ Real-time Messaging
Realtime conversation updates using WebSocket.

### 🔌 Multi-platform Integration
Each platform is implemented as an isolated adapter.

**Supported:**
- Website Widget
- Facebook
- Instagram
- Zalo

### 🤖 AI Assistant
AI can:
- Answer FAQs
- Check inventory
- Suggest products
- Generate reply suggestions

### 🏢 Multi-tenant Architecture
Each business has:
- Isolated conversations
- Isolated integrations
- Isolated AI configuration
- Isolated staff

---

## 🏗️ Architecture

### Backend
- **NestJS**
- Modular Monolith
- Clean Architecture
- Event-driven design

### Frontend
- **NextJS**
- TailwindCSS
- Shadcn UI

### Infrastructure
- PostgreSQL
- Redis
- Socket.IO
- BullMQ

---

## 📁 Project Structure

```txt
apps/
  backend/
  dashboard/
  widget/
packages/
  sdk/
  shared/
  ui/
  types/
```

---

## 🗂️ Backend Structure

```txt
src/
  modules/
    auth/
    tenant/
    inbox/
    conversation/
    message/
    integration/
    ai/
    automation/
  infrastructure/
  shared/
```

---

## 🎯 Core Principles

### 1. SDK-first
Integration must be simple.

```bash
npm install omnisupport-sdk
```

### 2. Plugin-based Integration
Each platform is isolated.

```txt
integrations/
  facebook/
  zalo/
  instagram/
```

### 3. Event-driven
Core events:
- `MessageReceived`
- `MessageSent`
- `ConversationCreated`
- `AIReplyGenerated`

### 4. AI as Orchestrator
AI never accesses the database directly.

**Correct flow:**
```txt
AI
 ↓
Inventory Service
 ↓
Database
```

---

## 🗺️ Development Roadmap

### Phase 1
- Website Widget
- Dashboard
- Authentication
- Realtime Messaging

### Phase 2
- Facebook Integration
- Conversation Management

### Phase 3
- Instagram + Zalo

### Phase 4
- AI FAQ Assistant

### Phase 5
- Inventory AI
- Order AI
- Product Recommendation

---

## 🚀 Non-functional Requirements

- Scalable
- Maintainable
- Modular
- Reusable
- Easy self-host
- Docker-first
- API-first

---

## 🐳 Deployment

```bash
docker compose up
```

---

## 🎯 Long-term Goal

Build an open-source AI-native customer communication platform optimized for ecommerce businesses.

---

## 📄 License

Copyright © 2026 Omnix
