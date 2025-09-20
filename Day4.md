# 📚 Giới thiệu vỀ CSS

### 3. Height & Width

| Thuộc tính   | Ý nghĩa                               | Giá trị thường dùng                                                           | Mặc định | Quy tắc kẹp                        | Lưu ý/Gotcha                                                         | Ví dụ nhanh                                      |
| ------------ | ------------------------------------- | ----------------------------------------------------------------------------- | -------- | ---------------------------------- | -------------------------------------------------------------------- | ------------------------------------------------ |
| `width`      | Độ **rộng mong muốn** của phần tử     | `px`, `%`, `rem`, `vw`, `auto`, `fit-content()`, `min/max-content`, `clamp()` | `auto`   | `min-width ≤ width ≤ max-width`    | Có thể gây tràn trên màn nhỏ nếu đặt cố định (px)                    | `.box { width: 600px; }`                         |
| `max-width`  | **Trần** cho độ rộng (không vượt quá) | `px`, `%`, `rem`, `vw`, `none`                                                | `none`   | Ép `width` không vượt trần         | Thân thiện responsive khi kết hợp `width: 100%`                      | `.container { width: 100%; max-width: 1200px; }` |
| `min-width`  | **Sàn** cho độ rộng (không nhỏ hơn)   | `px`, `%`, `rem`                                                              | `auto`   | Ép `width` không thấp hơn sàn      | Trong **flex**, dùng `min-width: 0` để cho phép co và tránh tràn chữ | `.col { flex: 1; min-width: 0; }`                |
| `height`     | Độ **cao mong muốn** của phần tử      | `px`, `%`, `rem`, `vh`, `auto`, `fit-content()`, `min/max-content`, `clamp()` | `auto`   | `min-height ≤ height ≤ max-height` | `%` chỉ hoạt động nếu **cha có height xác định**                     | `.hero { height: 60vh; }`                        |
| `max-height` | **Trần** cho độ cao                   | `px`, `%`, `vh`, `none`                                                       | `none`   | Ép `height` không vượt trần        | Thường đi kèm `overflow: auto` để bật cuộn                           | `.panel { max-height: 320px; overflow: auto; }`  |
| `min-height` | **Sàn** cho độ cao                    | `px`, `%`, `vh`                                                               | `auto`   | Ép `height` không thấp hơn sàn     | Dùng `min-height: 0` cho item trong **flex/grid** để cho phép co     | `.section { min-height: 100vh; }`                |


### 4. Background

| Thuộc tính                   | Mô tả                       | Giá trị chính (ví dụ)                                                                    | Mặc định                | Ghi chú / Ví dụ ngắn                                                                                                                                                   |
| ---------------------------- | --------------------------- | ---------------------------------------------------------------------------------------- | ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `background` (shorthand)     | Viết gộp các thuộc tính nền | `background: <color> <image> <position> / <size> <repeat> <origin> <clip> <attachment>;` | tùy từng thuộc tính con | Thứ tự linh hoạt, riêng `size` phải đi sau `position` và ngăn bằng `/`. *Ví dụ*: `background: #f6f url(bg.png) center / cover no-repeat border-box padding-box fixed;` |
| `background-color`           | Trong suốt                     | `transparent`, `#fff`, `rgb()`, `hsl()`                                                  | `transparent`           | Lớp dưới cùng khi có nhiều lớp nền                                                                                                                                     |
| `background-image`           | Ảnh/gradient nền            | `url("img.png")`, `linear-gradient(...)`, `none`                                         | `none`                  | Hỗ trợ **nhiều lớp**: `url(a), linear-gradient(...)` (lớp đầu vẽ **trên** cùng)                                                                                        |
| `background-position`        | Vị trí đặt ảnh nền          | `left top`, `center`, `right 20px bottom 10px`, `50% 50%`                                | `0% 0%`                 | Có thể dùng 1–2 từ khóa hoặc length/percent. Với 3–4 giá trị có thể chỉ định trục cụ thể                                                                               |
| `background-size`            | Kích thước ảnh nền          | `auto`, `<length>`, `<percent>`, `cover`, `contain`                                      | `auto auto`             | Trong shorthand: viết `position / size` → `center / cover`                                                                                                             |
| `background-repeat`          | Lặp ảnh nền                 | `repeat`, `no-repeat`, `repeat-x`, `repeat-y`, `space`, `round`                          | `repeat`                | Với nhiều lớp có thể đặt riêng từng giá trị, ngăn bằng dấu phẩy                                                                                                        |
| `background-attachment`      | Cách cuộn của nền           | `scroll`, `fixed`, `local`                                                               | `scroll`                | `fixed` ghim theo viewport; cẩn trọng hiệu năng trên mobile                                                                                                            |
| `background-origin`          | Gốc tính vị trí nền         | `border-box`, `padding-box`, `content-box`                                               | `padding-box`           | Ảnh hưởng đến **position** và **size**                                                                                                                                 |
| `background-clip`            | Phạm vi tô nền              | `border-box`, `padding-box`, `content-box`, `text`\*                                     | `border-box`            | `background-clip: text` thường cần `-webkit-background-clip: text` + `color: transparent`                                                                              |
| `background-blend-mode`      | Cách trộn giữa các lớp nền  | `multiply`, `screen`, `overlay`, …                                                       | `normal`                | Áp dụng khi có **nhiều lớp** (màu + ảnh/gradient)                                                                                                                      |
| `background-image: gradient` | Gradient như ảnh nền        | `linear-gradient(45deg, red, blue)`, `radial-gradient(...)`, `conic-gradient(...)`       | —                       | Là **ảnh nền tạo bởi CSS**, kết hợp được với các lớp khác                                                                                                              |

