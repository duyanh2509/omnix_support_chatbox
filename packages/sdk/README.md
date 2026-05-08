# OmniSupport SDK

SDK giúp shop/doanh nghiệp tích hợp chatbox vào website của họ.

## SDK sẽ chứa gì?

### 1. **client.js** - Kết nối với API
```javascript
class OmniSupportClient {
  constructor(apiKey) {
    this.apiKey = apiKey
    this.baseURL = 'https://api.omnisupport.com'
  }

  // Gửi tin nhắn
  async sendMessage(message) {
    return fetch(`${this.baseURL}/messages`, {
      method: 'POST',
      headers: {
        'Authorization': `Bearer ${this.apiKey}`,
        'Content-Type': 'application/json'
      },
      body: JSON.stringify(message)
    })
  }

  // Lấy lịch sử chat
  async getHistory() { ... }
  
  // Upload file
  async uploadFile(file) { ... }
}
```

### 2. **widget.js** - Giao diện chatbox
```javascript
class ChatWidget {
  constructor(config) {
    this.position = config.position || 'bottom-right'
    this.color = config.color || '#0084ff'
  }

  // Tạo HTML chatbox
  render() {
    const widget = document.createElement('div')
    widget.innerHTML = `
      <div class="omnisupport-widget">
        <div class="chat-header">Chat với chúng tôi</div>
        <div class="chat-messages"></div>
        <input class="chat-input" placeholder="Nhập tin nhắn..." />
      </div>
    `
    document.body.appendChild(widget)
  }

  // Hiển thị tin nhắn
  showMessage(message) { ... }
  
  // Ẩn/hiện widget
  toggle() { ... }
}
```

### 3. **websocket.js** - Real-time messaging
```javascript
class WebSocketManager {
  connect(apiKey) {
    this.socket = io('wss://omnisupport.com', {
      auth: { token: apiKey }
    })

    // Lắng nghe tin nhắn mới
    this.socket.on('new_message', (msg) => {
      this.onMessageReceived(msg)
    })
  }
}
```

### 4. **index.js** - Entry point (file chính)
```javascript
// File này gộp tất cả lại
import Client from './client'
import Widget from './widget'
import WebSocket from './websocket'

const OmniSupport = {
  init(config) {
    const client = new Client(config.apiKey)
    const widget = new Widget(config)
    const ws = new WebSocket()
    
    widget.render()
    ws.connect(config.apiKey)
    
    // Kết nối các phần với nhau
    widget.onSendMessage = (msg) => {
      client.sendMessage(msg)
    }
    
    ws.onMessageReceived = (msg) => {
      widget.showMessage(msg)
    }
  }
}

export default OmniSupport
```

### 5. **styles.css** - Giao diện
```css
.omnisupport-widget {
  position: fixed;
  bottom: 20px;
  right: 20px;
  width: 350px;
  height: 500px;
  border-radius: 10px;
  box-shadow: 0 0 20px rgba(0,0,0,0.2);
}
```

### 6. **types.d.ts** - TypeScript definitions
```typescript
export interface OmniSupportConfig {
  apiKey: string
  position?: 'bottom-right' | 'bottom-left'
  color?: string
  language?: 'vi' | 'en'
}

export interface Message {
  id: string
  content: string
  sender: 'customer' | 'staff'
  timestamp: Date
}
```

---

## Mục đích của SDK?

### 🎯 Mục đích 1: Giúp khách hàng tích hợp DỄ DÀNG
Shop chỉ cần copy-paste 3 dòng code → Có ngay chatbox!

### 🎯 Mục đích 2: Che giấu độ phức tạp
Shop không cần biết:
- API endpoint nào
- WebSocket hoạt động thế nào
- Xử lý lỗi ra sao
- Format dữ liệu như thế nào

SDK lo hết!

### 🎯 Mục đích 3: Nhất quán
Tất cả shop dùng SDK → Cùng 1 cách hoạt động → Dễ support

### 🎯 Mục đích 4: Cập nhật dễ dàng
Bạn sửa bug/thêm tính năng → Shop chỉ cần update SDK:
```bash
npm update @omnisupport/sdk
```

---

## Cách shop sử dụng SDK?

### Cách 1: CDN (Đơn giản nhất)
```html
<script src="https://cdn.omnisupport.com/sdk.js"></script>
<script>
  OmniSupport.init({ apiKey: 'abc123' })
</script>
```

### Cách 2: NPM (Cho React/Vue/Angular)
```bash
npm install @omnisupport/sdk
```

```javascript
import OmniSupport from '@omnisupport/sdk'

OmniSupport.init({
  apiKey: 'abc123',
  position: 'bottom-right',
  color: '#ff0000',
  language: 'vi'
})
```

---

## Tóm lại

**SDK = Gói code đóng sẵn giúp người khác dùng sản phẩm của bạn cực kỳ dễ dàng**

Không có SDK → Shop phải code 1000 dòng
Có SDK → Shop chỉ cần 3 dòng!
