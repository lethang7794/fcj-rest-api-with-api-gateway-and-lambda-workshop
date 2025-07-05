---
title: "Test /users - GET method"
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

1. Open [APIs section](https://console.aws.amazon.com/apigateway/main/apis) of the API Gateway console.
2. In the list of the APIs, click on the name of the API (`UsersAPI`).
3. You will be redirected to the _Resources_ section of the `UsersAPI`.
4. Under `/users` resource, select `GET` method.
5. Open the `Test` tab.

![alt text](/images/workshop-2/API-Gateway--users-GET-method--test-tab.jpg)

6. Click `Test`.

7. Verify that the `list-users` Lambda function is invoked successfully, and the response has a list of users.

![alt text](/images/workshop-2/API-Gateway--users-GET-method--test-results.jpg)
