# Kế hoạch triển khai OmniSupport

## 📋 Tổng quan

Dự án được chia thành **4 Phases chính**, mỗi phase có nhiều requirements nhỏ.

---

## 🎯 PHASE 1: Foundation & Website Chat Widget

**Mục tiêu:** Tạo chat widget cơ bản hoạt động trên website

**Thời gian:** 2-3 tuần

**Kết quả:** Khách hàng có thể chat trên website, bạn nhận tin nhắn real-time

---

### Requirement 1.1: Setup Backend Project ⏱️ 2-3 giờ

**Mục tiêu:** Khởi tạo NestJS backend

**Checklist:**
- [ ] Cài đặt Node.js (nếu chưa có)
- [ ] Cài đặt pnpm
- [ ] Tạo NestJS project trong `apps/backend`
- [ ] Cấu hình TypeScript
- [ ] Cấu hình ESLint & Prettier
- [ ] Test chạy server: `pnpm dev`

**Output:** Server chạy được tại `http://localhost:3000`

---

### Requirement 1.2: Setup Database ⏱️ 2-3 giờ

**Mục tiêu:** Cài đặt PostgreSQL và Prisma

**Checklist:**
- [ ] Cài đặt Docker Desktop
- [ ] Tạo `docker-compose.yml` cho PostgreSQL
- [ ] Chạy PostgreSQL: `docker compose up -d`
- [ ] Cài đặt Prisma
- [ ] Tạo Prisma schema cơ bản
- [ ] Chạy migration đầu tiên
- [ ] Test kết nối database

**Output:** Database chạy và kết nối thành công

---

### Requirement 1.3: Authentication Module ⏱️ 4-5 giờ

**Mục tiêu:** Đăng nhập/đăng ký cho shop owner

**Checklist:**
- [ ] Tạo User model trong Prisma
- [ ] Tạo Auth module (NestJS)
- [ ] API: POST /auth/register
- [ ] API: POST /auth/login
- [ ] JWT token generation
- [ ] Password hashing (bcrypt)
- [ ] Auth Guard middleware
- [ ] Test với Postman/Thunder Client

**Output:** 
- API đăng ký/đăng nhập hoạt động
- Nhận được JWT token

---

### Requirement 1.4: Conversation & Message Models ⏱️ 3-4 giờ

**Mục tiêu:** Tạo database schema cho chat

**Checklist:**
- [ ] Tạo Conversation model
- [ ] Tạo Message model
- [ ] Tạo Customer model
- [ ] Định nghĩa relationships
- [ ] Chạy migration
- [ ] Tạo seed data mẫu
- [ ] Test query với Prisma Studio

**Output:** Database có đủ bảng để lưu tin nhắn

---

### Requirement 1.5: Message API ⏱️ 4-5 giờ

**Mục tiêu:** CRUD API cho tin nhắn

**Checklist:**
- [ ] Tạo Message module
- [ ] API: GET /conversations (list conversations)
- [ ] API: GET /conversations/:id/messages (get messages)
- [ ] API: POST /messages (send message)
- [ ] API: PATCH /messages/:id (update message)
- [ ] Pagination cho messages
- [ ] Test tất cả APIs

**Output:** APIs hoạt động, test bằng Postman

---

### Requirement 1.6: WebSocket Setup ⏱️ 3-4 giờ

**Mục tiêu:** Real-time messaging với Socket.IO

**Checklist:**
- [ ] Cài đặt @nestjs/websockets và socket.io
- [ ] Tạo WebSocket Gateway
- [ ] Event: `message:send`
- [ ] Event: `message:received`
- [ ] Event: `typing:start` và `typing:stop`
- [ ] Authentication cho WebSocket
- [ ] Test với Socket.IO client

**Output:** Tin nhắn gửi/nhận real-time

---

### Requirement 1.7: Chat Widget (Frontend) ⏱️ 6-8 giờ

**Mục tiêu:** Tạo chat widget nhúng vào website

**Checklist:**
- [ ] Setup React + Vite trong `apps/widget`
- [ ] Tạo UI chat bubble (nút chat góc phải)
- [ ] Tạo UI chat window (cửa sổ chat)
- [ ] Component: MessageList
- [ ] Component: MessageInput
- [ ] Component: TypingIndicator
- [ ] Kết nối Socket.IO client
- [ ] Gửi/nhận tin nhắn real-time
- [ ] Styling với TailwindCSS
- [ ] Build widget thành single file

**Output:** Widget hoạt động, có thể nhúng vào website

---

### Requirement 1.8: Admin Dashboard - Basic ⏱️ 8-10 giờ

**Mục tiêu:** Giao diện để shop owner xem và trả lời tin nhắn

