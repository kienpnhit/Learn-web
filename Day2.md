# 📚 Buổi 2: Table, Form input 

### 1. Nội dung chi tiết

# Inline và Block trong HTML

**Khái niệm**
- **Inline element**: Là phần tử hiển thị **trên cùng một dòng** với nội dung xung quanh. Nó chỉ chiếm không gian vừa đủ cho nội dung bên trong.
- **Block element**: Là phần tử **chiếm toàn bộ chiều ngang** của thẻ cha, đẩy nội dung tiếp theo xuống một dòng mới.

**Ví dụ**

### Inline elements
- `<span>`: dùng để bao bọc một đoạn text nhỏ.
- `<a>`: liên kết.
- `<strong>`, `<em>`: nhấn mạnh chữ.

### Block elements
- `<div>`: khối bao tổng quát.
- `<p>`: đoạn văn bản.
- `<h1> → <h6>`: tiêu đề.

### 2. Table

# Giới thiệu về Table

Trong **HTML**, thẻ `<table>` được dùng để hiển thị dữ liệu dưới dạng bảng.  
Một bảng cơ bản bao gồm:

- `<table>`: Khai báo bảng.
- `<tr>` (Table Row): Hàng trong bảng.
- `<th>` (Table Header): Ô tiêu đề (thường in đậm, canh giữa).
- `<td>` (Table Data): Ô dữ liệu.
- `colspan`: gộp cột
- `rowspan`: gộp hàng

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
```
# Giới thiệu HTML Form

HTML **form** dùng để thu thập dữ liệu từ người dùng và gửi về server.

## 1) Thẻ căn bản
- `<form>`: bao toàn bộ biểu mẫu.
- `<label>`: nhãn mô tả cho control (liên kết bằng `for` → `id`).
- `<input>`: nhiều loại điều khiển (text, email, file, …).
- `<select>` + `<option>` (+ `<optgroup>`): danh sách chọn.
- `<textarea>`: vùng nhập nhiều dòng.
- `<button>`: nút bấm (`type="submit" | "reset" | "button"`).
- `<fieldset>` & `<legend>`: nhóm và tiêu đề nhóm trường.

## 2) Thuộc tính quan trọng của `<form>` (Chưa cần ghi nhớ)
- `action`: URL nhận dữ liệu.
- `method`: phương thức gửi — `GET` (hiện query trên URL) / `POST` (gửi trong body).
- `enctype`: kiểu mã hoá dữ liệu, dùng khi upload file:
  - Mặc định: `application/x-www-form-urlencoded`
  - File: `multipart/form-data`
  - JSON (tuỳ backend): gửi qua JS `fetch`/XHR.
- `autocomplete="on|off"`: gợi ý tự động.
- `novalidate`: bỏ kiểm tra HTML5 (không khuyến nghị).

## 3) Thuộc tính hay dùng trên control
- Chung: `id`, `name` (tên trường khi submit), `value`, `required`, `disabled`, `readonly`, `placeholder`, `autocomplete`.
- Ràng buộc: `min`, `max`, `step`, `minlength`, `maxlength`, `pattern`.
- Khác:
  - `multiple` (nhiều giá trị: file, email, select).
  - `accept` (kiểu file cho `<input type="file">`).
  - `checked` (mặc định cho checkbox/radio).
  - `selected` (mặc định cho option).
 
  Đọc thêm tại link: https://www.w3schools.com/html/html_form_input_types.asp
    

## 4) Các `input type` thường gặp
- Văn bản: `text`, `password`, `email`, `search`, `tel`, `url`
- Số & phạm vi: `number`, `range`
- Ngày giờ: `date`, `time`, `datetime-local`, `month`, `week`
- Chọn lựa: `checkbox`, `radio`, `color`, `file`
- Hành động: `submit`, `reset`, `button`, `image`, `hidden`

## 5) Ví dụ nhanh (đầy đủ nhãn, ràng buộc, nhóm trường)
```html
<form action="/signup" method="POST" enctype="multipart/form-data" autocomplete="on">
  <fieldset>
    <legend>Thông tin tài khoản</legend>

    <label for="email">Email *</label>
    <input id="email" name="email" type="email" required placeholder="you@example.com" />

    <label for="pwd">Mật khẩu *</label>
    <input id="pwd" name="password" type="password" required minlength="8" />

    <label for="age">Tuổi</label>
    <input id="age" name="age" type="number" min="1" max="120" step="1" />

    <label for="avatar">Ảnh đại diện</label>
    <input id="avatar" name="avatar" type="file" accept="image/*" />
  </fieldset>

  <fieldset>
    <legend>Tùy chọn</legend>

    <p>Giới tính:</p>
    <label><input type="radio" name="gender" value="male" /> Nam</label>
    <label><input type="radio" name="gender" value="female" /> Nữ</label>

    <label for="skills">Kỹ năng</label>
    <select id="skills" name="skills[]" multiple>
      <option value="html">HTML</option>
      <option value="css">CSS</option>
      <option value="js">JavaScript</option>
    </select>

    <label for="bio">Giới thiệu</label>
    <textarea id="bio" name="bio" rows="3" placeholder="Tôi là..."></textarea>

    <label>
      <input type="checkbox" name="tos" required />
      Tôi đồng ý với điều khoản
    </label>
  </fieldset>

  <button type="submit">Đăng ký</button>
  <button type="reset">Làm lại</button>
</form>


