Tên Dự Án: Test Collection of APIs

Ngày Kiểm Thử: 19/06/2025

Người Kiểm Thử: Nguyễn Xuân Lam

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
