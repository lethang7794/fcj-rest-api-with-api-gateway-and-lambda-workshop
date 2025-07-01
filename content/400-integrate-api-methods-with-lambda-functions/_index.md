---
title: "Integrate API methods with Lambda functions"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

In this section, we'll connect our REST API endpoints to their corresponding Lambda functions. This integration will enable our API Gateway to trigger the appropriate Lambda functions based on the HTTP methods and routes. We'll cover the following integrations:

| API Resource - Method    | Lambda Function | Description                           |
| ------------------------ | --------------- | ------------------------------------- |
| `/users          GET`    | `list-users`    | Retrieve all users from the system    |
| `/users          POST`   | `create-user`   | Add a new user to the system          |
| `/users/{userId} GET`    | `get-user`      | Retrieve details of a specific user   |
| `/users/{userId} PATCH`  | `update-user`   | Modify an existing user's information |
| `/users/{userId} DELETE` | `delete-user`   | Remove a user from the system         |

Each integration will be configured with the appropriate request/response mappings to ensure seamless communication between API Gateway and Lambda functions.
