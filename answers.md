## PHẦN A:

## CÂU A1:

1. Vẽ layout cho HTML:

| Kích thước | < 768px (Mobile) | 768px - 991px (Tablet) | ≥ 992px (Desktop/Laptop) |
| :--- | :--- | :--- | :--- |
| Số cột (Box/Row) | 1 cột | 2 cột | 4 cột |
| Box layout | Xếp chồng dọc (1 col/row) | 2x2 grid (2 col/row) | 1 hàng ngang (4 col/row) |

2. Giải thích:
- `col-md-6`: Nghĩa là trên các thiết bị có độ rộng màn hình >= 768px (Medium devices), phần tử này sẽ chiếm 6/12 cột
- `Tại sao không cần viết col-sm-12?`: Vì trong Bootstrap, các class `col-*` mặc định có chiều rộng 100% (`col-12`) nếu không có class nào khác chỉ định cho breakpoint nhỏ hơn. `md` là breakpoint tiếp theo sau `sm` và mặc định, nên `col-12` là giá trị mặc định cho các màn hình dưới 768px

## CÂU A2:

1. Giải thích class `d-none d-md-block`:
- `d-none`: Ẩn phần tử trên tất cả các kích thước màn hình (display: none)
- `d-md-block`: Hiển thị phần tử dưới dạng block từ màn hình ≥ 768px trở lên
- Kết quả: Phần tử sẽ bị ẩn trên màn hình nhỏ (Mobile < 768px) và hiển thị từ màn hình Medium trở lên

2. 5 spacing utilities:
- `mt-3`: `margin-top` với mức độ 3 (mặc định là 1rem).
- `px-4`: `padding-left` và `padding-right` với mức độ 4 (mặc định là 1.5rem)
- `mb-auto`: `margin-bottom: auto!important` (thường dùng trong flexbox để đẩy phần tử)
- `ms-2`: `margin-start` (margin-left trong LTR) với mức độ 2 (0.5rem)
- `pt-5`: `padding-top` với mức độ 5 (3rem)

3. Sự khác nhau giữa Container:
- `.container`: Có chiều rộng cố định (fixed width) thay đổi theo từng breakpoint
- `.container-fluid`: Luôn chiếm 100% chiều rộng màn hình ở mọi breakpoint
- `.container-md`: Chiếm 100% chiều rộng cho đến khi đạt breakpoint `md` (768px), từ đó trở đi nó hoạt động giống `.container`