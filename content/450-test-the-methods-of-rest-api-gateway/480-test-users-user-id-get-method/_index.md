---
title: "Test /users/{userId} - GET method"
weight: 6
chapter: false
pre: " <b> 4.6 </b> "
---

- Open the `Test` tab.
- In `Test method` - `Path` - `userId` , fill in `d1d2f263-9a93-408c-a836-c13e24fcebf6`.

  > [!NOTE]
  > Replace the id value with the id of user created in previous step.

- Click `Test`.

  ![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--test-path.jpg)

- Verify that the `get-user` Lambda function is invoked successfully, and the response is the data of the user.

  ![alt text](/images/workshop-2/API-Gateway--users-userId-GET-method--test-results.jpg)
