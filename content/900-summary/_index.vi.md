---
title: "Tổng kết"
weight: 9
chapter: false
pre: " <b> 9. </b> "
---

## Tổng kết

Trong workshop này, bạn đã:

- Tiếp xúc các hàm Lambda với internet dưới dạng RESTful API bằng cách sử dụng Amazon API Gateway (thay vì sử dụng URL hàm như trong workshop trước).

Vì bạn đang sử dụng cùng các hàm Lambda như trong workshop trước, bạn cần:

- Sử dụng _tích hợp không phải proxy_ (non-proxy integration) của Lambda và đảm bảo rằng đầu vào cho hàm Lambda được cung cấp dưới dạng tải trọng yêu cầu tích hợp.

Nói cách khác, bạn cần:

- Ánh xạ bất kỳ dữ liệu đầu vào nào mà client cung cấp dưới dạng tham số yêu cầu vào phần thân yêu cầu tích hợp phù hợp.

  Ví dụ: Từ đường dẫn `/users/{userId}` sang phần thân `{ "id": "$input.params('userId')" }`.

- Chuyển đổi phần thân yêu cầu do client cung cấp sang định dạng mà hàm Lambda có thể nhận dạng được.

## Bước tiếp theo

Nếu bạn quan tâm nhiều hơn về cách tích hợp API Gateway với các hàm Lambda, hãy xem các tài liệu sau:

- [Sự kiện và trình kích hoạt - Cách hoạt động của Lambda - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/concepts-basics.html#gettingstarted-concepts-event)
- [Kích hoạt Lambda với sự kiện từ các dịch vụ AWS khác - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/lambda-services.html#lambda-invocation-trigger)
- [Kích hoạt hàm Lambda bằng điểm cuối Amazon API Gateway - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/services-apigateway.html)

Nếu không, bạn có thể chuyển sang workshop tiếp theo để tìm hiểu về:

- Tích hợp ứng dụng frontend với API Gateway.
- Lưu trữ ứng dụng frontend với S3

<!-- TODO: add link to next workshop -->
