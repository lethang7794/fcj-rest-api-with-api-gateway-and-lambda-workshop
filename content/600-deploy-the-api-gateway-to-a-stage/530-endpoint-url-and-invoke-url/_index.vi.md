---
title: "Endpoint URL và Invoke URL"
weight: 3
chapter: false
pre: " <b> 6.3. </b> "
---

Mỗi API của Amazon API Gateway có

- một _endpoint_ mặc định (còn gọi là tên máy chủ - hostname - của API) theo định dạng
  - `{api-id}.execute-api.{region}.amazonaws.com`, hoặc
  - `{hostname}`

Mỗi stage có sẵn để các ứng dụng client gọi thông qua

- một _base URL_ (URL cơ sở) theo định dạng
  - `{protocol}://{hostname}/{stage}`, hoặc
  - `https://{api-id}.execute-api.{region}.amazonaws.com/{stage}` (đối với REST API Gateway trong trường hợp của chúng ta).

---

Để gọi một API đã triển khai, client gửi yêu cầu tới

- một _Invoke URL_ (URL gọi) theo định dạng
  - `{protocol}://{hostname}/{stage}{resourcePath}`, hoặc
  - `https://{api-id}.execute-api.{region}.amazonaws.com/{stage}{resourcePath}` (đối với REST API Gateway trong trường hợp của chúng ta).

Ví dụ:

- Stage `dev` của một REST API có thể truy cập tại Invoke URL: `https://{api-id}.execute-api.{region}.amazonaws.com/dev`

![alt text](/images/workshop-2/api-gateway--invoke-url--stage.png)

- Tài nguyên gốc `/` của stage `dev` của cùng REST API có thể truy cập tại Invoke URL: `https://{api-id}.execute-api.{region}.amazonaws.com/dev/`

![alt text](/images/workshop-2/api-gateway--invoke-url--root-resource.png)

- Tài nguyên `users` của stage `dev` của cùng REST API có thể truy cập tại Invoke URL: `https://{api-id}.execute-api.{region}.amazonaws.com/dev/users`

![alt text](/images/workshop-2/api-gateway--invoke-url--users-resource.png)
