---
title: "Triển khai và stage"
weight: 1
chapter: false
pre: " <b> 6.1. </b> "
---

<!-- TODO: add diagram to clarify stage and deployment  -->

Một _deployment_ (sự triển khai) là một **bản chụp** cấu hình API của bạn.

- Sau khi bạn cập nhật cấu hình API (tài nguyên, phương thức, tích hợp...), bạn phải triển khai lại API lên một stage để các thay đổi có sẵn cho client gọi.

Một _stage_ là một **tham chiếu có tên** đến một _deployment_ của API và được cung cấp để các ứng dụng client có thể gọi.

- Đối với mỗi stage của API, bạn có thể cấu hình các thiết lập khác nhau

  Ví dụ: Bộ nhớ đệm, giới hạn tốc độ, cài đặt tường lửa/chứng chỉ...

- Ví dụ: Bạn có thể có các stage như `dev`, `prod`, `v2`.

> [!TIP]
> Về bản chất, bạn _triển khai_ một API bằng cách tạo một **sự triển khai (deployment)** và liên kết nó với một **môi trường (stage)**.
