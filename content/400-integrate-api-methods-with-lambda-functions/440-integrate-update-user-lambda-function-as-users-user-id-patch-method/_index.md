---
title: "Integrate update-user Lambda function as /users/{userId} - PATCH method"
weight: 7
chapter: false
pre: " <b> 4.7 </b> "
---


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
