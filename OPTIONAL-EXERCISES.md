# Optional developer exercises

These are learning activities, not a claim that the author performed a lab. No exercise is a mandatory pilot or publication gate. Use local code and documentation where possible. For cloud work, use only an authorized isolated nonproduction account, synthetic data, least privilege and a spending budget. Avoid public endpoints/buckets unless deliberately required and reviewed. Record resource names and delete only your exercise resources afterward. Never copy production credentials, patient details, customer records or real secrets into an assistant, test fixture or log.

## 1. Partial success and a stable retry contract

Create a local handler fixture with five logical records and one deterministic failure. Write tests that distinguish whole-batch failure from an explicitly reported failed-record list. Give the same business operation the same idempotency identity across two deliveries. Record why a receipt/message delivery ID may differ from the business-operation identity. Compare your fixture with the exact Lambda/SQS integration contract before any optional deployment.

Evidence to keep: input events, expected failed identifiers, assertions for successful records and a note about standard versus FIFO ordering. A local fixture does not prove live Lambda event-source configuration.

## 2. Data access and pagination

Model a key-based query that returns an empty filtered page with a continuation token. Make the next page return a match. Test that an empty item list does not by itself stop pagination. Separately compare table/LSI/GSI read consistency options in the official docs. Do not confuse a filter with a key condition or assume a GSI can perform a strongly consistent read.

Evidence to keep: fake responses, requested next tokens and the final logical result. If you optionally use DynamoDB, use a small synthetic table and remove only that table after recording the outcome.

## 3. Identity boundaries without real secrets

Draw the AWS principal for each action in an ECS workflow: pulling an image, injecting a startup secret and making an S3 SDK call from application code. Use placeholder ARNs. Compare taskRoleArn and executionRoleArn. Review one narrowly scoped policy and one applicable deny. Explain why adding an allow does not override an explicit deny.

Evidence to keep: the principal/action/resource table and policy reasoning. A policy simulator result is not proof of a production request; do not change live policies for this exercise.

## 4. Safe managed-AI integration

Using synthetic text and a local mocked response, test allowed output, blocked output, masked output, validation error and retryable throttle handling. Distinguish ordinary response text from structured tool arguments. Validate and authorize a proposed tool action before invoking a fake side effect. Keep session ownership server-side and test that another user's session ID is rejected.

Evidence to keep: state transitions, consent/denial handling and the redacted diagnostic record. For optional real inference, first verify the chosen service/model's access, current data terms, retention and logging configuration. Private connectivity and a non-training commitment do not imply that every logging/retention control is already correct. Use a bounded request budget.

## 5. Generated code and meaningful tests

Ask an approved AWS development assistant to explain or modify a nonsecret small function. Use an explicit behavior requirement. Inspect the diff for a changed boolean condition, numeric representation, exception handling or unsupported API. Generate tests, then ensure at least one regression test fails on the deliberately buggy implementation and passes only after the real repair.

Evidence to keep: requirement, before/after diff, expected values and actual test output. Do not call a generated test file, a green mock or a line-coverage percentage independent expert validation.

## 6. Reproducible container release

Build a tiny local image using pinned dependencies. Record its image identity and the difference between a tag and a digest. Confirm the health command exists inside the final image and exits nonzero for a failing synthetic health endpoint. Review how an ECS task-definition revision is selected by a service and how a rolling deployment's percentages affect replacement.

Evidence to keep: Dockerfile, local image identity and health command results. Optional ECR pushes and ECS tasks can incur charges; do not provision a cluster merely to answer a paper exercise. Preview lifecycle selections before any optional image cleanup and preserve every digest still needed for deployment/rollback.

## 7. Source-bound deployment validation

Create a local release record that names one artifact hash and its test result. Deliberately attach a previous release's result and make a validation script reject the mismatch. Compare this with your existing pipeline's artifact inputs, validation hooks and authorized approval action. An AI-generated release summary should reference the same current version, not replace the actual test/approval event.

Evidence to keep: artifact identity, current result, rejected stale result and the exact validation rule. No real production deployment is required.

## 8. Troubleshooting and measured optimization

Generate synthetic structured logs with request, environment, version and status fields. Write a query/analysis that isolates one incident and excludes another environment. Record a baseline before changing a retry budget, cache rule, concurrency limit or memory setting in a local benchmark. Compare correctness, latency and resource use, not just one smaller configuration number.

Evidence to keep: scoped input data, hypothesis, one controlled change and measured result. Local results are not a universal AWS performance guarantee. Never delete contradictory evidence merely because it conflicts with an assistant's suggestion.
