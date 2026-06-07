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