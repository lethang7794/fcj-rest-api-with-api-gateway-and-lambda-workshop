---
title: "Kiểm tra phương thức PATCH /users/{userId}"
weight: 4
chapter: false
pre: " <b> 5.4. </b> "
---

1. Trong phần _Resources_ của `UsersAPI`.
1. Dưới tài nguyên `{userId}` của tài nguyên `/users`, chọn phương thức `POST`.

1. Mở tab `Test`.
1. Trong trường Request body, nhập:

   > [!NOTE]
   > Thay thế giá trị id bằng id của người dùng đã tạo ở bước trước.

   ```json
   {
     "id": "d1d2f263-9a93-408c-a836-c13e24fcebf6",
     "email": "tranvanan@gmail.com",
     "name": "Tran Van An"
   }
   ```

![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--test-request.jpg)

1. Nhấp vào `Test`.

1. Xác minh rằng hàm Lambda `update-user` được gọi thành công và phản hồi là dữ liệu của người dùng đã được cập nhật.

![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--test-results.jpg)
