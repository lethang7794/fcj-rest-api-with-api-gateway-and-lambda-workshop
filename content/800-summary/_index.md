---
title: "Summary"
weight: 8
chapter: false
pre: " <b> 8. </b> "
---

In this workshop, you:

- Expose the Lambda functions to the internet as a RESTful API by using Amazon API Gateway (instead of using function URL as in previous workshop).

Because you're using the same Lambda functions as in previous workshop, you need to:

- Use Lambda _non-proxy integration_ and ensure that input to the Lambda function is supplied as the integration request payload.

In other words, you need to:

- Map any input data the client supplied as request parameters into the proper integration request body.

  E.g. From `/users/{userId}` path to `{ "id": "$input.params('userId')" }` body.

- Translate the client-supplied request body into a format recognized by the Lambda function.
