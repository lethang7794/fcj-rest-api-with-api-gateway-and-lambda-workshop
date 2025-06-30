---
title: "Test /users/{userId} - PATCH method"
weight: 8
chapter: false
pre: " <b> 4.8 </b> "
---

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
