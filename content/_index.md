---
title: TODO - Workshop title
weight: 1
chapter: false
---

# Workshop 2: Building REST APIs with Amazon API Gateway and AWS Lambda

In this workshop, you will:

- Create a RESTful API using Amazon API Gateway
- The API is backed by the serverless workload - the Lambda functions (created in previous workshop)

The architecture of the REST API looks like this

![alt text](/images/diagrams/workshop-2--api-gateway--rest-api.drawio.svg)

{{% toc %}}

## Introduction

**Amazon API Gateway** is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale.

- APIs act as the "front door" for applications to access data, business logic, or functionality from your backend services.
- Using API Gateway, you can create RESTful APIs and WebSocket APIs that enable real-time two-way communication applications.
- API Gateway supports containerized and serverless workloads, as well as web applications.

**AWS Lambda** is a serverless compute service that runs your code in response to events and automatically manages the underlying compute resources for you, making it easier to build applications that respond quickly to new information.

## Create REST API Gateway

- Open [APIs section](https://console.aws.amazon.com/apigateway/main/apis) of the API Gateway console.
- Click `Create API`.

  ![alt text](/images/workshop-2/API-Gateway--list-APIs.jpg)

- In the `Choose an API type` page, under the `REST API` type, click `Build`.

  ![alt text](/images/workshop-2/API-Gateway--create-type.jpg)

- In the `Create REST API` page:

  - API name: fill in `UsersAPI`
  - Click `Create API`

  ![alt text](/images/workshop-2/API-Gateway--create-detail.jpg)

## Integrate API methods with Lambda functions

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

## Deploy the API

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

## Invoke the methods of REST API Gateway

- Now instead of invoking the Lambdas function using different function URLs, with any HTTP methods as in previous workshop:

  ```shell
  curl 'https://u2z6j6noy3vnrynejsjqmkgiry0asnnm.lambda-url.ap-southeast-1.on.aws/'
  ```

  ```shell
  curl 'https://qzpsv22gd3s4qbnfwz2v5yefoy0dmipa.lambda-url.ap-southeast-1.on.aws/' \
    -H 'content-type: application/json' \
    -d '{ "id": "a3127179-6ba4-4c3b-855a-4f65d4ee6345" }'
  ```

  ```shell
  curl 'https://zvybyad2wvq5dto3upm2mgtcwa0epmul.lambda-url.ap-southeast-1.on.aws/' \
    -H 'content-type: application/json' \
    -d '{ "name": "First Cloud Journey", "email": "fcj@example.com" }'
  ```

  ```shell
  curl 'https://hk3icryf6br2ociwan5ier2gqe0gyaoi.lambda-url.ap-southeast-1.on.aws/' \
    -H 'content-type: application/json' \
    -d '{ "id": "bcfe3cf9-1607-489e-8501-f99c194e6cc9", "email": "fcj@aws.com" }'
  ```

  ```shell
  curl 'https://5ywq2njgsehqpl3xl2nrs334ue0inscy.lambda-url.ap-southeast-1.on.aws/' \
    -H 'content-type: application/json' \
    -d '{ "id": "bcfe3cf9-1607-489e-8501-f99c194e6cc9" }'
  ```

- After integrate the Lambda functions to the API Gateway with the type of _REST API_, you invoke your Lambda functions via the API Gateway using:

  - the same URL (the _Invoke URL_ of the API and the stage)
  - different resource paths
  - different HTTP methods

  > [!NOTE]
  > Replace `https://pg6xn32zdc.execute-api.ap-southeast-1.amazonaws.com/dev` with your API's Invoke URL.

  ```shell
  # Make a GET request to /users path (to invoke list-users)
  curl 'https://pg6xn32zdc.execute-api.ap-southeast-1.amazonaws.com/dev/users'
  ```

  ```shell
  # Make a POST request to /users path (to invoke create-user)
  curl 'https://pg6xn32zdc.execute-api.ap-southeast-1.amazonaws.com/dev/users' \
    -X POST \
    -H 'content-type: application/json' \
    -d '{ "name": "First Cloud Journey (API)", "email": "fcj-api@example.com" }'
  ```

  ```shell
  # Make a GET request to /users/{userId} path (to invoke get-user)
  curl 'https://pg6xn32zdc.execute-api.ap-southeast-1.amazonaws.com/dev/users/5aab87c6-1328-44c9-98c6-c556c1351591'
  ```

  ```shell
  # Make a PATCH request to /users/{userId} path (to invoke update-user)
  curl 'https://pg6xn32zdc.execute-api.ap-southeast-1.amazonaws.com/dev/users/5aab87c6-1328-44c9-98c6-c556c1351591' \
    -X PATCH \
    -H 'content-type: application/json' \
    -d '{ "name": "First Cloud Journey (API)", "email": "fcj-api@aws.com" }'
  ```

  ```shell
  # Make a DELETE request to /users/{userId} path (to invoke delete-user)
  curl 'https://pg6xn32zdc.execute-api.ap-southeast-1.amazonaws.com/dev/users/5aab87c6-1328-44c9-98c6-c556c1351591' \
    -X DELETE
  ```

  ![alt text](/images/workshop-2/API-Gateway--invoke-REST-API-methods.png)

> [!TIP]
> Now you can delete all the function URLs that have been created with your Lambda functions. The API Gateway can invoke these Lambda functions without the function URLs.

## Cleanup

> [!NOTE]
> Keep these resources if you want to continue with the next workshop.

<!-- TODO: link to next workshop  -->

In additional to the resources in:

- Workshop 1: DynamoDB, Lambda functions, IAM Roles.

The AWS resource you need to cleanup in this workshop is the API Gateway:

- Open [APIs section](https://console.aws.amazon.com/apigateway/main/apis) of the API Gateway console.
- In the list of the APIs, click on the name of the API (`UsersAPI`).
- Click `Delete`.

  ![alt text](/images/workshop-2/API-Gateway--delete-API.png)

- Type in `confirm`
- Click `Delete`.

  ![alt text](/images/workshop-2/API-Gateway--delete-API-confirm.png)

## Summary

In this workshop, you:

- Expose the Lambda functions to the internet as a RESTful API by using Amazon API Gateway (instead of using function URL as in previous workshop).

Because you're using the same Lambda functions as in previous workshop, you need to

- use Lambda _non-proxy integration_ and ensure that input to the Lambda function is supplied as the integration request payload.

In other words, you need to:

- map any input data the client supplied as request parameters into the proper integration request body.

  e.g. From `/users/{userId}` path to `{ "id": "$input.params('userId')" }` body.

- translate the client-supplied request body into a format recognized by the Lambda function.
