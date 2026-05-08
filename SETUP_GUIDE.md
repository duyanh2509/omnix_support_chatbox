# 🚀 Hướng dẫn Setup môi trường

## Bước 1: Kiểm tra Node.js

Mở terminal và chạy:
```bash
node --version
```

**Yêu cầu:** Node.js >= 20.0.0

**Nếu chưa có Node.js:**
- Tải tại: https://nodejs.org/
- Chọn phiên bản LTS (Long Term Support)
- Cài đặt và restart terminal

---

## Bước 2: Cài đặt pnpm

pnpm là package manager nhanh hơn npm.

### Cách 1: Dùng npm (đã có sẵn khi cài Node.js)
```bash
npm install -g pnpm
```

### Cách 2: Dùng PowerShell (Windows)
```powershell
iwr https://get.pnpm.io/install.ps1 -useb | iex
```

### Kiểm tra:
```bash
pnpm --version
```

**Yêu cầu:** pnpm >= 8.0.0

---

## Bước 3: Cài đặt dependencies

Trong thư mục project:
```bash
cd C:\Users\Admin\Desktop\Omnix\omnix_support_chatbox
pnpm install
```

**Lưu ý:** Lần đầu sẽ mất 2-5 phút để tải tất cả packages.

---

## Bước 4: Chạy backend

```bash
pnpm dev:backend
```

**Kết quả mong đợi:**
```
🚀 Backend is running on: http://localhost:3000/api
```

---

## Bước 5: Test API

### Cách 1: Dùng trình duyệt
Mở: http://localhost:3000/api/health

### Cách 2: Dùng curl
```bash
curl http://localhost:3000/api/health
```

### Cách 3: Dùng Thunder Client (VS Code extension)
- Cài extension "Thunder Client"
- New Request
- GET http://localhost:3000/api/health
- Send

**Response mong đợi:**
```json
{
  "status": "ok",
  "timestamp": "2026-05-09T...",
  "service": "OmniSupport Backend",
  "version": "0.1.0"
}
```

---

## ❌ Xử lý lỗi thường gặp

### Lỗi: "Cannot find module '@nestjs/core'"
**Nguyên nhân:** Chưa chạy `pnpm install`

**Giải pháp:**
```bash
pnpm install
```

### Lỗi: "pnpm: command not found"
**Nguyên nhân:** Chưa cài pnpm

**Giải pháp:**
```bash
npm install -g pnpm
```

### Lỗi: "Port 3000 already in use"
**Nguyên nhân:** Có app khác đang dùng port 3000

**Giải pháp 1:** Tắt app đang dùng port 3000

**Giải pháp 2:** Đổi port trong `.env`:
```env
PORT=3001
```

### Lỗi: "node: command not found"
**Nguyên nhân:** Chưa cài Node.js

**Giải pháp:** Tải và cài Node.js từ https://nodejs.org/

---

## 📝 Checklist Setup

- [ ] Node.js đã cài (>= 20.0.0)
- [ ] pnpm đã cài (>= 8.0.0)
- [ ] Đã chạy `pnpm install`
- [ ] Backend chạy được: `pnpm dev:backend`
- [ ] API health check trả về OK

---

## 🆘 Cần trợ giúp?

Nếu gặp lỗi khác, hãy:
1. Copy toàn bộ error message
2. Chụp màn hình
3. Gửi cho tôi để debug