**Checklist:**
- [ ] Setup Next.js trong `apps/dashboard`
- [ ] Trang login
- [ ] Layout: Sidebar + Main content
- [ ] Trang: Conversation List
- [ ] Trang: Conversation Detail
- [ ] Component: MessageThread
- [ ] Component: MessageInput
- [ ] Kết nối Socket.IO
- [ ] Real-time message updates
- [ ] Styling với TailwindCSS + Shadcn UI

**Output:** Dashboard hoạt động, có thể chat với khách

---

### Requirement 1.9: Testing & Bug Fixes ⏱️ 4-6 giờ

**Checklist:**
- [ ] Test flow: Khách chat → Shop nhận → Shop trả lời
- [ ] Test real-time updates
- [ ] Fix bugs
- [ ] Optimize performance
- [ ] Add loading states
- [ ] Add error handling

**Output:** Phase 1 hoàn chỉnh, không có bug nghiêm trọng

---

## 🎯 PHASE 2: Multi-platform Integration

**Mục tiêu:** Tích hợp Facebook, Instagram, Zalo

**Thời gian:** 3-4 tuần

---

### Requirement 2.1: Integration Architecture ⏱️ 3-4 giờ

**Mục tiêu:** Thiết kế kiến trúc adapter pattern

**Checklist:**
- [ ] Tạo Interface: `IMessageAdapter`
- [ ] Tạo Interface: `IWebhookHandler`
- [ ] Tạo base class: `BaseAdapter`
- [ ] Tạo Integration model trong Prisma
- [ ] Tạo IntegrationService

**Output:** Kiến trúc sẵn sàng cho các platform

---

### Requirement 2.2: Facebook Messenger Integration ⏱️ 8-10 giờ

**Checklist:**
- [ ] Đăng ký Facebook App
- [ ] Setup Facebook webhook
- [ ] Tạo FacebookAdapter
- [ ] Xử lý webhook events
- [ ] API: Nhận tin nhắn từ Facebook
- [ ] API: Gửi tin nhắn đến Facebook
- [ ] Sync customer profile
- [ ] Handle attachments (images, files)
- [ ] Test với Facebook Page

**Output:** Nhận/gửi tin Facebook Messenger thành công

---

### Requirement 2.3: Instagram Direct Integration ⏱️ 6-8 giờ

**Checklist:**
- [ ] Setup Instagram Business Account
- [ ] Tạo InstagramAdapter
- [ ] Xử lý Instagram webhooks
- [ ] API: Nhận tin nhắn Instagram
- [ ] API: Gửi tin nhắn Instagram
- [ ] Handle Instagram media
- [ ] Test với Instagram account

**Output:** Nhận/gửi tin Instagram thành công

---

### Requirement 2.4: Zalo OA Integration ⏱️ 6-8 giờ

**Checklist:**
- [ ] Đăng ký Zalo Official Account
- [ ] Tạo ZaloAdapter
- [ ] Xử lý Zalo webhooks
- [ ] API: Nhận tin nhắn Zalo
- [ ] API: Gửi tin nhắn Zalo
- [ ] Handle Zalo templates
- [ ] Test với Zalo OA

**Output:** Nhận/gửi tin Zalo thành công

---

### Requirement 2.5: Unified Inbox UI ⏱️ 6-8 giờ

**Checklist:**
- [ ] Update Conversation model (add platform field)
- [ ] Show platform icon (Facebook/Instagram/Zalo/Website)
- [ ] Filter conversations by platform
- [ ] Unified message format
- [ ] Platform-specific features
- [ ] Test với tất cả platforms

**Output:** Dashboard hiển thị tin nhắn từ tất cả nền tảng

---

### Requirement 2.6: Testing Phase 2 ⏱️ 4-6 giờ

**Checklist:**
- [ ] Test nhận tin từ Facebook
- [ ] Test nhận tin từ Instagram
- [ ] Test nhận tin từ Zalo
- [ ] Test gửi tin đến tất cả platforms
- [ ] Test attachments
- [ ] Fix bugs

**Output:** Phase 2 hoàn chỉnh

---

## 🎯 PHASE 3: AI Chatbot

**Mục tiêu:** AI tự động trả lời câu hỏi

**Thời gian:** 2-3 tuần

---

### Requirement 3.1: OpenAI Integration ⏱️ 3-4 giờ

**Checklist:**
- [ ] Đăng ký OpenAI API key
- [ ] Cài đặt OpenAI SDK
- [ ] Tạo AIService
- [ ] Test basic chat completion
- [ ] Setup system prompt
- [ ] Handle API errors

**Output:** Có thể gọi OpenAI API

---

### Requirement 3.2: Inventory Service ⏱️ 4-5 giờ

**Checklist:**
- [ ] Tạo Product model
- [ ] Tạo Inventory model
- [ ] API: Check product availability
- [ ] API: Get product info
- [ ] API: Search products
- [ ] Seed sample products

