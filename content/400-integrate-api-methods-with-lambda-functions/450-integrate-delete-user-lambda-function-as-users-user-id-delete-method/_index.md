---
title: "Integrate delete-user Lambda function as /users/{userId} - DELETE method"
weight: 9
chapter: false
pre: " <b> 4.9 </b> "
---

- Go back to the _Resources_ section of the `UsersAPI` API in API Gateway console.
- Select `/users/{userId}` resource.
- Click `Create method`.

  ![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--create-method.jpg)

- In the `Create method` page':

  - In `Method details` section:

    - `Method type`: Select `DELETE`.
    - Integration type: Keep Lambda function.
    - Lambda function: Choose the `delete-user` function.

    ![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--create-method-detail.jpg)

  - Keep other settings as default.

  - Scroll to the bottom and click `Create method`.

- You will be redirect to the detail of the `/users/{userId} - DELETE` method.

  ![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--method-detail.png)

- Open the `Integration request` tab.
- In the `Integration request settings` section, click `Edit`.

  ![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--integration-request.jpg)

- In the `Edit integration request` page:

  ![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--integration-request-detail.jpg)

  - Expand the `URL path parameters` section:

    - Click `Add path parameter`.

    - `Name`: Fill in `userId`.
    - `Mapped from`: Fill in `method.request.path.userId`.

  - Expand the `Mapping templates` section:

    - Click `Add mapping template`.

    - `Content type`: Fill in `application/json`.
    - `Template body`: Fill in:

      ```json
      {
        "id": "$input.params('userId')"
      }
      ```

      ![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--integration-request--URL-path-parameters-and-mapping-template-body.jpg)

  - Scroll to the bottom, click `Save`.
