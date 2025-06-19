Tên Dự Án: Test Collection of APIs

Ngày Kiểm Thử: 19/06/2025

Người Kiểm Thử: Nguyễn Xuân Lam

GIỚI THIỆU

Postman là một công cụ giao diện đồ họa phổ biến giúp lập trình viên và kiểm thử viên làm việc với API dễ dàng hơn. Với Postman, người dùng có thể gửi các yêu cầu HTTP như GET, POST, PUT và DELETE để kiểm tra hoạt động của API, đồng thời xem chi tiết phản hồi từ server như mã trạng thái, tiêu đề và nội dung trả về. Ngoài ra, Postman cho phép viết các đoạn mã JavaScript nhỏ trong tab Tests để tự động kiểm tra dữ liệu phản hồi có đúng định dạng hay không, giúp phát hiện lỗi nhanh chóng. Người dùng cũng có thể tổ chức các yêu cầu API thành các bộ sưu tập (collections), chạy kiểm thử hàng loạt bằng Collection Runner, mô phỏng server khi backend chưa sẵn sàng, và tích hợp với hệ thống CI/CD thông qua công cụ dòng lệnh Newman để chạy và xuất báo cáo kiểm thử tự động. Nhờ giao diện thân thiện và tính năng mạnh mẽ, Postman trở thành công cụ không thể thiếu trong quá trình phát triển và kiểm thử phần mềm hiện đại.


1. Mục Tiêu Kiểm Thử: Sử dụng Postman để kiểm thử một API thực tế

2. Môi Trường Kiểm Thử: Postman.

3. Phương Pháp Kiểm Thử: Kiểm thử tự động và thủ công trên phần mềm Postman.

4. Kịch Bản Kiểm Thử Lần 1:
Tên Kịch Bản: Kiểm thử cơ bản của 1 URL

Mục Đích: Test khả năng hoạt động của URL và phần mềm Postman

Phương Thức HTTP (GET/POST/PUT/DELETE): GET

URL: https://jsonplaceholder.typicode.com/users

Kết Quả Mong Đợi: Gửi yêu cầu thành công

Kết Quả Thực Tế: Đã gửi yêu cầu thành công

Trạng Thái: Thành công

