---
title: "Chuẩn bị"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

Trước khi bắt đầu workshop này, bạn cần:

1. Một IAM user với quyền `AdministratorAccess` mà bạn có thể sử dụng để đăng nhập vào AWS Management Console.

   ![alt text](/images/workshop-2/IAM-user-login-and-permissions.png)

   Nếu bạn chưa tạo IAM user, hãy làm theo hướng dẫn [Tạo IAM Group và IAM User :: QUẢN LÝ KIỂM SOÁT TRUY CẬP VỚI AWS IAM (IDENTITY AND ACCESS MANAGEMENT)](https://000002.awsstudygroup.com/2-create-admin-user-and-group/) để tạo.

2. Các hàm Lambda CRUD (`create-user`, `list-users`, `get-user`, `update-user`, `delete-user`) sẽ được sử dụng làm backend, tích hợp với REST API Gateway.

   Nếu bạn chưa tạo các hàm Lambda CRUD này, hãy làm theo workshop trước để tạo chúng.
