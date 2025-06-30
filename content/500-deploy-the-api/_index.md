---
title: "Deploy the API"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

- Open [APIs section](https://console.aws.amazon.com/apigateway/main/apis) of the API Gateway console.
- In the list of the APIs, click on the name of the API (`UsersAPI`).
- You will be redirected to the _Resources_ section of the `UsersAPI`.

- Click `Deploy API`

  ![alt text](/images/workshop-2/API-Gateway--usersAPI--deploy-API.jpg)

- In the _Deploy API_ popup.

  - State: Select `*New stage*`.
  - Stage name: Fill in `dev`.
  - Click `Deploy`.

  ![alt text](/images/workshop-2/API-Gateway--usersAPI--deploy-API--stage.jpg)

- You will be redirected to the `Stages` page of `UsersAPI`.
- Copy the `Invoke URL` of `dev` stage.

  ![alt text](/images/workshop-2/API-Gateway--usersAPI--stage--invoke-URL.jpg)
