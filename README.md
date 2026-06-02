# BÁO CÁO TÌM HIỂU VÀ KIỂM THỬ API BẰNG POSTMAN

## Thông tin sinh viên

* Họ và tên: Vũ Tiến Hưng
* Môn học: Kiểm thử phần mềm
* Công cụ sử dụng: Postman
* API sử dụng: JSONPlaceholder

---

# 1. Giới thiệu

Postman là một công cụ phổ biến dùng để kiểm thử API. Công cụ này hỗ trợ gửi các yêu cầu HTTP như GET, POST, PUT, DELETE và giúp kiểm tra dữ liệu phản hồi từ máy chủ.

Trong bài thực hành này, em sử dụng Postman để kiểm thử các API cơ bản thông qua dịch vụ JSONPlaceholder.

---

# 2. Mục tiêu thực hành

* Tìm hiểu giao diện và cách sử dụng Postman.
* Thực hiện gửi các yêu cầu GET và POST.
* Kiểm tra phản hồi từ API.
* Thực hiện kiểm thử lỗi.
* Viết Test Script tự động trong Postman.

---

# 3. Môi trường thực hiện

| Thành phần   | Thông tin       |
| ------------ | --------------- |
| Hệ điều hành | Windows         |
| Công cụ      | Postman         |
| API          | JSONPlaceholder |
| Giao thức    | HTTP/HTTPS      |

API sử dụng:

https://jsonplaceholder.typicode.com

---

# 4. Tạo Collection

Đầu tiên em tạo Collection có tên:

Postman Testing

Collection dùng để quản lý các Request trong cùng một dự án kiểm thử.

Ảnh minh họa:

![Collection](images/collection.png)

---

# 5. Kiểm thử GET Request

## Mục tiêu

Lấy thông tin bài viết có ID = 1.

## Thông tin Request

Method:

GET

URL:

https://jsonplaceholder.typicode.com/posts/1

## Kết quả mong đợi

* Server trả về thông tin bài viết.
* Status Code = 200 OK.

## Kết quả thực tế

Server trả về dữ liệu JSON chứa thông tin bài viết.

Ảnh minh họa:

![GET Request](images/get-post-detail.png)

## Đánh giá

Kết quả đúng như mong đợi.

---

# 6. Kiểm thử POST Request

## Mục tiêu

Tạo mới một bài viết.

## Thông tin Request

Method:

POST

URL:

https://jsonplaceholder.typicode.com/posts

Body:

{
"title": "Postman Test",
"body": "Hoc Postman",
"userId": 1
}

## Kết quả mong đợi

* Tạo mới dữ liệu.
* Status Code = 201 Created.

## Kết quả thực tế

Server phản hồi thành công và trả về ID của bản ghi mới.

Ảnh minh họa:

![POST Request](images/post-create-post.png)

## Đánh giá

API xử lý yêu cầu tạo dữ liệu thành công.

---

# 7. Kiểm thử lỗi API

## Mục tiêu

Kiểm tra phản hồi khi truy cập đường dẫn không tồn tại.

## Thông tin Request

Method:

GET

URL:

https://jsonplaceholder.typicode.com/abcxyz

## Kết quả mong đợi

Server trả về lỗi 404.

## Kết quả thực tế

Server trả về:

404 Not Found

Ảnh minh họa:

![404 Error](images/get-error.png)

## Đánh giá

Hệ thống xử lý lỗi đúng theo mong đợi.

---

# 8. Viết Test Script trong Postman

Để kiểm tra tự động Status Code của API, em sử dụng đoạn mã sau:

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

## Kết quả

Sau khi thực thi Request, Postman hiển thị:

✓ Status code is 200

Ảnh minh họa:

![Test Script](images/test-status-200.png)

## Đánh giá

Bài kiểm thử thành công và API trả về đúng mã trạng thái.

---

# 9. Kết quả thực hiện

| STT | Chức năng kiểm thử | Kết quả    |
| --- | ------------------ | ---------- |
| 1   | GET Request        | Thành công |
| 2   | POST Request       | Thành công |
| 3   | Kiểm thử lỗi 404   | Thành công |
| 4   | Test Script        | Thành công |

---

# 10. Nhận xét

Qua bài thực hành, em đã làm quen với giao diện Postman và biết cách:

* Tạo Collection.
* Tạo và gửi Request.
* Kiểm tra Response.
* Xử lý các trường hợp lỗi.
* Viết Test Script tự động.

Postman là công cụ mạnh mẽ và hữu ích trong việc kiểm thử API, giúp giảm thời gian kiểm thử thủ công và nâng cao chất lượng phần mềm.

---

# 11. Kết luận

Bài thực hành đã hoàn thành các yêu cầu cơ bản về tìm hiểu và sử dụng Postman. Em đã thực hiện thành công các thao tác kiểm thử GET, POST, kiểm tra lỗi và xây dựng Test Script tự động để đánh giá kết quả trả về của API.
