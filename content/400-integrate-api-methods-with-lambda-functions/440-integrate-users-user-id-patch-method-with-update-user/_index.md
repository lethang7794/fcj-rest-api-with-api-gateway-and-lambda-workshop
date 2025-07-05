---
title: "Integrate /users/{userId} - PATCH method with update-user"
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---

1. Go back to the _Resources_ section of the `UsersAPI` API in API Gateway console.
2. Select `/users/{userId}` resource.
3. Click `Create method`.

![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--create-method.jpg)

4. In the `Create method` page - `Method details` section:
   - `Method type`: Select `UPDATE`.
   - Integration type: Keep Lambda function.
   - Lambda function: Choose the `update-user` function.

![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--create-method-detail.jpg)

5. Keep other settings as default.
   - Scroll to the bottom and click `Create method`.

6. You will be redirect to the detail of the `/users/{userId} - PATCH` method.

![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--method-detail.jpg)

7. Open the `Integration request` tab.
8. In the `Integration request settings` section, click `Edit`.

![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--integration-request.jpg)

9. In the `Edit integration request` page, expand the `URL path parameters` section:
   - Click `Add path parameter`.
   - `Name`: Fill in `userId`.
   - `Mapped from`: Fill in `method.request.path.userId`.

![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--integration-request--URL-path-parameters.png)

10. Expand the `Mapping templates` section:
    - Click `Add mapping template`.
    - `Content type`: Fill in `application/json`.
    - `Template body`: Fill in:

      ```text
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

11. Scroll to the bottom, click `Save`.
