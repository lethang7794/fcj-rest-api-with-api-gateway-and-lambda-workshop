---
title: "Kiểm tra phương thức GET /users"
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

1. Mở [phần APIs](https://console.aws.amazon.com/apigateway/main/apis) trong bảng điều khiển API Gateway.
1. Trong danh sách các API, nhấp vào tên API (`UsersAPI`).
1. Bạn sẽ được chuyển hướng đến phần _Resources_ của `UsersAPI`.
1. Dưới tài nguyên `/users`, chọn phương thức `GET`.
1. Mở tab `Test`.

![alt text](/images/workshop-2/API-Gateway--users-GET-method--test-tab.jpg)

1. Nhấp vào `Test`.

1. Xác minh rằng hàm Lambda `list-users` được gọi thành công và phản hồi có danh sách người dùng.

![alt text](/images/workshop-2/API-Gateway--users-GET-method--test-results.jpg)
