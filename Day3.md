# 📚 Giới thiệu về CSS

### 1. CSS là gì?

**CSS (Cascading Style Sheets)** là ngôn ngữ dùng để mô tả cách hiển thị của các phần tử HTML trên trang web.  
Nó cho phép bạn tách riêng phần **nội dung (HTML)** và phần **trình bày (CSS)**, giúp mã dễ bảo trì hơn.

## Tại sao cần CSS?

- 🎨 Tạo giao diện đẹp mắt: màu sắc, font chữ, layout.
- 📱 Hỗ trợ responsive: hiển thị tốt trên mọi thiết bị.
- ⚡ Giảm trùng lặp: thay đổi một nơi, áp dụng cho nhiều phần tử.
- 🛠️ Dễ bảo trì và mở rộng dự án.

## Cách nhúng CSS vào HTML

1. **Inline CSS** (trực tiếp trong thẻ HTML):
   ```html
   <p style="color: red;">Đoạn chữ này màu đỏ</p>
   ```
2. **Internal CSS** (trong thẻ <style>):
   ```html
   <style>
     p {
       color: blue;
     }
   </style>
   ```
3. **External CSS** (file .css riêng):
   ```html
   <link rel="stylesheet" href="styles.css">
   ```

## Cú pháp cơ bản
```css
selector {
  property: value;
}
```

Các khái niệm quan trọng

- Selector: chọn phần tử HTML (p, h1, .class, #id, …).

- Property: thuộc tính cần thay đổi (màu, kích thước, margin…).

- Value: giá trị áp dụng cho thuộc tính đó.

### 2. CSS Text
# CSS Text & Font

| Thuộc tính        | Nhóm      | Ý nghĩa / Công dụng                                           | Ví dụ                                       |
|--------------------|-----------|---------------------------------------------------------------|---------------------------------------------|
| `color`           | Text      | Đặt màu chữ                                                   | `p { color: red; }`                         |
| `text-align`      | Text      | Căn chỉnh văn bản: trái, phải, giữa, justify                   | `h1 { text-align: center; }`                |
| `text-decoration` | Text      | Trang trí chữ: gạch dưới, gạch ngang, bỏ gạch                  | `a { text-decoration: none; }`              |
| `text-transform`  | Text      | Biến đổi chữ: in hoa, in thường, viết hoa chữ cái đầu          | `p { text-transform: uppercase; }`          |
| `text-indent`     | Text      | Thụt đầu dòng đoạn văn                                        | `p { text-indent: 30px; }`                  |
| `letter-spacing`  | Text/Font | Khoảng cách giữa các ký tự                                    | `h1 { letter-spacing: 2px; }`               |
| `word-spacing`    | Text/Font | Khoảng cách giữa các từ                                       | `p { word-spacing: 10px; }`                 |
| `line-height`     | Text/Font | Độ cao dòng (giãn cách dòng)                                  | `p { line-height: 1.8; }`                   |
| `white-space`     | Text      | Quy định cách xử lý khoảng trắng                              | `pre { white-space: pre; }`                 |
| `text-shadow`     | Text      | Tạo bóng cho văn bản                                          | `h1 { text-shadow: 2px 2px 5px gray; }`     |
| `direction`       | Text      | Hướng văn bản: trái → phải (ltr) hoặc phải → trái (rtl)        | `p { direction: rtl; }`                     |
| `vertical-align`  | Text      | Căn chỉnh dọc cho văn bản trong dòng                          | `img { vertical-align: middle; }`           |
| `font-family`     | Font      | Chọn font chữ, có thể liệt kê nhiều font dự phòng              | `p { font-family: Arial, sans-serif; }`     |
| `font-size`       | Font      | Kích thước chữ (px, em, rem, %)                               | `h1 { font-size: 24px; }`                   |
| `font-weight`     | Font      | Độ đậm nhạt (normal, bold, 100–900)                          | `h2 { font-weight: bold; }`                 |
| `font-style`      | Font      | Kiểu chữ: nghiêng, bình thường                                | `em { font-style: italic; }`                |
| `font-variant`    | Font      | Kiểu hiển thị chữ hoa nhỏ (small-caps)                       | `p { font-variant: small-caps; }`           |
| `font` (shorthand)| Font      | Viết gọn nhiều thuộc tính font trong 1 dòng                   | `p { font: italic bold 16px/1.5 Arial; }`   |


**Link đọc thêm:** https://www.w3schools.com/css/css_text.asp

# So sánh đơn vị CSS: px, em, rem, %

| Đơn vị | Tham chiếu                | Ưu điểm                                    | Nhược điểm                                | Ví dụ                                                                 |
|--------|---------------------------|--------------------------------------------|-------------------------------------------|----------------------------------------------------------------------|
| `px`   | Pixel thật trên màn hình  | Cố định, dễ kiểm soát, chính xác           | Không responsive, không co giãn            | `p { font-size: 16px; }` (luôn 16px)                                 |
| `em`   | Font-size của **cha**     | Linh hoạt, dễ tạo tỉ lệ so với cha         | Cộng dồn nhiều cấp gây khó kiểm soát       | `p { font-size: 1.5em; }` (cha 20px → con 30px)                      |
| `rem`  | Font-size của **root** (`html`) | Ổn định, dễ quản lý toàn cục             | Phụ thuộc cấu hình `html`                  | `h1 { font-size: 2rem; }` (`html` 16px → 32px)                       |
| `%`    | Tùy thuộc ngữ cảnh (cha)  | Rất linh hoạt (layout responsive)          | Dễ nhầm vì phụ thuộc thuộc tính cha        | `div { width: 50%; }` (cha 800px → con 400px)<br>`p { font-size: 150%; }` (cha 20px → con 30px) |

### 3. Class & ID
## 1) Khái niệm
- **class**: Nhãn *có thể dùng cho nhiều phần tử*. Dùng để nhóm các phần tử có cùng kiểu.
- **id**: Định danh *duy nhất trên trang* (mỗi id chỉ nên xuất hiện **1 lần**).

## 2) Cú pháp HTML
```html
<div class="card primary">Thẻ có 2 class</div>
<div id="header">Phần đầu trang</div
```

Ghi theo dạng **a-b-c-d**:
- !important
- a = inline style  
- b = số **ID**  
- c = số **class/attribute/pseudo-class** (`.a`, `[type]`, `:hover`, `:has()`, `:is()`…)  
- d = số **type/pseudo-element** (`div`, `h1`, `::before`…)


