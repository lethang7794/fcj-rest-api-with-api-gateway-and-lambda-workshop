---
title: "Test /users/{userId} - DELETE method"
weight: 10
chapter: false
pre: " <b> 4.10 </b> "
---

- Open the `Test` tab.
- In `Test method` - `Path` - `userId` , fill in `d1d2f263-9a93-408c-a836-c13e24fcebf6`.

  > [!NOTE]
  > Replace the id value with the id of user created in previous step.

- Click `Test`.

  ![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--test.jpg)

- Verify that the `get-user` Lambda function is invoked successfully, and the response is the data of the user.

  ![alt text](/images/workshop-2/API-Gateway--users-userId-DELETE-method--test-results.jpg)
