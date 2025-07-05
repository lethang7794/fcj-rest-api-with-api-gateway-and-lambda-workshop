---
title: "Tích hợp phương thức POST /users với create-user"
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

1. Quay lại phần _Resources_ của API `UsersAPI` trong bảng điều khiển API Gateway.
1. Chọn tài nguyên `/users`.
1. Nhấp vào `Create method`.

![alt text](/images/workshop-2/API-Gateway--users-POST-method--create-method.jpg)

1. Trong trang `Create method`, phần `Method details`:

- `Method type`: Chọn `POST`.
- Integration type: Giữ nguyên Lambda function.
- Lambda function: Chọn hàm `create-user`.

![alt text](/images/workshop-2/API-Gateway--users-POST-method--create-method-detail.jpg)

1. Giữ nguyên các cài đặt khác.
   - Cuộn xuống dưới và nhấp vào `Create method`.

1. Bạn sẽ được chuyển hướng đến trang chi tiết của phương thức `/users - POST`.

![alt text](/images/workshop-2/API-Gateway--users-POST-method--method-detail.jpg)
