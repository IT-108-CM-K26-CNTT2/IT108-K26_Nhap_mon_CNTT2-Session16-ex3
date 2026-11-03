# Bài 3: Xử lý sự cố giao diện website doanh nghiệp

## 1. Nguyên nhân lỗi hiển thị

### Chi tiết Box Model của `div.lesson-content`

| Thành phần | Giá trị hiện tại | Vấn đề |
|---|---|---|
| Content (width) | `width: 65% !important;` | Chiếm quá nhiều không gian ngang của vùng chứa |
| Margin | `margin-right: -20px;` | Margin âm |

### Lý do phần tử bị đè

- `margin-right: -20px` kéo phần tử kế tiếp ("Danh sách video") lùi sang trái 20px, đè lên `div.lesson-content`.
- Chiều rộng 65% quá lớn nên không còn đủ chỗ cho khung bên phải, làm lỗi chồng lấn rõ hơn.

## 2. Giải pháp khắc phục

Mở DevTools, tab **Elements**, chọn `div.lesson-content`, chỉnh trong khung **Styles**:

1. **Bỏ margin âm:** đổi `margin-right: -20px;` thành `margin-right: 20px;` (hoặc `0`).
2. **Kiểm soát độ rộng:** giảm `width: 65% !important;` xuống khoảng 55% - 60% để chừa đủ không gian cho khung bên phải.
3. **Kiểm tra lại:** dùng sơ đồ Box Model trong tab **Computed** để xác nhận không còn chồng lấn.
4. **Ghi nhận kết quả:** ghi lại giá trị đã sửa và báo Dev cập nhật vào file CSS gốc (chỉnh trong DevTools chỉ có tác dụng tạm thời, tải lại trang là mất).
