---
title: "Deploy the API to a stage"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

Simply creating and developing an API Gateway API doesn't automatically make it callable by your users. To make it callable, you must ["_deploy_ your API to a **stage**"](https://docs.aws.amazon.com/apigateway/latest/developerguide/rest-api-publish.html).

## Deployment and stage of an API Gateway's API

<!-- TODO: add diagram to clarify stage and deployment  -->

A _deployment_ is a **snapshot** of your API configuration.

- After you've updated your API configuration (resources, methods, integrations...), you must re-deploy your API to a stage so the changes is available for clients to invoke.

A _stage_ is a **named reference** to a _deployment_ of the API and is made available for client applications to call.

- For each stage of your API, you can configure different settings

  e.g. Cache, throttling, firewall/certificate settings...

- For example, you can have `dev`, `prod`, `v2` stages.

> [!TIP]
> Under the hood, you _deploy_ an API by creating a **deployment** and associating it with a **stage**.

## Endpoint URL and Invoke URL

Each API of Amazon API Gateway has

- a default _endpoint_ (aka hostname of the API) in the format of
  - `{api-id}.execute-api.{region}.amazonaws.com`, or
  - `{hostname}`

Each stage is available for client applications to call via

- a _base URL_ in the format of
  - `{protocol}://{hostname}/{stage}`, or
  - `https://{api-id}.execute-api.{region}.amazonaws.com/{stage}` (for REST API Gateway in our case).

---

To call a deployed API, the client submits a request against

- an _Invoke URL_ in the format of
  - `{protocol}://{hostname}/{stage}{resourcePath}`, or
  - `https://{api-id}.execute-api.{region}.amazonaws.com/{stage}{resourcePath}` (for REST API Gateway in our case).

For example

- the stage `dev` of a REST API is available at the Invoke URL: `https://{api-id}.execute-api.{region}.amazonaws.com/dev`

![alt text](../../images/workshop-2/api-gateway--invoke-url--stage.png)

- the root resource `/` of stage `dev` of the same REST API is available at the Invoke URL: `https://{api-id}.execute-api.{region}.amazonaws.com/dev/`

![alt text](../../images/workshop-2/api-gateway--invoke-url--root-resource.png)

- the resource `users` of stage `dev` of the same REST API is available at the Invoke URL: `https://{api-id}.execute-api.{region}.amazonaws.com/dev/users`

![alt text](../../images/workshop-2/api-gateway--invoke-url--users-resource.png)

## Deploy the API to dev stage

1. Open [APIs section](https://console.aws.amazon.com/apigateway/main/apis) of the API Gateway console.
2. In the list of the APIs, click on the name of the API (`UsersAPI`).
3. You will be redirected to the _Resources_ section of the `UsersAPI`.

4. Click `Deploy API`

![alt text](/images/workshop-2/API-Gateway--usersAPI--deploy-API.jpg)

5. In the _Deploy API_ popup.
   - State: Select `*New stage*`.
   - Stage name: Fill in `dev`.
   - Click `Deploy`.

![alt text](/images/workshop-2/API-Gateway--usersAPI--deploy-API--stage.jpg)

6. You will be redirected to the `Stages` page of `UsersAPI`.
7. Copy the `Invoke URL` of `dev` stage.

![alt text](/images/workshop-2/API-Gateway--usersAPI--stage--invoke-URL.jpg)

## Deploy or publish?

In the Lambda console, it's _Deploy API_, but in the AWS Lambda docs, it may also be _Publish API_.

![alt text](/images/workshop-2/api-gateway--deploy.png)

![alt text](/images/workshop-2/api-gateway--publish.png)
