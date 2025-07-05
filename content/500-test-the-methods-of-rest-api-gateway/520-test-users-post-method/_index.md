---
title: "Test /users - POST method"
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---

1. In the _Resources_ section of the `UsersAPI`.
2. Under `/users` resource, select `POST` method.
3. Open `Test` tab.
4. In the Request body field, fill in:

   ```json
   {
     "email": "tranvana@gmail.com",
     "name": "Tran Van A"
   }
   ```

![alt text](/images/workshop-2/API-Gateway--users-POST-method--test-request.jpg)

5. Click `Test`.

6. Verify that the `create-users` Lambda function is invoked successfully, and the response is the created user.

![alt text](/images/workshop-2/API-Gateway--users-POST-method--test-results.jpg)
