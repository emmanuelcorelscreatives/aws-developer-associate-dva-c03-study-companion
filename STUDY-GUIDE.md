# AWS Developer Associate DVA-C03 practice companion

## Version and purpose

This material targets DVA-C03, available **December 1, 2026**. DVA-C02 remains in use through **November 30, 2026**. Check AWS's current guide before booking. The directory's older C02 name records preparation history, not the target of the selected bank.

These are six original practice forms with 65 questions each. They are not actual or recalled exam questions and are not affiliated with or endorsed by AWS. This is a practice-test companion, not a beginner programming course or a replacement for hands-on development.

## A useful attempt cycle

1. Take one form in 130 minutes without looking up answers. Record uncertain choices, including guesses that turn out correct.
2. Review **every option explanation**. State the decisive requirement in your own words: consistency, authorization, failure handling, release identity, data protection, or time budget.
3. Open the linked official source. Compare the specific integration and its assumptions; do not generalize one service's behavior to every service.
4. Classify errors as missing knowledge, missed constraint, wrong API/identity, wrong event shape, stale evidence, or an unsafe assumption.
5. Use the review journal and a focused exercise before another form. Repeating a memorized answer is not the same as explaining the decision.

All 65 practice questions are scored. The official guide describes 50 scored and 15 unscored exam questions, and a scaled passing score of 720. A practice percentage is **not** an AWS scaled score. The existing 70% practice benchmark is a study setting, not a prediction or guarantee.

## C03 domain guide

| Domain | Weight | Decisions to rehearse |
| --- | ---: | --- |
| Development with AWS Services | 30% | SDK contracts, sync/async events, Lambda integration, data access, AI-assisted coding and managed AI integration |
| Security | 26% | Federation, temporary credentials, scoped permissions, presigned access, encryption/secrets, safe AI service use |
| Testing and Deployment | 22% | Artifact/configuration preparation, container images, tests and environments, CI/CD release and rollback |
| Troubleshooting and Optimization | 22% | Root-cause evidence, logs/metrics/traces, runtime health, resource/cache/concurrency tradeoffs, AI-assisted diagnosis |

The bank's integer domain allocation totals 116/101/86/87 over 390 questions. It approximates the official weights; AWS does not prescribe these per-practice-form counts. Concepts deliberately recur across forms. Unique stems do not imply zero conceptual overlap or calibrated psychometric equivalence.

## Changes to notice from C02

- Old sensitive-data task 2.3 content maps to C03 2.2. C03 **2.3 now means AI security**: service access, privacy, filtering, agent interactions and sensitive logging.
- Domain 3 is **Testing and Deployment**, with tasks 3.1–3.3. Container build/release and AI-assisted testing/release are explicit additions.
- Lambda performance tuning belongs in optimization; local SAM testing is testing, not proof of deployed IAM/network behavior.
- AI suggestions are proposals to evaluate against code, tests and operational evidence. They are not a substitute for authorization, user consent, release criteria or measured performance.
- Bedrock's non-training commitment, network privacy, service retention and optional invocation logging are separate questions. Read the current service/model-specific terms and settings; do not assume that private transport means no payload can be retained.

## Quick decision checklist

- **Identity:** Which principal actually performs the call: user, assumed-role session, Lambda execution role, ECS task role or ECS execution role?
- **Contract:** Which invocation type, event schema, pagination token, batch result or callback identifier is required?
- **Failure:** Is the operation retryable, partially successful, duplicated, out of order, rejected, or already ambiguous? What is bounded?
- **Data:** What consistency, lifetime, cache key and retention are required? Does a cached value cross an identity boundary?
- **Release:** Which exact artifact/digest/revision was tested and deployed? Is a rollback target available and eligible?
- **Evidence:** Does the log/metric/trace belong to this request, environment, version and time window?

## Documentation lifecycle

Links and service features change. The internal source snapshots were captured November 24–25, 2026; use live official documentation when applying a feature. In particular, the captured Amazon Q Developer code-review page announces IDE-plugin support ending April 30, 2027 and points to Kiro for similar capabilities. The exam skills concern AI-assisted workflows, not permanent availability of a particular IDE menu. Recheck that tool-specific material before use after its lifecycle date.

You can complete the practice tests without an AWS account. Any optional cloud exercise requires an authorized nonproduction account, spending controls and cleanup. Never use real customer data or production credentials for these exercises.
