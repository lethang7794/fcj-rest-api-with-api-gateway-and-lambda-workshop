---
title: "Kiểm tra các phương thức của REST API Gateway"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

Trong phần này, chúng ta sẽ kiểm tra các endpoint của REST API Gateway bằng cách sử dụng AWS Management Console. Giao diện điều khiển cung cấp một giao diện thân thiện để xác minh chức năng của từng endpoint trước khi triển khai lên một môi trường (stage).

## Quy trình kiểm tra

1. **Truy cập tab Test của từng tài nguyên - phương thức API**
   - Điều hướng đến API Gateway trong AWS Console
   - Chọn API và tài nguyên/phương thức mong muốn
   - Mở tab Test

2. **Kiểm tra từng tài nguyên - phương thức**

   | Tài nguyên API - Phương thức | Hàm Lambda    | Yêu cầu kiểm tra                             |
   | --------------------------- | ------------- | -------------------------------------------- |
   | `/users          GET`       | `list-users`  | Trả về tất cả người dùng từ hệ thống         |
   | `/users          POST`      | `create-user` | Thêm người dùng mới vào hệ thống             |
   | `/users/{userId} GET`       | `get-user`    | Trả về chi tiết của một người dùng cụ thể    |
   | `/users/{userId} PATCH`     | `update-user` | Cập nhật thông tin người dùng với dữ liệu mới|
   | `/users/{userId} DELETE`    | `delete-user` | Xóa người dùng khỏi hệ thống                 |

3. **Xác minh phản hồi**
   - Kiểm tra mã trạng thái HTTP
   - Xác thực nội dung phản hồi
   - [Tùy chọn] Xem lại nhật ký CloudWatch để biết chi tiết thực thi Lambda

Tính năng kiểm tra của Management Console cho phép bạn nhanh chóng xác thực API mà không cần triển khai lên môi trường (stage), rất lý tưởng cho việc phát triển và gỡ lỗi.
