# Lộ trình học để phát triển OmniSupport

## 📚 Kiến thức cần có

### 1. **Nền tảng cơ bản** (Bắt buộc)

#### JavaScript/TypeScript ⭐⭐⭐⭐⭐
- **Tại sao:** Toàn bộ project dùng JavaScript
- **Học gì:**
  - ES6+ (async/await, promises, arrow functions)
  - TypeScript (types, interfaces, generics)
- **Thời gian:** 2-3 tháng nếu chưa biết
- **Tài liệu:**
  - https://javascript.info/
  - https://www.typescriptlang.org/docs/

#### Node.js ⭐⭐⭐⭐⭐
- **Tại sao:** Backend chạy trên Node.js
- **Học gì:**
  - NPM/pnpm package manager
  - Module system (import/export)
  - Event loop, streams
- **Thời gian:** 1-2 tháng
- **Tài liệu:**
  - https://nodejs.org/en/docs/

---

### 2. **Backend Development** (Bắt buộc)

#### NestJS ⭐⭐⭐⭐⭐
- **Tại sao:** Framework chính cho backend
- **Học gì:**
  - Modules, Controllers, Services
  - Dependency Injection
  - Guards, Interceptors, Pipes
  - WebSocket Gateway
- **Thời gian:** 2-3 tuần
- **Tài liệu:**
  - https://docs.nestjs.com/

#### PostgreSQL ⭐⭐⭐⭐
- **Tại sao:** Database chính
- **Học gì:**
  - SQL queries (SELECT, INSERT, UPDATE, DELETE)
  - Relationships (1-1, 1-N, N-N)
  - Indexes, transactions
- **Thời gian:** 2-3 tuần
- **Tài liệu:**
  - https://www.postgresql.org/docs/

#### Prisma ORM ⭐⭐⭐⭐
- **Tại sao:** Quản lý database dễ dàng
- **Học gì:**
  - Schema definition
  - Migrations
  - Prisma Client API
- **Thời gian:** 1 tuần
- **Tài liệu:**
  - https://www.prisma.io/docs/

#### Redis ⭐⭐⭐
- **Tại sao:** Cache và session
- **Học gì:**
  - Key-value storage
  - Pub/Sub
  - Expiration
- **Thời gian:** 1 tuần
- **Tài liệu:**
  - https://redis.io/docs/

---

### 3. **Frontend Development** (Bắt buộc)

#### React ⭐⭐⭐⭐⭐
- **Tại sao:** Widget và Dashboard dùng React
- **Học gì:**
  - Components, Props, State
  - Hooks (useState, useEffect, useContext)
  - React Router
- **Thời gian:** 1-2 tháng
- **Tài liệu:**
  - https://react.dev/

#### Next.js ⭐⭐⭐⭐
- **Tại sao:** Dashboard dùng Next.js
- **Học gì:**
  - App Router
  - Server Components
  - API Routes
- **Thời gian:** 2-3 tuần
- **Tài liệu:**
  - https://nextjs.org/docs

#### TailwindCSS ⭐⭐⭐
- **Tại sao:** Styling nhanh
- **Học gì:**
  - Utility classes
  - Responsive design
  - Custom config
- **Thời gian:** 1 tuần
- **Tài liệu:**
  - https://tailwindcss.com/docs

---

### 4. **Real-time Communication** (Bắt buộc)

#### WebSocket / Socket.IO ⭐⭐⭐⭐⭐
- **Tại sao:** Chat real-time
- **Học gì:**
  - WebSocket protocol
  - Socket.IO events
  - Rooms and namespaces
- **Thời gian:** 1-2 tuần
- **Tài liệu:**
  - https://socket.io/docs/

---

### 5. **API Integration** (Bắt buộc)

#### REST API ⭐⭐⭐⭐⭐
- **Tại sao:** Giao tiếp giữa frontend-backend
- **Học gì:**
  - HTTP methods (GET, POST, PUT, DELETE)
  - Status codes
  - Authentication (JWT)
- **Thời gian:** 2 tuần

#### Facebook Graph API ⭐⭐⭐⭐
- **Tại sao:** Tích hợp Facebook Messenger
- **Học gì:**
  - Webhooks
  - Send/Receive messages
  - Page access tokens
- **Thời gian:** 1-2 tuần
- **Tài liệu:**
  - https://developers.facebook.com/docs/graph-api/

#### Instagram Graph API ⭐⭐⭐⭐
- **Tại sao:** Tích hợp Instagram Direct
- **Học gì:**
  - Instagram messaging
  - Media handling
- **Thời gian:** 1 tuần
- **Tài liệu:**
  - https://developers.facebook.com/docs/instagram-api/

#### Zalo OA API ⭐⭐⭐⭐
- **Tại sao:** Tích hợp Zalo
- **Học gì:**
  - Zalo Official Account
  - Message templates
- **Thời gian:** 1 tuần
- **Tài liệu:**
  - https://developers.zalo.me/docs/

