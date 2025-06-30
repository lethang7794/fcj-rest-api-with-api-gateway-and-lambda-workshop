---
title: "Integrate get-user Lambda function as /users/{userId} - GET method"
weight: 5
chapter: false
pre: " <b> 4.5 </b> "
---


- Go back to the _Resources_ section of the `UsersAPI` API in API Gateway console.
- Select `/users` resource.
- Click `Create resource`.

  ![alt text](/images/workshop-2/API-Gateway--users-userId--create-resource.jpg)

- In the `Create resource` page:

  - For `Resource path`: Choose `/users`
  - For `Resource name`: Fill in `{userId}`.

    > [!NOTE]
    > Be aware of the two brackets: `{` and `}`.

  - Click `Create resource`.

    ![alt text](/images/workshop-2/API-Gateway--users-userId--create-resource-detail.jpg)

- Click on the `/users/{userId}` resource you've just created.
- Click `Create method`.

  ![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--create-method.jpg)

- In the `Create method` page':

  - In `Method details` section:

    - `Method type`: Select `GET`.
    - Integration type: Keep Lambda function.
    - Lambda function: Choose the `get-user` function.

    ![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--create-method-detail.jpg)

  - Keep other settings as default.

  - Scroll to the bottom and click `Create method`.

- You will be redirect to the detail of the `/users/{userId} - GET` method.

  ![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--method-detail.jpg)

- Open the `Integration request` tab.
- In the `Integration request settings` section, click `Edit`.

  ![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--integration-request.jpg)

- In the `Edit integration request` page:

  ![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--integration-request-detail.jpg)

  - Expand the `URL path parameters` section:

    - Click `Add path parameter`.

      ![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--integration-request--URL-path-parameters.png)

    - `Name`: Fill in `userId`.
    - `Mapped from`: Fill in `method.request.path.userId`.

      ![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--integration-request--URL-path-parameters--userId.png)

  - Expand the `Mapping templates` section:

    - Click `Add mapping template`.

      ![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--integration-request--mapping-template.png)

    - `Content type`: Fill in `application/json`.
    - `Template body`: Fill in:

      ```json
      {
        "id": "$input.params('userId')"
      }
      ```

      ![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--integration-request--mapping-template-body.png)

  - Scroll to the bottom, click `Save`.
