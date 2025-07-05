---
title: "Gọi các phương thức của REST API Gateway"
weight: 7
chapter: false
pre: " <b> 7. </b> "
---

## Không sử dụng API Gateway

Khi không sử dụng API Gateway, bạn phải _trực tiếp_ gọi các hàm Lambda thông qua các URL hàm khác nhau, với bất kỳ phương thức HTTP nào như trong workshop trước:

```shell
curl 'https://u2z6j6noy3vnrynejsjqmkgiry0asnnm.lambda-url.ap-southeast-1.on.aws/'
```

```shell
curl 'https://qzpsv22gd3s4qbnfwz2v5yefoy0dmipa.lambda-url.ap-southeast-1.on.aws/' \
  -H 'content-type: application/json' \
  -d '{ "id": "a3127179-6ba4-4c3b-855a-4f65d4ee6345" }'
```

```shell
curl 'https://zvybyad2wvq5dto3upm2mgtcwa0epmul.lambda-url.ap-southeast-1.on.aws/' \
  -H 'content-type: application/json' \
  -d '{ "name": "First Cloud Journey", "email": "fcj@example.com" }'
```

```shell
curl 'https://hk3icryf6br2ociwan5ier2gqe0gyaoi.lambda-url.ap-southeast-1.on.aws/' \
  -H 'content-type: application/json' \
  -d '{ "id": "bcfe3cf9-1607-489e-8501-f99c194e6cc9", "email": "fcj@aws.com" }'
```

```shell
curl 'https://5ywq2njgsehqpl3xl2nrs334ue0inscy.lambda-url.ap-southeast-1.on.aws/' \
  -H 'content-type: application/json' \
  -d '{ "id": "bcfe3cf9-1607-489e-8501-f99c194e6cc9" }'
```

> [!NOTE]
> Lưu ý rằng mỗi lần bạn thực hiện một lệnh gọi HTTP đến một URL khác nhau, bạn - với tư cách là người dùng cuối - đang tự xử lý việc định tuyến đến API cho các thao tác CRUD.

## Với API Gateway

Sau khi tích hợp các hàm Lambda vào API Gateway, kiến trúc của chúng ta sẽ trông như thế này:

![alt text](/images/diagrams/workshop-2--api-gateway--rest-api--event.drawio.svg)

Sau khi tích hợp các hàm Lambda vào API Gateway với loại _REST API_,

- thay vì _trực tiếp_ gọi các hàm Lambda,
- bạn gọi REST API Gateway bằng cách sử dụng:
  - cùng một URL (URL _Invoke URL_ của API trong một stage)
  - các đường dẫn tài nguyên khác nhau
  - các phương thức HTTP khác nhau
- sau đó API Gateway sẽ _trực tiếp_ gọi các hàm Lambda của bạn.

## API Gateway đóng vai trò là trình kích hoạt cho các hàm Lambda

> [!NOTE]
> Khi một dịch vụ AWS khác trực tiếp gọi hàm Lambda của bạn, dịch vụ đó được gọi là _trigger_ (trình kích hoạt) cho hàm Lambda của bạn.

Trong trường hợp của chúng ta, API Gateway đóng vai trò là trình kích hoạt cho các hàm Lambda.

Về mặt kỹ thuật, khi chúng ta gọi API Gateway - một sự kiện xảy ra trong API Gateway:

- API Gateway tạo dữ liệu cho sự kiện đã xảy ra

  Dữ liệu này ở định dạng JSON chứa:
  - loại sự kiện
  - và các thông tin khác...

> [!NOTE]
> Dữ liệu được tạo này còn được gọi là _sự kiện được tạo_ (hoặc ngắn gọn là _sự kiện_).

- Sau đó, API Gateway trực tiếp gọi hàm Lambda của bạn với _(sự kiện được tạo)_.

> [!TIP]
> Chúc mừng, bạn vừa tạo kiến trúc hướng sự kiện (EDA) đầu tiên của mình trên AWS.

---

## Gọi REST API Gateway của chúng ta

> [!NOTE]
> Thay thế `https://pg6xn32zdc.execute-api.ap-southeast-1.amazonaws.com/dev` bằng Invoke URL của API của bạn.

```shell
# Gửi yêu cầu GET đến đường dẫn /users (để gọi list-users)
curl 'https://pg6xn32zdc.execute-api.ap-southeast-1.amazonaws.com/dev/users'
```

```shell
# Gửi yêu cầu POST đến đường dẫn /users (để gọi create-user)
curl 'https://pg6xn32zdc.execute-api.ap-southeast-1.amazonaws.com/dev/users' \
  -X POST \
  -H 'content-type: application/json' \
  -d '{ "name": "First Cloud Journey (API)", "email": "fcj-api@example.com" }'
```

```shell
# Gửi yêu cầu GET đến đường dẫn /users/{userId} (để gọi get-user)
curl 'https://pg6xn32zdc.execute-api.ap-southeast-1.amazonaws.com/dev/users/5aab87c6-1328-44c9-98c6-c556c1351591'
```

```shell
# Gửi yêu cầu PATCH đến đường dẫn /users/{userId} (để gọi update-user)
curl 'https://pg6xn32zdc.execute-api.ap-southeast-1.amazonaws.com/dev/users/5aab87c6-1328-44c9-98c6-c556c1351591' \
  -X PATCH \
  -H 'content-type: application/json' \
  -d '{ "name": "First Cloud Journey (API)", "email": "fcj-api@aws.com" }'
```

```shell
# Gửi yêu cầu DELETE đến đường dẫn /users/{userId} (để gọi delete-user)
curl 'https://pg6xn32zdc.execute-api.ap-southeast-1.amazonaws.com/dev/users/5aab87c6-1328-44c9-98c6-c556c1351591' \
  -X DELETE
```

![alt text](/images/workshop-2/API-Gateway--invoke-REST-API-methods.png)

> [!TIP]
> Nếu bạn vẫn còn giữ các URL hàm từ workshop trước, bây giờ bạn có thể xóa tất cả chúng. API Gateway có thể gọi các hàm Lambda này mà không cần các URL hàm.
