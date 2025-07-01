---
title: "Integrate /users/{userId} - GET method with get-user"
weight: 5
chapter: false
pre: " <b> 4.5 </b> "
---

    
1. Go back to the _Resources_ section of the `UsersAPI` API in API Gateway console.
2. Select `/users` resource.
3. Click `Create resource`.

![alt text](/images/workshop-2/API-Gateway--users-userId--create-resource.jpg)

4. In the `Create resource` page:

    - For `Resource path`: Choose `/users`
    - For `Resource name`: Fill in `{userId}`.
  
      > [!NOTE]
      > Be aware of the two brackets: `{` and `}`.
  
    - Click `Create resource`.
  
![alt text](/images/workshop-2/API-Gateway--users-userId--create-resource-detail.jpg)
  
5. Click on the `/users/{userId}` resource you've just created.
6. Click `Create method`.

![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--create-method.jpg)

7. In the `Create method` page':

    - In `Method details` section:

      - `Method type`: Select `GET`.
      - Integration type: Keep Lambda function.
      - Lambda function: Choose the `get-user` function.

![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--create-method-detail.jpg)

    - Keep other settings as default.

    - Scroll to the bottom and click `Create method`.

8. You will be redirect to the detail of the `/users/{userId} - GET` method.

![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--method-detail.jpg)

9. Open the `Integration request` tab.
10. In the `Integration request settings` section, click `Edit`.

![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--integration-request.jpg)

11. In the `Edit integration request` page:

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
