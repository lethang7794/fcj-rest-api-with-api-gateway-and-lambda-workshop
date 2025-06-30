---
title: "Integrate create-user Lambda function as /users - POST method"
weight: 3
chapter: false
pre: " <b> 4.3 </b> "
---

- Go back to the _Resources_ section of the `UsersAPI` API in API Gateway console.
- Select `/users` resource.
- Click `Create method`.

  ![alt text](/images/workshop-2/API-Gateway--users-POST-method--create-method.jpg)

- In the `Create method` page:

  - In `Method details` section:

    - `Method type`: Select `POST`.
    - Integration type: Keep Lambda function.
    - Lambda function: Choose the `create-user` function.

    ![alt text](/images/workshop-2/API-Gateway--users-POST-method--create-method-detail.jpg)

  - Keep other settings as default.

  - Scroll to the bottom and click `Create method`.

- You will be redirect to the detail of the `/users - POST` method.

  ![alt text](/images/workshop-2/API-Gateway--users-POST-method--method-detail.jpg)

- Open the `Test` tab.
- In the Request body field, fill in:

  ```json
  {
    "email": "tranvana@gmail.com",
    "name": "Tran Van A"
  }
  ```
