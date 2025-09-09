# 📚 Buổi 1: Table, Form input & Layout trong HTML

## 📝 Nội dung chi tiết

### 1. Table

# Giới thiệu về Table

Trong **HTML**, thẻ `<table>` được dùng để hiển thị dữ liệu dưới dạng bảng.  
Một bảng cơ bản bao gồm:

- `<table>`: Khai báo bảng.
- `<tr>` (Table Row): Hàng trong bảng.
- `<th>` (Table Header): Ô tiêu đề (thường in đậm, canh giữa).
- `<td>` (Table Data): Ô dữ liệu.

---

## Ví dụ cơ bản

```html
<table border="1">
  <tr>
    <th>Tên</th>
    <th>Tuổi</th>
    <th>Thành phố</th>
  </tr>
  <tr>
    <td>Lan</td>
    <td>20</td>
    <td>Hà Nội</td>
  </tr>
  <tr>
    <td>Minh</td>
    <td>25</td>
    <td>Đà Nẵng</td>
  </tr>
</table>

### 2. Website tĩnh vs động - **Static website**: chỉ HTML/CSS/JS → nội dung cố
định - **Dynamic website**: backend xử lý dữ liệu → nội dung thay đổi 👉 Ví dụ:
- Tĩnh: portfolio cá nhân - Động: Facebook, Shopee --- ### 3. 3 ngôn ngữ
frontend - **HTML (Nouns)**: nội dung trang web - **CSS (Adjectives)**: định
dạng, màu sắc, bố cục - **JavaScript (Verbs)**: hành động, sự kiện, logic ---
### 4. Cài đặt VS Code - **Tải và cài đặt**: Truy cập
https://code.visualstudio.com - **Cài Extensions cần thiết**: - Live Server (by
Ritwick Dey) → chạy web trực tiếp - Prettier → format code đẹp - HTML CSS
Support → gợi ý code - Auto Rename Tag → đổi tên thẻ tự động - **Tạo dự án đầu
tiên**: - Tạo thư mục `my-first-website` - Tạo file `index.html` với nội dung
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

Đây là cấu trúc 1 file html.

- Chạy với Live Server

### 5.HTML là gì?

HTML (HyperText Markup Language) là ngôn ngữ đánh dấu siêu văn bản – dùng để tạo cấu trúc và nội dung của trang web.

- Không phải ngôn ngữ lập trình.
- Giống như bộ khung hoặc bản vẽ kiến trúc của ngôi nhà website.
- Trình duyệt (Chrome, Edge, Firefox…) sẽ đọc mã HTML và hiển thị ra thành văn bản, hình ảnh, nút bấm, video…

Cấu tạo của 1 phần tử html:
Thẻ mở -> nội dung -> thẻ đóng

Các thẻ HTML cơ bản:

- Khai báo <!DOCTYPE> cho HTML5
- `<html>` Phần tử gốc định nghĩa toàn bộ tài liệu
- `<head>` chứa thông tin meta về trang HTML
- `<body>` nội dung trang web
- `<title>` Tiêu đề trang
- `<h1> -> <h6>` định nghĩa tiêu đề
- `<p>` định nghĩa đoạn văn
- `<span>` định nghĩa 1 phần đoạn văn
- `<a>` định nghĩa đường dẫn
  `<a href="https://google.com">This is a link</a>`
- Hình ảnh HTML được định nghĩa bằng thẻ `<img>`
  `<img src="w3schools.jpg" alt="abc.com" width="104" height="142">`
- `<button>` nút bấm
- Bảng

```
<table>
  <tr>
    <td>Emil</td>
    <td>Tobias</td>
    <td>Linus</td>
  </tr>
  <tr>
    <td>16</td>
    <td>14</td>
    <td>10</td>
  </tr>
</table>
```

- Danh sách

```
ul>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
```

ul ko có thứ tự, ol có thứ tự

- `<div>` đại diện 1 vùng chứa

## Comment trong html

`<!-- Write your comments here -->`

## 📌 Các thẻ định dạng văn bản trong HTML

- `<b>` → **Bold text** = **Chữ in đậm** (chỉ để trang trí, không nhấn mạnh ý nghĩa)
- `<strong>` → **Important text** = **Chữ quan trọng** (in đậm + có ý nghĩa nhấn mạnh, tốt cho SEO & screen reader)

- `<i>` → _Italic text_ = _Chữ in nghiêng_ (chỉ để trang trí)
- `<em>` → _Emphasized text_ = _Chữ nhấn mạnh_ (in nghiêng + có ý nghĩa nhấn mạnh, tốt cho SEO & screen reader)

- `<mark>` → ==Marked text== = **Chữ được đánh dấu (highlight)**

- `<small>` → Smaller text = **Chữ nhỏ hơn**

- `<del>` → ~~Deleted text~~ = **Chữ bị gạch bỏ** (nội dung đã xóa)
- `<ins>` → Inserted text = **Chữ được chèn thêm** (thường gạch chân)

- `<sub>` → Subscript text = **Chữ dưới dòng** (ví dụ: H₂O)
- `<sup>` → Superscript text = **Chữ trên dòng** (ví dụ: x²)

## 📌 Thuộc tính `target` trong thẻ `<a>`

Thuộc tính **`target`** xác định nơi mở tài liệu khi click vào liên kết.

## 🔹 Các giá trị của `target`

- **`_self`** (mặc định)  
  👉 Mở link trong **cùng cửa sổ/tab hiện tại**.

- **`_blank`**  
  👉 Mở link trong **cửa sổ hoặc tab mới**.

- **`_parent`**  
  👉 Mở link trong **khung cha (parent frame)**.  
  (Thường dùng khi trang có nhiều frame lồng nhau.)

- **`_top`**  
  👉 Mở link trong **toàn bộ cửa sổ trình duyệt**, thay thế toàn bộ frame.
