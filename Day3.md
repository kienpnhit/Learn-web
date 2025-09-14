# 📚 Buổi 2: Table, Form input 

### 1. Inline và Block trong HTML

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
```
### 3. Semantic HTML

# Bảng tóm tắt Semantic HTML

| Thẻ         | Ý nghĩa                                           | Ví dụ ngắn |
|-------------|---------------------------------------------------|------------|
| `<article>` | Khối nội dung **tự chứa**, độc lập (bài viết, card tin) | `<article><h2>Bài blog</h2><p>Nội dung...</p></article>` |
| `<aside>`   | Nội dung **phụ** (sidebar, liên kết liên quan)    | `<aside><h3>Bài liên quan</h3></aside>` |
| `<details>` | Khối có thể **mở/đóng** để ẩn/hiện nội dung       | `<details><summary>Xem thêm</summary><p>Chi tiết...</p></details>` |
| `<summary>` | Tiêu đề của `<details>`, bấm vào để mở/đóng        | *(dùng chung với `<details>`)* |
| `<figure>`  | Gói nội dung minh họa (ảnh, biểu đồ, code block) | `<figure><img src="a.png"><figcaption>Mô tả</figcaption></figure>` |
| `<figcaption>` | Chú thích cho `<figure>`                        | *(dùng kèm trong `<figure>`)* |
| `<footer>`  | Chân trang (trang hoặc khối nội dung)             | `<footer>© 2025 MySite</footer>` |
| `<header>`  | Phần đầu (tiêu đề, logo, meta) của trang hoặc khối| `<header><h1>Tech Blog</h1></header>` |
| `<main>`    | Nội dung **chính** của trang (chỉ có 1)           | `<main><h2>Bài nổi bật</h2></main>` |
| `<mark>`    | Tô sáng đoạn văn bản                              | `<p>Cẩn thận với <mark>XSS</mark></p>` |
| `<nav>`     | Vùng **điều hướng** (menu, breadcrumb)            | `<nav><a href="/">Home</a></nav>` |
| `<section>` | Nhóm nội dung theo **chủ đề**, có tiêu đề         | `<section><h2>Giới thiệu</h2><p>...</p></section>` |
| `<time>`    | Biểu diễn **thời gian** có thể máy hiểu           | `<time datetime="2025-09-14">14/09/2025</time>` |

Ví dụ:

```
<header>
  <h1>Tech Blog</h1>
  <nav aria-label="Chính">
    <a href="/">Trang chủ</a>
    <a href="/bai-viet">Bài viết</a>
    <a href="/lien-he">Liên hệ</a>
  </nav>
</header>

<main>
  <article>
    <header>
      <h2>Hiểu nhanh Semantic HTML</h2>
      <p>Xuất bản <time datetime="2025-09-14">14/09/2025</time></p>
    </header>

    <section>
      <h3>Tóm tắt</h3>
      <p>Dùng thẻ có ý nghĩa giúp <mark>SEO</mark> & Accessibility.</p>
    </section>

    <figure>
      <img src="semantic.png" alt="Cấu trúc semantic" />
      <figcaption>Bố cục header / main / footer.</figcaption>
    </figure>

    <details>
      <summary>Chi tiết kỹ thuật</summary>
      <p>Sử dụng <code>&lt;section&gt;</code> cho nhóm chủ đề,
         <code>&lt;article&gt;</code> cho khối tự chứa.</p>
    </details>

    <footer>
      <small>Tác giả: Kiên • <a href="/tac-gia/kien" rel="author">Hồ sơ</a></small>
    </footer>
  </article>

  <aside aria-label="Bài liên quan">
    <h3>Bạn có thể thích</h3>
    <ul>
      <li><a href="#">Heading đúng chuẩn</a></li>
      <li><a href="#">Alt text cho hình ảnh</a></li>
    </ul>
  </aside>
</main>

<footer>
  <small>© 2025 Tech Blog</small>
