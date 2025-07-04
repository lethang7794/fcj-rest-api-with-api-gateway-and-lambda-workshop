---
title: "Invoke the methods of REST API Gateway"
weight: 7
chapter: false
pre: " <b> 7. </b> "
---

## Without API Gateway

Without an API Gateway, you _directly_ invoke the Lambdas function using different function URLs, with any HTTP methods as in previous workshop:

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
> Notice each time, you make a HTTP call to a different URL, you - as the end user - are handling the routing to the API for CRUD operations.

## With API Gateway

After integrate the Lambda functions to the API Gateway, our architect now looks like this:

![alt text](/images/diagrams/workshop-2--api-gateway--rest-api--event.drawio.svg)

After integrate the Lambda functions to the API Gateway with the type of _REST API_,

- instead of _directly_ invoking the Lambda functions,
- you call the REST API Gateway using:
  - the same URL (the _Invoke URL_ of the API in a stage)
  - different resource paths
  - different HTTP methods
- then the API Gateway also _directly_ invoke your Lambda functions.

## API Gateway acts as a trigger for Lambda functions

> [!NOTE]
> When an other AWS service directly invoke your Lambda function, that's service is called a _trigger_ for your Lambda function.

In our case, the API Gateway is acting as a trigger for the Lambda functions.

Under the hood, when we call the API Gateway - an event occurs in API Gateway:

- API Gateway generates data for that occurred event

  The data is in JSON format contains
  - the event type
  - other information...

> [!NOTE]
> This generated data is also know as _generated event_ (or in short _event_).

- API Gateway then directly invoke your Lambda function with the _(generated) event_.

> [!TIP]
> Congratulation, you just create your first event-driven architect in AWS.

---

## Invoke our REST API Gateway

> [!NOTE]
> Replace `https://pg6xn32zdc.execute-api.ap-southeast-1.amazonaws.com/dev` with your API's Invoke URL.

```shell
# Make a GET request to /users path (to invoke list-users)
curl 'https://pg6xn32zdc.execute-api.ap-southeast-1.amazonaws.com/dev/users'
```

```shell
# Make a POST request to /users path (to invoke create-user)
curl 'https://pg6xn32zdc.execute-api.ap-southeast-1.amazonaws.com/dev/users' \
  -X POST \
  -H 'content-type: application/json' \
  -d '{ "name": "First Cloud Journey (API)", "email": "fcj-api@example.com" }'
```

```shell
# Make a GET request to /users/{userId} path (to invoke get-user)
curl 'https://pg6xn32zdc.execute-api.ap-southeast-1.amazonaws.com/dev/users/5aab87c6-1328-44c9-98c6-c556c1351591'
```

```shell
# Make a PATCH request to /users/{userId} path (to invoke update-user)
curl 'https://pg6xn32zdc.execute-api.ap-southeast-1.amazonaws.com/dev/users/5aab87c6-1328-44c9-98c6-c556c1351591' \
  -X PATCH \
  -H 'content-type: application/json' \
  -d '{ "name": "First Cloud Journey (API)", "email": "fcj-api@aws.com" }'
```

```shell
# Make a DELETE request to /users/{userId} path (to invoke delete-user)
curl 'https://pg6xn32zdc.execute-api.ap-southeast-1.amazonaws.com/dev/users/5aab87c6-1328-44c9-98c6-c556c1351591' \
  -X DELETE
```

![alt text](/images/workshop-2/API-Gateway--invoke-REST-API-methods.png)

> [!TIP]
> If you still keep the function URLs in previous workshop, now you can delete all of them. The API Gateway can invoke these Lambda functions without the function URLs.
