# CSS `position`

## 1) Các giá trị cơ bản
- `static` (mặc định): phần tử theo luồng bình thường, **bỏ qua** top/right/bottom/left/z-index.  
- `relative`: giữ chỗ trong luồng, **dịch chuyển** theo `top/right/bottom/left`. Tạo **containing block** cho `absolute` con khi cần.  
- `absolute`: **thoát** khỏi luồng, định vị theo **containing block gần nhất** (tổ tiên gần nhất **không phải** `static`; thường là `relative/absolute/fixed/sticky` hoặc viewport nếu không có).  
- `fixed`: bám **viewport**, không cuộn theo trang (trừ khi tổ tiên có transform/filters tạo context cuộn).  
- `sticky`: kết hợp `relative` + “dính” khi cuộn đến ngưỡng (`top/right/bottom/left`). Cần **vùng cuộn** và **khoảng trống** để dính.

> **Offset hợp lệ**: `top | right | bottom | left` chỉ có tác dụng khi `position != static`.
