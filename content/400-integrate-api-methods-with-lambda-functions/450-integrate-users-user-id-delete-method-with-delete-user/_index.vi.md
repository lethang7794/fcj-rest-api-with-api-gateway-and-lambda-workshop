---
title: "Tích hợp phương thức DELETE /users/{userId} với delete-user"
weight: 5
chapter: false
pre: " <b> 4.5. </b> "
---

1. Quay lại phần _Resources_ của API `UsersAPI` trong bảng điều khiển API Gateway.
1. Chọn tài nguyên `/users/{userId}`.
1. Nhấp vào `Create method`.

![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--create-method.jpg)

1. Trong trang `Create method` - phần `Method details`:
   - `Method type`: Chọn `DELETE`.
   - Integration type: Giữ nguyên Lambda function.
   - Lambda function: Chọn hàm `delete-user`.

![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--create-method-detail.jpg)

1. Giữ nguyên các cài đặt khác.
   - Cuộn xuống dưới và nhấp vào `Create method`.

1. Bạn sẽ được chuyển hướng đến trang chi tiết của phương thức `/users/{userId} - DELETE`.

![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--method-detail.png)

1. Mở tab `Integration request`.
1. Trong phần `Integration request settings`, nhấp vào `Edit`.

![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--integration-request.jpg)

1. Trong trang `Edit integration request`:

![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--integration-request-detail.jpg)

1. Mở rộng phần `URL path parameters`:
   - Nhấp vào `Add path parameter`.
   - `Name`: Nhập `userId`.
   - `Mapped from`: Nhập `method.request.path.userId`.

1. Mở rộng phần `Mapping templates`:
   - Nhấp vào `Add mapping template`.
   - `Content type`: Nhập `application/json`.
   - `Template body`: Nhập:

     ```json
     {
       "id": "$input.params('userId')"
     }
     ```

![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--integration-request--URL-path-parameters-and-mapping-template-body.jpg)

1. Cuộn xuống dưới, nhấp vào `Save`.
