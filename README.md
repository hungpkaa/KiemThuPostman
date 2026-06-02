# BÁO CÁO KIỂM THỬ API BẰNG POSTMAN

Tên dự án: Kiểm thử API với JSONPlaceholder  
Người kiểm thử: Vũ Tiến Hưng  
Công cụ sử dụng: Postman  
API sử dụng: https://jsonplaceholder.typicode.com  

## 1. Mục tiêu kiểm thử

Sử dụng Postman để kiểm thử các API cơ bản với các phương thức GET, POST và kiểm tra phản hồi từ server.

## 2. Môi trường kiểm thử

- Hệ điều hành: Windows
- Công cụ: Postman
- API: JSONPlaceholder Fake REST API

## 3. Kịch bản kiểm thử 1: GET danh sách bài viết

- Phương thức: GET
- URL: https://jsonplaceholder.typicode.com/posts
- Kết quả mong đợi: Server trả về danh sách bài viết
- Kết quả thực tế: Gửi yêu cầu thành công
- Status code: 200 OK
- Trạng thái: Thành công

![GET Posts](images/get-posts.png)

## 4. Kịch bản kiểm thử 2: GET chi tiết một bài viết

- Phương thức: GET
- URL: https://jsonplaceholder.typicode.com/posts/1
- Kết quả mong đợi: Server trả về thông tin bài viết có id = 1
- Kết quả thực tế: Gửi yêu cầu thành công
- Status code: 200 OK
- Trạng thái: Thành công

![GET Post Detail](images/get-post-detail.png)

## 5. Kịch bản kiểm thử 3: POST tạo bài viết mới

- Phương thức: POST
- URL: https://jsonplaceholder.typicode.com/posts
- Body:

```json
{
  "title": "Postman Test",
  "body": "Day la bai viet duoc tao bang Postman",
  "userId": 1
}
##6. Kịch bản kiểm thử 4: GET sai đường dẫn
Phương thức: GET
URL: https://jsonplaceholder.typicode.com/abcxyz
Kết quả mong đợi: Server báo lỗi không tìm thấy
Kết quả thực tế: Server trả về lỗi
Status code: 404 Not Found
Trạng thái: Không thành công
