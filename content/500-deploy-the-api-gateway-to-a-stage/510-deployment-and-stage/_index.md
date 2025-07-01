---
title: "Deployment and stage"
weight: 1
chapter: false
pre: " <b> 5.1 </b> "
---

<!-- TODO: add diagram to clarify stage and deployment  -->

A _deployment_ is a **snapshot** of your API configuration.

- After you've updated your API configuration (resources, methods, integrations...), you must re-deploy your API to a stage so the changes is available for clients to invoke.

A _stage_ is a **named reference** to a _deployment_ of the API and is made available for client applications to call.

- For each stage of your API, you can configure different settings

  e.g. Cache, throttling, firewall/certificate settings...

- For example, you can have `dev`, `prod`, `v2` stages.

> [!TIP]
> Under the hood, you _deploy_ an API by creating a **deployment** and associating it with a **stage**.
