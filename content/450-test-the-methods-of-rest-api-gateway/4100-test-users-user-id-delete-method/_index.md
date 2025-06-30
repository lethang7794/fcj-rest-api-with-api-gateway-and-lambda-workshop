---
title: "Test /users/{userId} - DELETE method"
weight: 10
chapter: false
pre: " <b> 4.10 </b> "
---

1. Open the `Test` tab.
2. In `Test method` - `Path` - `userId` , fill in `d1d2f263-9a93-408c-a836-c13e24fcebf6`.

> [!NOTE]
> Replace the id value with the id of user created in previous step.

3. Click `Test`.

![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--test.jpg)

4. Verify that the `get-user` Lambda function is invoked successfully, and the response is the data of the user.

![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--test-results.jpg)
