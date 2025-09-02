# 📚 Buổi 1: Giới thiệu & Cài đặt môi trường học lập trình Web  

## 📝 Nội dung chi tiết

### Điều gì xảy ra khi bạn ấn vào 1 link website

Nhận link ->  Trình duyệt gửi yêu cầu tới server chưa web theo địa chỉ -> lấy các file tạo web gửi lại cho trình duyệt -> trình duyệt dịch file hiển thị web


### 1. Giới thiệu tổng quan Web Development
- **Frontend**: giao diện, trải nghiệm người dùng → HTML, CSS, JS  
- **Backend**: máy chủ, cơ sở dữ liệu, logic → Node, PHP, Java, Python...  

📌 Ví dụ:  
- Frontend = menu và bàn ghế trong nhà hàng  
- Backend = bếp nấu ăn và kho nguyên liệu  

---

### 2. Website tĩnh vs động
- **Static website**: chỉ HTML/CSS/JS → nội dung cố định  
- **Dynamic website**: backend xử lý dữ liệu → nội dung thay đổi  

👉 Ví dụ:  
- Tĩnh: portfolio cá nhân  
- Động: Facebook, Shopee  

---

### 3. 3 ngôn ngữ frontend
- **HTML (Nouns)**: nội dung trang web  
- **CSS (Adjectives)**: định dạng, màu sắc, bố cục  
- **JavaScript (Verbs)**: hành động, sự kiện, logic

---

### 4. Cài đặt VS Code
- **Tải và cài đặt**:
  Truy cập https://code.visualstudio.com
- **Cài Extensions cần thiết**:  
  - Live Server (by Ritwick Dey) → chạy web trực tiếp  
  - Prettier → format code đẹp  
  - HTML CSS Support → gợi ý code  
  - Auto Rename Tag → đổi tên thẻ tự động
- **Tạo dự án đầu tiên**:
  -  Tạo thư mục `my-first-website`
  -  Tạo file `index.html` với nội dung
 
```
  <!DOCTYPE html>
  <html>
    <head>
      <meta charset="UTF-8">
      <title>Website đầu tiên</title>
    </head>
    <body>
      <h1>Hello World!</h1>
      <p>Tôi đang học HTML, CSS và JavaScript.</p>
    </body>
  </html>
```
  -  Chạy với Live Server

 ### 5.HTML là gì?
 HTML (HyperText Markup Language) là ngôn ngữ đánh dấu siêu văn bản – dùng để tạo cấu trúc và nội dung của trang web.
 - Không phải ngôn ngữ lập trình.
 - Giống như bộ khung hoặc bản vẽ kiến trúc của ngôi nhà website.
 - Trình duyệt (Chrome, Edge, Firefox…) sẽ đọc mã HTML và hiển thị ra thành văn bản, hình ảnh, nút bấm, video…

 Cấu tạo của 1 phần tử html: 
 Thẻ mở -> nội dung -> thẻ đóng

