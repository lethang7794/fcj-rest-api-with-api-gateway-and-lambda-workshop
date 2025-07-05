---
title: "Tích hợp các phương thức API với hàm Lambda"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

Trong phần này, chúng ta sẽ kết nối các endpoint REST API với các hàm Lambda tương ứng. Sự tích hợp này sẽ cho phép API Gateway kích hoạt (trigger) các hàm Lambda phù hợp dựa trên các phương thức HTTP và route. Chúng ta sẽ thực hiện các tích hợp sau:

| Tài nguyên API - Phương thức | Hàm Lambda    | Mô tả                                |
| --------------------------- | ------------- | ------------------------------------ |
| `/users          GET`       | `list-users`  | Lấy danh sách tất cả người dùng trong hệ thống |
| `/users          POST`      | `create-user` | Thêm người dùng mới vào hệ thống     |
| `/users/{userId} GET`       | `get-user`    | Lấy thông tin chi tiết của một người dùng cụ thể |
| `/users/{userId} PATCH`     | `update-user` | Cập nhật thông tin của người dùng hiện có |
| `/users/{userId} DELETE`    | `delete-user` | Xóa người dùng khỏi hệ thống         |

Mỗi tích hợp sẽ được cấu hình với các ánh xạ request/response phù hợp để đảm bảo giao tiếp liền mạch giữa API Gateway và các hàm Lambda.
