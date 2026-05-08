# Yêu cầu dự án OmniSupport

## 🎯 BÀI TOÁN THỰC TẾ

### Vấn đề hiện tại:
Bạn có 1 website bán hàng, khách hàng nhắn tin qua nhiều kênh:
- 📱 Zalo
- 💬 Facebook Messenger  
- 📷 Instagram Direct
- 🌐 Website chat

**Khó khăn:**
- Phải mở 4 app khác nhau để trả lời
- Dễ bỏ sót tin nhắn
- Mất thời gian chuyển qua chuyển lại
- Không theo dõi được tổng thể

---

## ✅ GIẢI PHÁP: OmniSupport

### Tính năng chính:

#### 1. **Unified Inbox** (Hộp thư tổng hợp)
```
┌─────────────────────────────────────┐
│  Dashboard của bạn                  │
│                                     │
│  📥 Tất cả tin nhắn                 │
│  ├─ 💬 Nguyễn Văn A (Facebook)     │
│  ├─ 📱 Trần Thị B (Zalo)           │
│  ├─ 📷 Lê Văn C (Instagram)        │
│  └─ 🌐 Phạm Thị D (Website)        │
│                                     │
│  → Trả lời tất cả tại 1 nơi!       │
└─────────────────────────────────────┘
```

#### 2. **Real-time Messaging** (Tin nhắn thời gian thực)
- Tin nhắn mới → Hiện ngay lập tức
- Không cần refresh trang
- Thông báo desktop

#### 3. **AI Chatbot** (Trợ lý AI)

**Ví dụ 1: Check tồn kho**
```
Khách: "Áo thun trắng size M còn không?"
AI: [Tự động check database]
AI: "Dạ còn ạ, shop còn 15 cái size M. 
     Giá 199k. Anh/chị đặt hàng không ạ?"
```

**Ví dụ 2: Hỏi giá**
```
Khách: "Quần jean này giá bao nhiêu?"
AI: [Check database]
AI: "Dạ quần jean này giá 450k ạ. 
     Đang có khuyến mãi giảm 10% còn 405k."
```

**Ví dụ 3: Hỏi phức tạp → Chuyển người**
```
Khách: "Tôi muốn đổi hàng đã mua"
AI: "Dạ, để shop hỗ trợ anh/chị tốt hơn, 
     cho em chuyển sang nhân viên ạ."
→ Chuyển cho bạn xử lý
```

#### 4. **Multi-platform Integration**
```
Website của bạn
    ↓
OmniSupport Backend
    ↓
├─ Facebook API → Nhận/gửi tin Facebook
├─ Instagram API → Nhận/gửi tin Instagram  
├─ Zalo API → Nhận/gửi tin Zalo
└─ Website Widget → Chat trực tiếp
```

#### 5. **Open-source & Easy Integration**

**Shop khác muốn dùng:**

```bash
# Bước 1: Clone từ GitHub
git clone https://github.com/duyanh2509/omnix_support_chatbox.git

# Bước 2: Cài đặt
cd omnix_support_chatbox
docker compose up

# Bước 3: Cấu hình
# Điền API keys (Facebook, Zalo, Instagram)
# Kết nối database của shop

# Bước 4: Nhúng widget vào website
<script src="http://your-domain.com/widget.js"></script>
<script>
  OmniSupport.init({ apiKey: 'shop-key' })
</script>

# XONG! ✅
```

---

## 🏗️ KIẾN TRÚC HỆ THỐNG

