---
title: "Endpoint URL and Invoke URL"
weight: 3
chapter: false
pre: " <b> 6.3. </b> "
---

Each API of Amazon API Gateway has

- a default _endpoint_ (aka hostname of the API) in the format of
  - `{api-id}.execute-api.{region}.amazonaws.com`, or
  - `{hostname}`

Each stage is available for client applications to call via

- a _base URL_ in the format of
  - `{protocol}://{hostname}/{stage}`, or
  - `https://{api-id}.execute-api.{region}.amazonaws.com/{stage}` (for REST API Gateway in our case).

---

To call a deployed API, the client submits a request against

- an _Invoke URL_ in the format of
  - `{protocol}://{hostname}/{stage}{resourcePath}`, or
  - `https://{api-id}.execute-api.{region}.amazonaws.com/{stage}{resourcePath}` (for REST API Gateway in our case).

For example:

- The stage `dev` of a REST API is available at the Invoke URL: `https://{api-id}.execute-api.{region}.amazonaws.com/dev`

![alt text](/images/workshop-2/api-gateway--invoke-url--stage.png)

- The root resource `/` of stage `dev` of the same REST API is available at the Invoke URL: `https://{api-id}.execute-api.{region}.amazonaws.com/dev/`

![alt text](/images/workshop-2/api-gateway--invoke-url--root-resource.png)

- The resource `users` of stage `dev` of the same REST API is available at the Invoke URL: `https://{api-id}.execute-api.{region}.amazonaws.com/dev/users`

![alt text](/images/workshop-2/api-gateway--invoke-url--users-resource.png)