</footer>
```
# SEO và Semantic HTML

## `<header>` / `<footer>`
- **SEO**:  
  - `<header>` giúp công cụ tìm kiếm nhận diện **phần mở đầu** (logo, nav chính, tiêu đề).  
  - `<footer>` thường chứa liên kết phụ, thông tin liên hệ, bản quyền → Google đánh giá như "secondary content".  
- **Best practice**:  
  - Trong `<header>` đặt 1 **`<h1>` duy nhất** đại diện cho toàn trang.  
  - `<footer>` nên có **schema info** như `address`, `contact`.

---

## `<nav>`
- **SEO**:  
  - Giúp Googlebot dễ crawling, hiểu cấu trúc điều hướng.  
  - Anchor text trong `<nav>` quan trọng cho internal link SEO.  
- **Best practice**:  
  - Đặt menu chính trong `<nav>`.  
  - Dùng **text link** thay vì icon hoặc hình ảnh.  
  - Nếu có nhiều `<nav>` → thêm `aria-label` để phân biệt.

---

## `<main>`
- **SEO**:  
  - Nói cho Google biết đâu là **nội dung chính** của trang.  
  - Nội dung trong `<main>` có trọng số cao hơn so với aside/sidebar.  
- **Best practice**:  
  - Chỉ **1 `<main>` duy nhất**.  
  - Đặt bài viết, sản phẩm, nội dung chính bên trong.

---

## `<article>`
- **SEO**:  
  - Rất tốt cho blog/news/product → Google coi như **content unit độc lập**.  
  - Có thể hiển thị trong Google News/Discover nếu có metadata chuẩn.  
- **Best practice**:  
  - Mỗi `<article>` nên có `<h2>` tiêu đề riêng.  
  - Có thể chứa `<header>` và `<footer>` riêng.

---

## `<section>`
- **SEO**:  
  - Giúp phân chia nội dung **theo chủ đề**, hỗ trợ tạo **rich snippets** nếu có schema markup.  
- **Best practice**:  
  - Mỗi `<section>` nên có heading (`<h2>`, `<h3>`).  
  - Không lạm dụng (chỉ dùng khi có ý nghĩa rõ ràng).

---

## `<aside>`
- **SEO**:  
  - Nội dung trong `<aside>` bị coi là **phụ** (ads, related posts).  
  - Google hiểu là không phải core content.  
- **Best practice**:  
  - Dùng cho "Bài liên quan", "Tài liệu tham khảo".  
  - Không nhồi nhét từ khóa.

---

## `<h1>` … `<h6>`
- **SEO**:  
  - Rất quan trọng cho **cấu trúc nội dung**.  
  - `<h1>` là **tiêu đề chính** trang.  
  - Heading khác giúp Google hiểu dàn ý.  
- **Best practice**:  
  - Chỉ **1 `<h1>`/trang**.  
  - Dùng `<h2>`, `<h3>` theo cây logic, không nhảy cấp.

---

## `<figure>` / `<figcaption>` / `<img alt="">`
- **SEO**:  
  - Ảnh ảnh hưởng đến **Google Image Search**.  
  - `alt` text giúp Google hiểu nội dung ảnh.  
- **Best practice**:  
  - Mỗi `<img>` cần `alt` mô tả đúng.  
  - Nếu ảnh quan trọng → bọc `<figure>` + `<figcaption>`.

---

## `<time>`
- **SEO**:  
  - Giúp Google nhận diện **ngày đăng / cập nhật** → quan trọng cho News/Blog.  
- **Best practice**:  
  - Dùng `datetime="YYYY-MM-DD"`.  
  - Ví dụ: `<time datetime="2025-09-14">14/09/2025</time>`.

---

## `<mark>`
- **SEO**:  
  - Không ảnh hưởng trực tiếp, nhưng hỗ trợ **UX** khi highlight từ khóa.  
- **Best practice**:  
  - Dùng khi muốn nhấn mạnh keyword trên trang tìm kiếm nội bộ.

---

# Checklist SEO với Semantic HTML
- [x] Mỗi trang có **1 `<h1>` duy nhất**  
- [x] Nội dung chính nằm trong `<main>`  
- [x] Bài viết/blog dùng `<article>`  
- [x] Dùng heading hợp lý (H1 → H2 → H3)  
- [x] Hình ảnh có `alt` mô tả đúng, thêm `<figure>/<figcaption>` nếu cần  
- [x] Điều hướng chính đặt trong `<nav>`  
- [x] Dùng `<time>` cho ngày tháng rõ ràng  

---

👉 Semantic HTML không tự tăng SEO rank, nhưng giúp Google **hiểu cấu trúc**, dễ tạo **rich results** và cải thiện trải nghiệm người dùng.