**Output:** Service check tồn kho hoạt động

---

### Requirement 3.3: AI Function Calling ⏱️ 6-8 giờ

**Checklist:**
- [ ] Define function: `checkInventory`
- [ ] Define function: `getProductInfo`
- [ ] Define function: `searchProducts`
- [ ] Implement function handlers
- [ ] Connect AI with functions
- [ ] Test AI calling functions

**Output:** AI có thể check kho và trả lời

---

### Requirement 3.4: Auto-reply Logic ⏱️ 4-5 giờ

**Checklist:**
- [ ] Tạo AIConfig model (enable/disable AI)
- [ ] Detect when to use AI
- [ ] AI reply suggestions
- [ ] Auto-reply toggle
- [ ] Fallback to human
- [ ] Track AI performance

**Output:** AI tự động trả lời hoặc gợi ý

---

### Requirement 3.5: Knowledge Base ⏱️ 6-8 giờ

**Checklist:**
- [ ] Setup vector database (Pinecone/Qdrant)
- [ ] Tạo FAQ model
- [ ] Generate embeddings
- [ ] Semantic search
- [ ] Add FAQs to knowledge base
- [ ] AI search knowledge base

**Output:** AI trả lời dựa trên knowledge base

---

### Requirement 3.6: Testing Phase 3 ⏱️ 4-6 giờ

**Checklist:**
- [ ] Test AI check inventory
- [ ] Test AI answer FAQs
- [ ] Test AI suggestions
- [ ] Test fallback to human
- [ ] Optimize prompts
- [ ] Fix bugs

**Output:** Phase 3 hoàn chỉnh

---

## 🎯 PHASE 4: Polish & Deploy

**Mục tiêu:** Hoàn thiện và deploy production

**Thời gian:** 1-2 tuần

---

### Requirement 4.1: SDK Development ⏱️ 6-8 giờ

**Checklist:**
- [ ] Tạo SDK package
- [ ] Client API wrapper
- [ ] Widget loader
- [ ] TypeScript definitions
- [ ] Documentation
- [ ] Publish to NPM

**Output:** SDK sẵn sàng cho shop khác dùng

---

### Requirement 4.2: Docker Setup ⏱️ 4-5 giờ

**Checklist:**
- [ ] Dockerfile cho backend
- [ ] Dockerfile cho dashboard
- [ ] Dockerfile cho widget
- [ ] Docker Compose production
- [ ] Environment variables
- [ ] Test local với Docker

**Output:** Chạy toàn bộ hệ thống bằng Docker

---

### Requirement 4.3: Documentation ⏱️ 4-6 giờ

**Checklist:**
- [ ] Installation guide
- [ ] Configuration guide
- [ ] API documentation
- [ ] SDK documentation
- [ ] Troubleshooting guide
- [ ] Video tutorials (optional)

**Output:** Tài liệu đầy đủ

---

### Requirement 4.4: Testing & QA ⏱️ 6-8 giờ

**Checklist:**
- [ ] End-to-end testing
- [ ] Performance testing
- [ ] Security audit
- [ ] Cross-browser testing
- [ ] Mobile responsive testing
- [ ] Fix all bugs

**Output:** Production-ready

---

### Requirement 4.5: Deployment ⏱️ 4-6 giờ

**Checklist:**
- [ ] Setup VPS/Cloud server
- [ ] Setup domain & SSL
- [ ] Deploy backend
- [ ] Deploy dashboard
- [ ] Deploy widget CDN
- [ ] Setup monitoring
- [ ] Backup strategy

**Output:** Hệ thống live trên production

---

## 📊 TỔNG KẾT

### Tổng thời gian ước tính:
- **Phase 1:** 40-50 giờ (2-3 tuần)
- **Phase 2:** 40-50 giờ (2-3 tuần)
- **Phase 3:** 30-40 giờ (2 tuần)
- **Phase 4:** 25-35 giờ (1-2 tuần)

**TỔNG:** 135-175 giờ (8-10 tuần nếu làm full-time)

---

## 🎯 CÁCH SỬ DỤNG CHECKLIST NÀY

1. **Làm tuần tự** từ Requirement 1.1 → 1.2 → 1.3...
2. **Đánh dấu ✅** khi hoàn thành mỗi item
3. **Commit code** sau mỗi requirement
4. **Test kỹ** trước khi chuyển requirement tiếp theo
5. **Hỏi tôi** nếu gặp khó khăn ở bất kỳ bước nào

---

## 🚀 SẴN SÀNG BẮT ĐẦU?

Hãy bắt đầu với **Requirement 1.1: Setup Backend Project**!

Bạn đã sẵn sàng chưa? 😊
