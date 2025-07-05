---
title: "Summary"
weight: 9
chapter: false
pre: " <b> 9. </b> "
---

## Summary

In this workshop, you:

- Expose the Lambda functions to the internet as a RESTful API by using Amazon API Gateway (instead of using function URL as in previous workshop).

Because you're using the same Lambda functions as in previous workshop, you need to:

- Use Lambda _non-proxy integration_ and ensure that input to the Lambda function is supplied as the integration request payload.

In other words, you need to:

- Map any input data the client supplied as request parameters into the proper integration request body.

  E.g. From `/users/{userId}` path to `{ "id": "$input.params('userId')" }` body.

- Translate the client-supplied request body into a format recognized by the Lambda function.

## What's next

If you're interest more in how to integrate API Gateway with Lambda functions, check the following documentations:

- [Events and triggers - How Lambda works - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/concepts-basics.html#gettingstarted-concepts-event)
- [Invoking Lambda with events from other AWS services - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/lambda-services.html#lambda-invocation-trigger)
- [Invoking a Lambda function using an Amazon API Gateway endpoint - AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/services-apigateway.html)

Otherwise, you can go to the next workshop to learn about:

- Integrating a frontend application with API Gateway.
- Hosting a frontend application with S3

<!-- TODO: add link to next workshop -->
