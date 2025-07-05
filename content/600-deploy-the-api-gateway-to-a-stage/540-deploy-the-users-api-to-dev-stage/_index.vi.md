---
title: "Triển khai UsersAPI lên stage dev"
weight: 4
chapter: false
pre: " <b> 6.4. </b> "
---

1. Mở [phần APIs](https://console.aws.amazon.com/apigateway/main/apis) trong bảng điều khiển API Gateway.
1. Trong danh sách các API, nhấp vào tên API (`UsersAPI`).
1. Bạn sẽ được chuyển hướng đến phần _Resources_ của `UsersAPI`.

1. Nhấp vào `Deploy API`

![alt text](/images/workshop-2/API-Gateway--usersAPI--deploy-API.jpg)

1. Trong cửa sổ bật lên _Deploy API_:
   - State: Chọn `*New stage*`.
   - Stage name: Nhập `dev`.
   - Nhấp vào `Deploy`.

![alt text](/images/workshop-2/API-Gateway--usersAPI--deploy-API--stage.jpg)

1. Bạn sẽ được chuyển hướng đến trang `Stages` của `UsersAPI`.
1. Sao chép `Invoke URL` của stage `dev`.

![alt text](/images/workshop-2/API-Gateway--usersAPI--stage--invoke-URL.jpg)

> [!TIP]
> Chúc mừng, bạn đã triển khai thành công một API Gateway. Hãy sao chép invoke URL của stage `dev`, bạn sẽ cần nó trong bước tiếp theo.
