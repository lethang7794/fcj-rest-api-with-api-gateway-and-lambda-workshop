---
title: "Test methods of REST API Gateway"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

In this section, we'll test our REST API Gateway endpoints using the AWS Management Console. The console provides a user-friendly interface to verify each endpoint's functionality before deploying to a stage.

## Testing Process

1. **Access the Test tab of each API resource - method**
   - Navigate to API Gateway in AWS Console
   - Select your API and the desired resource/method
   - Open the Test tab

2. **Test each resource - method**

   | API Resource - Method    | Lambda Function | Test requirement                             |
   | ------------------------ | --------------- | -------------------------------------------- |
   | `/users          GET`    | `list-users`    | Return all users from the                    |
   | `/users          POST`   | `create-user`   | A new user is added to the system            |
   | `/users/{userId} GET`    | `get-user`      | Return detail of a specific user             |
   | `/users/{userId} PATCH`  | `update-user`   | The user detail is updated with the new data |
   | `/users/{userId} DELETE` | `delete-user`   | The user is removed from the system          |

3. **Verify Responses**
   - Check HTTP status codes
   - Validate response payloads
   - [Optional] Review CloudWatch logs for Lambda execution details

The Management Console's test feature allows you to quickly validate your API without needing to deploy it to a stage, making it ideal for development and debugging.
