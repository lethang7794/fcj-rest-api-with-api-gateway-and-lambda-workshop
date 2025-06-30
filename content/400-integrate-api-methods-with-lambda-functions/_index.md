---
title: "Integrate Lambda functions with API methods"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

### Integrate `list-users` Lambda function as `/users - GET` method

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

#### Test `/users - GET` method

- Open the `Test` tab.
- Click `Test`.

  ![alt text](/images/workshop-2/API-Gateway--users-GET-method--test-tab.jpg)

- Verify that the `list-users` Lambda function is invoked successfully, and the response has a list of users.

  ![alt text](/images/workshop-2/API-Gateway--users-GET-method--test-results.jpg)

### Integrate `create-user` Lambda function as `/users - POST` method

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

#### Test `/users - POST` method

- Click `Test`.

  ![alt text](/images/workshop-2/API-Gateway--users-POST-method--test-request.jpg)

- Verify that the `create-users` Lambda function is invoked successfully, and the response is the created user.

  ![alt text](/images/workshop-2/API-Gateway--users-POST-method--test-results.jpg)

### Integrate `get-user` Lambda function as `/users/{userId} - GET` method

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

#### Test `/users/{userId} - GET` method

- Open the `Test` tab.
- In `Test method` - `Path` - `userId` , fill in `d1d2f263-9a93-408c-a836-c13e24fcebf6`.

  > [!NOTE]
  > Replace the id value with the id of user created in previous step.

- Click `Test`.

  ![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--test-path.jpg)

- Verify that the `get-user` Lambda function is invoked successfully, and the response is the data of the user.

  ![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--test-results.jpg)

### Integrate `update-user` Lambda function as `/users/{userId} - PATCH` method

- Go back to the _Resources_ section of the `UsersAPI` API in API Gateway console.
- Select `/users/{userId}` resource.
- Click `Create method`.

  ![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--create-method.jpg)

- In the `Create method` page':

  - In `Method details` section:

    - `Method type`: Select `UPDATE`.
    - Integration type: Keep Lambda function.
    - Lambda function: Choose the `update-user` function.

    ![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--create-method-detail.jpg)

  - Keep other settings as default.

  - Scroll to the bottom and click `Create method`.

- You will be redirect to the detail of the `/users/{userId} - PATCH` method.

  ![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--method-detail.jpg)

- Open the `Integration request` tab.
- In the `Integration request settings` section, click `Edit`.

  ![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--integration-request.jpg)

- In the `Edit integration request` page:

  - Expand the `URL path parameters` section:

    - Click `Add path parameter`.
    - `Name`: Fill in `userId`.
    - `Mapped from`: Fill in `method.request.path.userId`.

      ![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--integration-request--URL-path-parameters.png)

  - Expand the `Mapping templates` section:

    - Click `Add mapping template`.

    - `Content type`: Fill in `application/json`.
    - `Template body`: Fill in:

      ```json
      ## Parse the request body into a JSON object
      #set($inputRoot = $input.path('$'))
      {
        #foreach($key in $inputRoot.keySet())
          "$key": "$util.escapeJavaScript($inputRoot.get($key))"#if($foreach.hasNext),#end
        #end,
        "id": "$input.params('userId')"
      }
      ```

      ![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--integration-request--mapping-template-body.png)

  - Scroll to the bottom, click `Save`.

#### Test `/users/{userId} - PATCH` method

- Open the `Test` tab.
- In the Request body field, fill in:

  ```json
  {
    "id": "d1d2f263-9a93-408c-a836-c13e24fcebf6",
    "email": "tranvanan@gmail.com",
    "name": "Tran Van An"
  }
  ```

  > [!NOTE]
  > Replace the id value with the id of user created in previous step.

- Click `Test`.

  ![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--test-request.jpg)

- Verify that the `update-user` Lambda function is invoked successfully, and the response is the data of updated user.

  ![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--test-results.jpg)

### Integrate `delete-user` Lambda function as `/users/{userId} - DELETE` method

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

#### Test `/users/{userId} - DELETE` method

- Open the `Test` tab.
- In `Test method` - `Path` - `userId` , fill in `d1d2f263-9a93-408c-a836-c13e24fcebf6`.

  > [!NOTE]
  > Replace the id value with the id of user created in previous step.

- Click `Test`.

  ![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--test.jpg)

- Verify that the `get-user` Lambda function is invoked successfully, and the response is the data of the user.

  ![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--test-results.jpg)