---

### 6. **AI & Machine Learning** (Giai đoạn 2)

#### OpenAI API ⭐⭐⭐⭐⭐
- **Tại sao:** AI chatbot
- **Học gì:**
  - GPT models
  - Function calling
  - Prompt engineering
- **Thời gian:** 2-3 tuần
- **Tài liệu:**
  - https://platform.openai.com/docs/

#### LangChain ⭐⭐⭐⭐
- **Tại sao:** Orchestrate AI workflows
- **Học gì:**
  - Chains
  - Agents
  - Tools
- **Thời gian:** 2 tuần
- **Tài liệu:**
  - https://js.langchain.com/docs/

#### Vector Database (Pinecone/Qdrant) ⭐⭐⭐
- **Tại sao:** Semantic search cho FAQ
- **Học gì:**
  - Embeddings
  - Similarity search
- **Thời gian:** 1-2 tuần

---

### 7. **DevOps & Deployment** (Quan trọng)

#### Docker ⭐⭐⭐⭐⭐
- **Tại sao:** Containerization, dễ deploy
- **Học gì:**
  - Dockerfile
  - Docker Compose
  - Container management
- **Thời gian:** 2 tuần
- **Tài liệu:**
  - https://docs.docker.com/

#### Git & GitHub ⭐⭐⭐⭐⭐
- **Tại sao:** Version control, open-source
- **Học gì:**
  - Commit, push, pull
  - Branches
  - Pull requests
- **Thời gian:** 1 tuần

---

### 8. **Architecture & Design Patterns** (Nâng cao)

#### Clean Architecture ⭐⭐⭐⭐
- **Tại sao:** Code dễ maintain
- **Học gì:**
  - Domain layer
  - Application layer
  - Infrastructure layer
- **Thời gian:** 2-3 tuần
- **Tài liệu:**
  - "Clean Architecture" by Robert C. Martin

#### Event-Driven Architecture ⭐⭐⭐⭐
- **Tại sao:** Modules giao tiếp qua events
- **Học gì:**
  - Domain events
  - Event handlers
  - Message queues
- **Thời gian:** 2 tuần

#### Multi-tenancy ⭐⭐⭐
- **Tại sao:** Nhiều shop dùng chung hệ thống
- **Học gì:**
  - Tenant isolation
  - Row-level security
- **Thời gian:** 1-2 tuần

---

## 🗓️ LỘ TRÌNH HỌC (Tổng: 6-8 tháng)

### Tháng 1-2: Nền tảng
- [ ] JavaScript/TypeScript cơ bản
- [ ] Node.js cơ bản
- [ ] React cơ bản

### Tháng 3-4: Backend
- [ ] NestJS
- [ ] PostgreSQL + Prisma
- [ ] Redis
- [ ] WebSocket/Socket.IO

### Tháng 5: Frontend
- [ ] Next.js
- [ ] TailwindCSS
- [ ] State management

### Tháng 6: API Integration
- [ ] Facebook API
- [ ] Instagram API
- [ ] Zalo API

### Tháng 7: AI
- [ ] OpenAI API
- [ ] LangChain
- [ ] Vector database

### Tháng 8: DevOps
- [ ] Docker
- [ ] CI/CD
- [ ] Deployment

---

## 📖 TÀI LIỆU HỌC TIẾNG VIỆT

### YouTube Channels:
- **Evondev** - React, Next.js
- **Hỏi Dân IT** - NestJS, Backend
- **CodersX** - JavaScript, Node.js

### Courses:
- **Udemy** - The Complete Node.js Developer Course
- **Udemy** - NestJS Zero to Hero
- **Udemy** - React - The Complete Guide

---

## 💡 LỜI KHUYÊN

### Nếu bạn mới bắt đầu:
1. Học JavaScript/TypeScript trước (2-3 tháng)
2. Làm project nhỏ để thực hành
3. Đọc code của người khác trên GitHub

### Nếu bạn đã biết JavaScript:
1. Tập trung vào NestJS và React
2. Học Docker sớm để dễ setup môi trường
3. Bắt đầu code ngay, học trong quá trình làm

### Nếu bạn muốn nhanh:
1. Thuê developer có kinh nghiệm
2. Hoặc tìm co-founder technical
3. Hoặc học 1 phần, outsource phần còn lại

---

## 🎯 KẾT LUẬN

**Tổng thời gian học:** 6-8 tháng (full-time)

**Kiến thức quan trọng nhất:**
1. JavaScript/TypeScript ⭐⭐⭐⭐⭐
2. NestJS ⭐⭐⭐⭐⭐
3. React ⭐⭐⭐⭐⭐
4. WebSocket ⭐⭐⭐⭐⭐
5. Docker ⭐⭐⭐⭐⭐

**Bắt đầu từ đâu?**
→ JavaScript → Node.js → NestJS → React → Tích hợp API
