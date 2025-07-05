---
title: "Test /users/{userId} - DELETE method"
weight: 5
chapter: false
pre: " <b> 5.5. </b> "
---

1. In the _Resources_ section of the `UsersAPI`.
2. Under `/users` resource's `{userId}` resource, select `POST` method.

3. Open the `Test` tab.
4. In `Test method` - `Path` - `userId` , fill in `d1d2f263-9a93-408c-a836-c13e24fcebf6`.

   > [!NOTE]
   > Replace the id value with the id of user created in previous step.

![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--test.jpg)

5. Click `Test`.
6. Verify that the `get-user` Lambda function is invoked successfully, and the response is the data of the user.

![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--test-results.jpg)