### Tổng quan:
```
┌──────────────────────────────────────────────────┐
│              KHÁCH HÀNG                          │
│  Facebook | Instagram | Zalo | Website          │
└──────────────────────────────────────────────────┘
                    ↓ ↓ ↓ ↓
┌──────────────────────────────────────────────────┐
│         OMNISUPPORT BACKEND (NestJS)             │
│  ┌────────────────────────────────────────────┐  │
│  │  Integration Layer                         │  │
│  │  ├─ Facebook Adapter                       │  │
│  │  ├─ Instagram Adapter                      │  │
│  │  ├─ Zalo Adapter                           │  │
│  │  └─ Website Adapter                        │  │
│  └────────────────────────────────────────────┘  │
│                    ↓                             │
│  ┌────────────────────────────────────────────┐  │
│  │  Business Logic                            │  │
│  │  ├─ Conversation Management                │  │
│  │  ├─ Message Processing                     │  │
│  │  └─ AI Orchestration                       │  │
│  └────────────────────────────────────────────┘  │
│                    ↓                             │
│  ┌────────────────────────────────────────────┐  │
│  │  AI Layer                                  │  │
│  │  ├─ OpenAI GPT                             │  │
│  │  ├─ Inventory Service (Check kho)          │  │
│  │  ├─ Product Service (Thông tin sản phẩm)   │  │
│  │  └─ Order Service (Đơn hàng)               │  │
│  └────────────────────────────────────────────┘  │
│                    ↓                             │
│  ┌────────────────────────────────────────────┐  │
│  │  Database Layer                            │  │
│  │  ├─ PostgreSQL (Messages, Users, Products) │  │
│  │  ├─ Redis (Cache, Sessions)                │  │
│  │  └─ Vector DB (AI Knowledge Base)          │  │
│  └────────────────────────────────────────────┘  │
└──────────────────────────────────────────────────┘
                    ↓ WebSocket
┌──────────────────────────────────────────────────┐
│         DASHBOARD (Next.js)                      │
│  Bạn xem và trả lời tin nhắn tại đây            │
└──────────────────────────────────────────────────┘
```

---

## 📦 CÁC THÀNH PHẦN

### 1. Backend API (apps/backend)
- **Ngôn ngữ:** TypeScript + NestJS
- **Database:** PostgreSQL + Prisma
- **Cache:** Redis
- **Real-time:** Socket.IO
- **AI:** OpenAI API + LangChain

### 2. Admin Dashboard (apps/dashboard)
- **Framework:** Next.js 14
- **UI:** TailwindCSS + Shadcn UI
- **State:** Zustand
- **Real-time:** Socket.IO Client

### 3. Chat Widget (apps/widget)
- **Framework:** React + Vite
- **UI:** TailwindCSS
- **Size:** < 100KB (optimized)

### 4. SDK (packages/sdk)
- **Mục đích:** Giúp shop khác tích hợp dễ dàng
- **Format:** NPM package + CDN

---

## 🚀 LỘ TRÌNH PHÁT TRIỂN

### Phase 1: Foundation (2-3 tuần)
- [ ] Setup NestJS backend
- [ ] Setup PostgreSQL + Prisma
- [ ] Authentication (JWT)
- [ ] Website chat widget
- [ ] Basic dashboard

**Kết quả:** Chat widget hoạt động trên website

---

### Phase 2: Multi-platform (3-4 tuần)
- [ ] Facebook Messenger integration
- [ ] Instagram Direct integration
- [ ] Zalo OA integration
- [ ] Unified inbox UI

**Kết quả:** Nhận tin từ 3 nền tảng vào 1 dashboard

---

### Phase 3: AI Chatbot (2-3 tuần)
- [ ] OpenAI integration
- [ ] Inventory check function
- [ ] Product info function
- [ ] Auto-reply logic

**Kết quả:** AI tự trả lời câu hỏi đơn giản

---

### Phase 4: Polish & Deploy (1-2 tuần)
- [ ] Docker setup
- [ ] Documentation
- [ ] Testing
- [ ] Deploy to production

**Kết quả:** Sẵn sàng cho production

---

## 💰 CHI PHÍ DỰ KIẾN

### Phát triển:
- **Tự làm:** 0đ (chỉ mất thời gian 3-4 tháng)
- **Thuê dev:** 50-100 triệu VNĐ

### Vận hành hàng tháng:
- **Server:** 500k - 2 triệu/tháng (tùy traffic)
- **OpenAI API:** 200k - 1 triệu/tháng (tùy số tin nhắn)
- **Domain:** 200k/năm

---

## 🎯 KẾT QUẢ MONG ĐỢI

### Sau khi hoàn thành:
1. ✅ Bạn có 1 hệ thống quản lý tin nhắn tập trung
2. ✅ AI tự động trả lời 60-70% câu hỏi đơn giản
3. ✅ Tiết kiệm 3-4 giờ/ngày
4. ✅ Không bỏ sót tin nhắn khách hàng
5. ✅ Shop khác có thể tải về và dùng
6. ✅ Có thể bán như 1 sản phẩm SaaS

---

## 📞 HỖ TRỢ

Nếu cần hỗ trợ trong quá trình phát triển:
- GitHub Issues: https://github.com/duyanh2509/omnix_support_chatbox/issues
- Email: duyanh2509@gmail.com
