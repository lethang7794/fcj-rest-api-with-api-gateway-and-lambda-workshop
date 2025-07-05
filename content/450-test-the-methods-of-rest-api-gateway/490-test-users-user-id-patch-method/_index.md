---
title: "Test /users/{userId} - PATCH method"
weight: 4
chapter: false
pre: " <b> 5.4 </b> "
---

1. In the _Resources_ section of the `UsersAPI`.
2. Under `/users` resource's `{userId}` resource, select `POST` method.

3. Open the `Test` tab.
4. In the Request body field, fill in:

   > [!NOTE]
   > Replace the id value with the id of user created in previous step.

   ```json
   {
     "id": "d1d2f263-9a93-408c-a836-c13e24fcebf6",
     "email": "tranvanan@gmail.com",
     "name": "Tran Van An"
   }
   ```

![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--test-request.jpg)

5. Click `Test`.

6. Verify that the `update-user` Lambda function is invoked successfully, and the response is the data of updated user.

![alt text](/images/workshop-2/API-Gateway--users-userId-PATCH-method--test-results.jpg)
