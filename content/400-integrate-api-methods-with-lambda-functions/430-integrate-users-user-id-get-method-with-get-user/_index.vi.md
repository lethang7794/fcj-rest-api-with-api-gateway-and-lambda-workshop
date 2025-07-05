---
title: "Tích hợp phương thức GET /users/{userId} với get-user"
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

1. Quay lại phần _Resources_ của API `UsersAPI` trong bảng điều khiển API Gateway.
1. Chọn tài nguyên `/users`.
1. Nhấp vào `Create resource`.

![alt text](/images/workshop-2/API-Gateway--users-userId--create-resource.jpg)

1. Trong trang `Create resource`:
   - Tại `Resource path`: Chọn `/users`
   - Tại `Resource name`: Nhập `{userId}`.

     > [!NOTE]
     > Lưu ý hai dấu ngoặc nhọn: `{` và `}`.

   - Nhấp vào `Create resource`.

![alt text](/images/workshop-2/API-Gateway--users-userId--create-resource-detail.jpg)

1. Nhấp vào tài nguyên `/users/{userId}` bạn vừa tạo.
1. Nhấp vào `Create method`.

![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--create-method.jpg)

1. Trong trang `Create method`, phần `Method details`:
   - `Method type`: Chọn `GET`.
   - Integration type: Giữ nguyên Lambda function.
   - Lambda function: Chọn hàm `get-user`.

![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--create-method-detail.jpg)

1. Giữ nguyên các cài đặt khác.
   - Cuộn xuống dưới và nhấp vào `Create method`.

1. Bạn sẽ được chuyển hướng đến trang chi tiết của phương thức `/users/{userId} - GET`.

![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--method-detail.jpg)

1. Mở tab `Integration request`.
1. Trong phần `Integration request settings`, nhấp vào `Edit`.

![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--integration-request.jpg)

1. Trong trang `Edit integration request`:

![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--integration-request-detail.jpg)

1. Mở rộng phần `URL path parameters`, nhấp vào `Add path parameter`.

![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--integration-request--URL-path-parameters.png)

- `Name`: Nhập `userId`.
- `Mapped from`: Nhập `method.request.path.userId`.

![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--integration-request--URL-path-parameters--userId.png)

1. Mở rộng phần `Mapping templates`, nhấp vào `Add mapping template`.

![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--integration-request--mapping-template.png)

- `Content type`: Nhập `application/json`.
- `Template body`: Nhập:

  ```json
  {
    "id": "$input.params('userId')"
  }
  ```

![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--integration-request--mapping-template-body.png)

1. Cuộn xuống dưới, nhấp vào `Save`.
