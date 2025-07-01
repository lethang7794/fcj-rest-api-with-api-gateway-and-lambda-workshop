---
title: "Integrate API methods with Lambda functions"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

In this section, we'll connect our REST API endpoints to their corresponding Lambda functions. This integration will enable our API Gateway to trigger the appropriate Lambda functions based on the HTTP methods and routes. We'll cover the following integrations:

| API Method               | Lambda Function | Description                           |
| ------------------------ | --------------- | ------------------------------------- |
| `GET    /users`          | `list-users`    | Retrieve all users from the system    |
| `POST   /users`          | `create-user`   | Add a new user to the system          |
| `GET    /users/{userId}` | `get-user`      | Retrieve details of a specific user   |
| `PATCH  /users/{userId}` | `update-user`   | Modify an existing user's information |
| `DELETE /users/{userId}` | `delete-user`   | Remove a user from the system         |

Each integration will be configured with the appropriate request/response mappings to ensure seamless communication between API Gateway and Lambda functions.