### Border

| Thuộc tính                      | Ý nghĩa                           | Giá trị thường dùng                                                                 | Ghi chú / Mẹo                                                     |
| ------------------------------- | --------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| `border` (shorthand)            | Gộp **width style color**         | `1px solid #ddd`                                                                    | Thứ tự: `width` → `style` → `color` (có thể đảo, miễn đúng loại). |
| `border-width`                  | Độ dày viền                       | `thin`, `medium`, `thick`, `0`, `2px`, `0.25rem`                                    | Ảnh hưởng kích thước hộp (trừ khi `box-sizing: border-box`).      |
| `border-style`                  | Kiểu viền                         | `none`, `solid`, `dashed`, `dotted`, `double`, `groove`, `ridge`, `inset`, `outset` | Nếu `style: none`, viền không hiển thị dù có `width/color`.       |
| `border-color`                  | Màu viền                          | `#000`, `rgb()`, `hsl()`, `transparent`, `currentColor`                             | Có thể set 1–4 giá trị (trên–phải–dưới–trái).                     |
| `border-top/right/bottom/left`  | Viền từng cạnh (shorthand)        | `border-top: 2px dashed red;`                                                       | Có phiên bản chi tiết: `border-top-width/style/color`.            |
| `border-block`, `border-inline` | Viền theo **trục writing-mode**   | `border-block: 1px solid;`                                                          | Hữu ích cho i18n (dọc/ngang). Có `*-start`, `*-end`.              |
| `border-radius`                 | Bo góc                            | `8px`, `50%`, `8px 16px`, `8px/16px`                                                | 1–4 giá trị; dùng `50%` để tạo tròn/oval (kèm `width=height`).    |
| `border-start-start-radius`…    | Bo góc theo trục logic            | `12px`                                                                              | Thay thế `border-top-left-radius` theo writing-mode.              |
| `border-image` (shorthand)      | Dùng ảnh/gradient làm viền        | `border-image: url(frame.png) 30 fill / 10px round;`                                | Cần **`border-style` ≠ `none`** (ví dụ `solid`) để hiển thị.      |
| `outline` (liên quan)           | Viền ngoài **không chiếm layout** | `outline: 2px solid blue;`                                                          | Dùng cho focus/khả năng truy cập; **khác** `border`.              |
| `box-sizing` (liên quan)        | Cách tính kích thước              | `content-box` \| `border-box`                                                       | Với `border-box`, `width/height` **đã gồm** border & padding.     |
| `background-clip` (liên quan)   | Phạm vi nền                       | `border-box` \| `padding-box` \| `content-box`                                      | Tránh nền “đổ” dưới viền khi cần.                                 |

### 5. Margin & Padding
**Khái niệm**
- Padding: khoảng đệm bên trong phần tử — giữa nội dung và viền (border).
- Margin: khoảng trống bên ngoài phần tử — giữa viền của nó và phần tử/biên xung quanh.

|<--------- margin --------->|
[  border  [   padding   [content]   ]  border  ]
|<---------------- element box ---------------->|

**So sánh**

| Tiêu chí                   | Padding                                | Margin                                     |
| -------------------------- | -------------------------------------- | ------------------------------------------ |
| Vị trí                     | Bên **trong** border                   | Bên **ngoài** border                       |
| Ảnh hưởng nền (background) | **Có**: background “tràn” vào padding  | **Không**: background không phủ margin     |
| Có thể âm (negative)       | ❌ Không                                | ✅ Có (ví dụ `margin-top: -8px`)            |
| Ảnh hưởng layout           | Tăng kích thước hộp (trừ `border-box`) | Tạo khoảng cách với xung quanh             |
| Tác dụng căn giữa          | ❌                                      | ✅ `margin: 0 auto` (khối có width cố định) |
| Collapsing (chồng lấn)     | ❌ Không                                | ✅ Có trên trục dọc giữa các block          |

**CÚ pháp**

```
/* Shorthand: 1–4 giá trị (top right bottom left) */
.box { padding: 16px; }              /* 4 cạnh */
.box { padding: 8px 12px; }          /* trên-dưới | trái-phải */
.box { padding: 8px 12px 20px; }     /* trên | trái-phải | dưới */
.box { padding: 8px 12px 20px 4px; } /* trên | phải | dưới | trái */

/* Từng cạnh */
.box { padding-top: 12px; padding-inline-start: 1rem; } /* logical props */
```

```
/* Shorthand: 1–4 giá trị */
.card { margin: 24px; }
.card { margin: 0 16px; }
.card { margin: 8px 16px 24px; }
.card { margin: 4px 8px 12px 16px; }

/* Từng cạnh */
.card { margin-bottom: 12px; margin-inline: auto; } /* logical props */

/* Căn giữa khối có width cố định */
.container { width: 600px; margin: 0 auto; }
```
