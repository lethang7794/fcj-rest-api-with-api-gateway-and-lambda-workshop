---
title: "Note"
date: 2025-07-01T10:27:29+07:00
weight: 9
---

<!-- TODO: Move to apporiate section -->

What is exactly an event?

AWS has tools to generate event:

- [AWS SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/using-sam-cli.html) has [`sam local generate-event`](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/using-sam-cli-local-generate-event.html) to generate event payload samples for supported AWS services.
- [Amazon EventBridge](https://docs.aws.amazon.com/eventbridge/) has [schema registry](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-schema-registry.html) for schema that defines the structure and content of events that are passed on an event bus in Amazon EventBridge.
- [AWS Integrated Application Test Kit (AWS IATK)](https://aws.amazon.com/blogs/compute/aws-integrated-application-test-kit/) provides the capability for you to [generate mock events](https://awslabs.github.io/aws-iatk/tutorial/examples/generate_mock_events/) from a schema stored in the Amazon EventBridge schema registry.
