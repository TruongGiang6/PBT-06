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

### PHẦN C:

## CÂU C1:

1. Quy trình đổi màu `$primary`:
- Công cụ: Cần Node.js, npm, và một trình biên dịch SASS
- Quy trình:
    + Cài đặt bootstrap qua npm: `npm install bootstrap`
    + Tạo file SASS tùy chỉnh
    + Định nghĩa lại biến trước khi import Bootstrap:
       ```scss
       $primary: #E63946;
       @import "node_modules/bootstrap/scss/bootstrap";
       ```
    + Biên dịch file `custom.scss` sang `custom.css` để sử dụng

2. Tại sao không nên override trực tiếp?
- Vì nếu override trực tiếp `.btn-primary`, ta chỉ đổi màu nút bấm. Nếu dùng SASS variables, các thành phần khác dùng màu `$primary` như badges, links, borders, background utilities sẽ tự động cập nhật theo, đảm bảo tính nhất quán của giao diện. Ngoài ra, SASS còn giúp tự động tính toán các biến thể màu (hover, active, focus)

## CÂU C2:

| Tiêu chí | CSS Thuần (Custom) | Bootstrap Version |
| :--- | :--- | :--- |
| Số dòng CSS | Rất nhiều (phải viết media queries, flex/grid rules) | Gần như bằng 0 (chỉ dùng classes có sẵn) |
| Thời gian phát triển | Chậm (phải test responsive thủ công) | Rất nhanh (layout chuẩn hóa sẵn) |
| Khả năng tùy biến | Vô hạn, linh hoạt tuyệt đối | Có giới hạn (nếu không dùng SASS) |

- NÊN dùng Bootstrap: Khi cần làm prototype nhanh, các dự án Dashboard/Admin, hoặc dự án cần sự nhất quán và không yêu cầu thiết kế quá đặc thù/sáng tạo
- KHÔNG NÊN dùng Bootstrap: Khi dự án yêu cầu bộ nhận diện thương hiệu độc bản (unique design), UI cực kỳ phức tạp hoặc yêu cầu tối ưu dung lượng file CSS (Bootstrap chứa nhiều code không dùng tới nếu không lọc)