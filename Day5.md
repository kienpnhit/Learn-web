
# 📚 Giới thiệu về CSS Layout

### 1. Flex box

# Giới thiệu về Flexbox

**Flexbox** (Flexible Box Layout Module) là một cơ chế bố cục trong CSS, giúp sắp xếp, căn chỉnh và phân phối không gian giữa các phần tử trong một container. Nó đặc biệt hữu ích khi thiết kế layout **responsive**.

---

## 1. Cấu trúc cơ bản
- **Flex container**: phần tử cha có `display: flex;`
- **Flex items**: phần tử con trực tiếp bên trong container.

```css
.container {
  display: flex;
}
.item {
  flex: 1;
}
```
## 2. Các thuộc tính chính
### Container
- `display: flex;` → bật flexbox
- `flex-direction` → hướng sắp xếp:
  - `row` (mặc định), `row-reverse`
  - `column`, `column-reverse`

- `justify-content` → căn chỉnh theo trục chính:
  - `flex-start`, `flex-end`, `center`
  - `space-between`, `space-around`, `space-evenly`
 
- `align-items` → căn chỉnh theo trục chéo:
  - `flex-start`, `flex-end`, `center`
  - `stretch`, `baseline`

- `flex-wrap` → cho phép xuống dòng:
  - `nowrap (mặc định)`, `wrap`, `wrap-reverse`

- `align-content` → căn chỉnh nhiều hàng:
  - `flex-start`, `flex-end`, `center`
  - `space-between`, `space-around`, `stretch`
 
### Item
- `flex-grow` → mức độ giãn ra khi còn chỗ trống
- `flex-shrink` → mức độ co lại khi thiếu chỗ
- `flex-basis` → kích thước cơ bản
- `flex` → viết gộp: flex: grow shrink basis;
- `align-self` → ghi đè align-items cho item riêng lẻ.
- `order` → thay đổi thứ tự hiển thị của item (mặc định = 0).
  ```
  .item:first-child {
    order: 2; /* nằm sau item có order thấp hơn */
  }
  .item:last-child {
    order: -1; /* lên đầu */
  }
  ```

### Ví dụ
```css
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>

.container {
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: 200px;
  background: #f0f0f0;
}
.item {
  flex: 1;
  margin: 5px;
  background: lightblue;
  text-align: center;
  padding: 20px;
}
```

  

