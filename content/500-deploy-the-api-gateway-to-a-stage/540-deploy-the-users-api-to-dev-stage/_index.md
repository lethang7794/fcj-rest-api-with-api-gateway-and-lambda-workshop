---
title: "Deploy the UsersAPI to dev stage"
weight: 4
chapter: false
pre: " <b> 5.4 </b> "
---

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

> [!TIP]
> Congratulations, you have deployed an API Gateway. Copy the invoke URL of the `dev` stage, you will need it in the next step.
