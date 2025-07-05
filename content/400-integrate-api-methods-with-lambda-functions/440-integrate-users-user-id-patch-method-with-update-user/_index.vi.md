---
title: "Tích hợp phương thức PATCH /users/{userId} với update-user"
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---

1. Quay lại phần _Resources_ của API `UsersAPI` trong bảng điều khiển API Gateway.
1. Chọn tài nguyên `/users/{userId}`.
1. Nhấp vào `Create method`.

![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--create-method.jpg)

1. Trong trang `Create method` - phần `Method details`:
   - `Method type`: Chọn `UPDATE`.
   - Integration type: Giữ nguyên Lambda function.
   - Lambda function: Chọn hàm `update-user`.

![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--create-method-detail.jpg)

1. Giữ nguyên các cài đặt khác.
   - Cuộn xuống dưới và nhấp vào `Create method`.

1. Bạn sẽ được chuyển hướng đến trang chi tiết của phương thức `/users/{userId} - PATCH`.

![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--method-detail.jpg)

1. Mở tab `Integration request`.
1. Trong phần `Integration request settings`, nhấp vào `Edit`.

![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--integration-request.jpg)

1. Trong trang `Edit integration request`, mở rộng phần `URL path parameters`:
   - Nhấp vào `Add path parameter`.
   - `Name`: Nhập `userId`.
   - `Mapped from`: Nhập `method.request.path.userId`.

![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--integration-request--URL-path-parameters.png)

1. Mở rộng phần `Mapping templates`:
    - Nhấp vào `Add mapping template`.
    - `Content type`: Nhập `application/json`.
    - `Template body`: Nhập:

      ```text
      ## Parse the request body into a JSON object
      #set($inputRoot = $input.path('$'))
      {
        #foreach($key in $inputRoot.keySet())
          "$key": "$util.escapeJavaScript($inputRoot.get($key))"#if($foreach.hasNext),#end
        #end,
        "id": "$input.params('userId')"
      }
      ```

![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--integration-request--mapping-template-body.png)

1. Cuộn xuống dưới, nhấp vào `Save`.
