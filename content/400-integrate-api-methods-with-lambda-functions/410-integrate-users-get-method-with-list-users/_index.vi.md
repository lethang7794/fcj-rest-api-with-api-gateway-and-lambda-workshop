---
title: "Tích hợp phương thức GET /users với list-users"
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

1. Mở [phần APIs](https://console.aws.amazon.com/apigateway/main/apis) trong bảng điều khiển API Gateway.
1. Trong danh sách các API, nhấp vào tên API (`UsersAPI`).

![alt text](/images/workshop-2/API-Gateway--API-detail.png)

1. Bạn sẽ được chuyển hướng đến phần _Resources_ của `UsersAPI`.

> [!TIP]
> Sau khi tạo một API, bạn sẽ tự động được chuyển hướng từ phần _APIs_ của API Gateway đến phần _Resources_ của API đó (ví dụ: `API: UsersAPI`).

1. Nhấp vào `Create resource`

![alt text](/images/workshop-2/API-Gateway--create-resource.jpg)

1. Trong trang `Create resource`:
   - Tại `Resource path`: Chọn `/`
   - Tại `Resource name`: Nhập `users`.
   - Nhấp vào `Create resource`.

![alt text](/images/workshop-2/API-Gateway--users-resource--create-resource-detail.jpg)

1. Nhấp vào tài nguyên `users` bạn vừa tạo.
1. Nhấp vào `Create method`.

![alt text](/images/workshop-2/API-Gateway--users-GET-method--create-method.jpg)

1. Trong trang `Create method`, phần `Method details`:
   - `Method type`: Chọn `GET`.
   - Integration type: Giữ nguyên Lambda function.
   - Lambda function: Chọn hàm `list-users`.

![alt text](/images/workshop-2/API-Gateway--users-GET-method--create-method-detail.jpg)

1. Giữ nguyên các cài đặt khác.
   - Cuộn xuống dưới và nhấp vào `Create method`.

![alt text](/images/workshop-2/API-Gateway--users-GET-method--create-button.jpg)

1. Bạn sẽ được chuyển hướng đến trang chi tiết của phương thức `/users - GET`.

![alt text](/images/workshop-2/API-Gateway--users-GET-method.jpg)
