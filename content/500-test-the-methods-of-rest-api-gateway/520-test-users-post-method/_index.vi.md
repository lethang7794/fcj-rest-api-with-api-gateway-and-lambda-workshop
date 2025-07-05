---
title: "Kiểm tra phương thức POST /users"
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---

1. Trong phần _Resources_ của `UsersAPI`.
1. Dưới tài nguyên `/users`, chọn phương thức `POST`.
1. Mở tab `Test`.
1. Trong trường Request body, nhập:

   ```json
   {
     "email": "tranvana@gmail.com",
     "name": "Tran Van A"
   }
   ```

![alt text](/images/workshop-2/API-Gateway--users-POST-method--test-request.jpg)

1. Nhấp vào `Test`.

1. Xác minh rằng hàm Lambda `create-users` được gọi thành công và phản hồi là thông tin người dùng vừa được tạo.

![alt text](/images/workshop-2/API-Gateway--users-POST-method--test-results.jpg)
