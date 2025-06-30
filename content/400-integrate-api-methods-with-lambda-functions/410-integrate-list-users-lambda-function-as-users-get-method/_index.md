---
title: "Integrate list-users Lambda function as /users - GET method"
weight: 1
chapter: false
pre: " <b> 4.1 </b> "
---

- Open [APIs section](https://console.aws.amazon.com/apigateway/main/apis) of the API Gateway console.
- In the list of the APIs, click on the name of the API (`UsersAPI`).

  ![alt text](/images/workshop-2/API-Gateway--API-detail.png)

- You will be redirected to the _Resources_ section of the `UsersAPI`.

> [!TIP]
> After you create an API, you will be automatically redirected
>
> - from the _APIs_ section of the API Gateway
> - to the _Resources_ section of that API (e.g. `API: UsersAPI`).

- Click `Create resource`

  ![alt text](/images/workshop-2/API-Gateway--create-resource.jpg)

- In the `Create resource` page

  - For `Resource path`: Choose `/`
  - For `Resource name`: Fill in `users`.
  - Click `Create resource`.

  ![alt text](/images/workshop-2/API-Gateway--users-resource--create-resource-detail.jpg)

- Click on the `users` resource you've just created.
- Click `Create method`.

  ![alt text](/images/workshop-2/API-Gateway--users-GET-method--create-method.jpg)

- In the `Create method` page:

  - In `Method details` section:

    - `Method type`: Select `GET`.
    - Integration type: Keep Lambda function.
    - Lambda function: Choose the `list-users` function.

    ![alt text](/images/workshop-2/API-Gateway--users-GET-method--create-method-detail.jpg)

  - Keep other settings as default.

  - Scroll to the bottom and click `Create method`.

    ![alt text](/images/workshop-2/API-Gateway--users-GET-method--create-button.jpg)

- You will be redirect to the detail of the `/users - GET` method.

  ![alt text](/images/workshop-2/API-Gateway--users-GET-method.jpg)
