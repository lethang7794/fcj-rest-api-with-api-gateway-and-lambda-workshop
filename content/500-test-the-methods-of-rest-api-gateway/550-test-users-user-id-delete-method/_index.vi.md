---
title: "Kiểm tra phương thức DELETE /users/{userId}"
weight: 5
chapter: false
pre: " <b> 5.5. </b> "
---

1. Trong phần _Resources_ của `UsersAPI`.
1. Dưới tài nguyên `{userId}` của tài nguyên `/users`, chọn phương thức `POST`.

1. Mở tab `Test`.
1. Trong `Test method` - `Path` - `userId`, nhập `d1d2f263-9a93-408c-a836-c13e24fcebf6`.

   > [!NOTE]
   > Thay thế giá trị id bằng id của người dùng đã tạo ở bước trước.

![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--test.jpg)

1. Nhấp vào `Test`.
1. Xác minh rằng hàm Lambda `get-user` được gọi thành công và phản hồi là dữ liệu của người dùng.

![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--test-results.jpg)
