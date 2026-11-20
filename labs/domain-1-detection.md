# Domain 1: Detection (16%) - Week 6

## Lab 1.1: Organization-wide logging (task 1.2)

- Create an **organization CloudTrail trail** delivering to a log-archive bucket in the security account, with SSE-KMS, log file validation and a bucket policy that denies deletion. Add CloudTrail Lake if it is available in your account.
- Turn on VPC Flow Logs, Route 53 Resolver query logs, and S3 server access or data event logging for one bucket.
- Query with **Athena** and **CloudWatch Logs Insights**: who called `DeleteTrail`, which IPs were rejected, which domains were resolved.

## Lab 1.2: Threat detection and aggregation (task 1.1)

- Enable **GuardDuty** organization-wide with the extra protection plans (S3, runtime, Lambda, malware). Enable **Security Hub** with cross-Region aggregation.
- Generate sample findings, then trigger a few real ones (for example, an instance resolving a known-bad test domain). Route high-severity findings through **EventBridge** to SNS.
- Create a CloudWatch metric filter and alarm for root user logins and console logins without MFA.

## Lab 1.3: Data lake and sensitive data discovery (tasks 1.1.4, 1.2.3, 1.2.5)

- Enable **Amazon Security Lake** (check current pricing and any free trial first), then query OCSF-normalised data with Athena.
- Create an S3 bucket filled with fake PII records and run a **Macie** discovery job. Review how findings reach Security Hub.

## Lab 1.4: Troubleshooting drill (task 1.3)

Break and repair each of these, noting the symptom first:

- A CloudWatch agent with a bad config or missing instance profile permission.
- A Lambda function with no log permissions.
- API Gateway access logging without the account-level CloudWatch role.
- A CloudFront standard logging destination with the wrong bucket settings.
- A trail whose bucket policy blocks delivery.
