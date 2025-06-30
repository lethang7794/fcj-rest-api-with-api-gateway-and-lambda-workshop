---
title: "Deploy the API to a stage"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

Simply creating and developing an API Gateway API doesn't automatically make it callable by your users. To make it callable, you must deploy your API to a stage.

## Deployment and stage of API Gateway

<!-- TODO: add diagram to clarify stage and deployment  -->

A _deployment_ is a **snapshot** of your API configuration.

A stage is a **named reference** to a _deployment_ of the API and is made available for client applications to call.

A stage is a named reference to a deployment, which is a snapshot of the API.
Stages are environments that you can deploy your API to. For example, you can create `development` or `production` stages.

You can configure different settings for each stage of your API. For changes to take effect, you must first deploy your API.

---

An API _stage_ is a logical reference to a lifecycle state of your API (for example, `dev`, `prod`, `beta`, or `v2`).

- API stages are identified by their API ID and stage name, and they're included in the URL you use to invoke the API.
- Each stage is a **named reference** to a _deployment_ of the API and is made available for client applications to call.
- You can create a `$default` stage that is served from the base of your API's URL—for example, `https://{api_id}.execute-api.{region}.amazonaws.com/`. You use this URL to invoke an API stage.

---

After you deploy an API to a stage, it’s available for clients to invoke. You must deploy an API for changes to take effect. If you enable automatic deployments, changes to an API are automatically released for you.

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