Kết quả sau khi kiểm thử:
![image](https://github.com/user-attachments/assets/7513e1f6-cc37-4857-b3ac-7d4a079c3c27)

Kịch Bản Kiểm Thử Lần 2:
Tên Kịch Bản: Tạo bài viết mới với dữ liệu JSON cụ thể

Mục Đích: Kiểm tra khả năng gửi nội dung JSON đến server để tạo một bài viết mới và xác minh server phản hồi đúng dữ liệu

Phương Thức HTTP: POST

URL: https://jsonplaceholder.typicode.com/posts

Kết Quả Mong Đợi: Server phản hồi 201 Created, nội dung phản hồi chứa lại đúng dữ liệu gửi đi cùng id mới

Kết Quả Thực Tế: Server phản hồi 201 Created, trả về JSON gồm:

"title": "Siêu nhân sấm sét"

"body": "Nguyễn Xuân Lam"

"userId": 10

"id": 101

Trạng Thái: ✅ Thành công

Kết quả sau khi kiểm thử:
![image](https://github.com/user-attachments/assets/4a35f237-a54d-4845-9a09-924f4f23033c)

Kịch Bản Kiểm Thử Lần 3:
Tên Kịch Bản: Cập nhật bài viết với ID = 1

Mục Đích: Kiểm thử khả năng cập nhật nội dung bài viết đã tồn tại bằng phương thức PUT

Phương Thức HTTP: PUT

URL: https://jsonplaceholder.typicode.com/posts/1

Kết Quả Mong Đợi: Server phản hồi mã 200 OK, dữ liệu trả về là bài viết mới với nội dung đã cập nhật

Kết Quả Thực Tế: Server phản hồi 200 OK, trả về dữ liệu JSON mới gồm:

"id": 1

"title": "Việt Nam"

"body": "Đây là đài tiếng nói Việt Nam"

"userId": 1

Trạng Thái: ✅ Thành công

Kết quả sau khi kiểm thử:
![image](https://github.com/user-attachments/assets/c8bea99f-8f5d-4e2f-9370-df8b85cd95a8)

Kịch Bản Kiểm Thử Lần 4:
Tên Kịch Bản: Xoá bài viết có ID = 1

Mục Đích: Kiểm tra khả năng xử lý yêu cầu xoá tài nguyên của API

Phương Thức HTTP: DELETE

URL: https://jsonplaceholder.typicode.com/posts/1

Kết Quả Mong Đợi: Server phản hồi mã 200 OK, không trả về nội dung hoặc chỉ trả về JSON rỗng

Kết Quả Thực Tế: Server phản hồi 200 OK trong 404ms, phần body trả về {}

Trạng Thái: ✅ Thành công

Kết quả sau khi kiểm thử:
![image](https://github.com/user-attachments/assets/a02d4785-bef2-4a5a-9ee0-361970ee4f28)

Kịch Bản Kiểm Thử Lần 5:
Tên Kịch Bản: Kiểm tra phản hồi trạng thái của trang chủ API

Mục Đích: Kiểm tra xem trang chủ của API JSONPlaceholder phản hồi thành công với mã trạng thái 200 hay không

Phương Thức HTTP: GET

URL: https://jsonplaceholder.typicode.com/

Kết Quả Mong Đợi: Server phản hồi mã trạng thái 200 OK

Kết Quả Thực Tế: Server phản hồi 200 OK trong 124ms, test script kiểm tra trạng thái đã pass: Status is 200

Trạng Thái: ✅ Thành công

Kết quả sau khi kiểm thử:
![image](https://github.com/user-attachments/assets/7d99a91b-d166-429f-bcdf-e6f239a1d76f)

Kịch Bản Kiểm Thử Lần 6:
Tên Kịch Bản: Tạo bài viết mới và kiểm tra phản hồi chi tiết

Mục Đích: Kiểm tra việc gửi POST để tạo bài viết mới và xác minh phản hồi trả về đúng mã trạng thái và có chứa trường id

Phương Thức HTTP: POST

URL: https://jsonplaceholder.typicode.com/posts

Kết Quả Mong Đợi: Server phản hồi mã 201 Created, và dữ liệu trả về phải có trường "id"

Kết Quả Thực Tế:

Mã phản hồi: 201 Created

Thời gian phản hồi: 981 ms

Các kiểm thử trong tab Scripts:

✅ Status is 201

✅ Response has ID

Trạng Thái: ✅ Thành công

Kết quả sau khi kiểm thử:
![image](https://github.com/user-attachments/assets/d8859562-9db9-42fb-b547-d35dd056e47e)

Kịch Bản Kiểm Thử Lần 7:
Tên Kịch Bản: Cập nhật bài viết bằng phương thức PUT và xác minh phản hồi

Mục Đích: Kiểm tra server có phản hồi đúng với mã trạng thái 200 OK khi thực hiện cập nhật bài viết hay không

Phương Thức HTTP: PUT

URL: https://jsonplaceholder.typicode.com/posts/1

Kết Quả Mong Đợi: Server phản hồi 200 OK và test script xác nhận trạng thái đúng

Kết Quả Thực Tế:

Server phản hồi mã 200 OK sau 1.27 giây

Test script "Status is 200" đã PASS

Trạng Thái: ✅ Thành công

Kết quả sau khi kiểm thử:
![image](https://github.com/user-attachments/assets/ffe1f135-4c98-46af-b5cc-da79f485c84a)

Kịch Bản Kiểm Thử Lần 8:
Tên Kịch Bản: Xoá bài viết và xác minh phản hồi 200 hoặc 204

Mục Đích: Kiểm tra phản hồi từ server khi thực hiện yêu cầu xoá tài nguyên, với khả năng chấp nhận cả mã trạng thái 200 hoặc 204

Phương Thức HTTP: DELETE

URL: https://jsonplaceholder.typicode.com/posts/1

Kết Quả Mong Đợi: Server phản hồi mã 200 OK hoặc 204 No Content tùy vào cách xử lý, và script xác minh trạng thái phản hồi hợp lệ

Kết Quả Thực Tế:

Server phản hồi mã 200 OK trong 847ms

Test script "Status is 200 or 204" đã PASS

Trạng Thái: ✅ Thành công

Kết quả sau khi kiểm thử:
![image](https://github.com/user-attachments/assets/123b9998-3830-4e48-8b26-a66c133b125e)


