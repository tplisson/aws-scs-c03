# Domain 3: Infrastructure Security (18%) - Week 5

## Lab 3.1: Edge protection (task 3.1)

- Serve a static site from S3 through **CloudFront with Origin Access Control**, then block direct S3 access.
- Attach **AWS WAF** with a managed rule group, a rate-based rule and a geo rule. Test with `curl` loops. Configure S3 CORS wrongly, then correct it.
- Read how Shield Advanced is enabled and what it adds, but do not subscribe (large fixed cost).

## Lab 3.2: Hardened compute and secure admin access (tasks 3.2.1-3.2.5)

- Build an **EC2 Image Builder** pipeline producing a hardened AMI. Launch from it with **IMDSv2 required**, no inbound ports and **Session Manager** access only.
- Create a **Patch Manager** baseline and maintenance window, and view compliance. Enable **Inspector** and read the findings for the instance.
- **Break it:** remove the instance profile permission for SSM and diagnose why the instance vanishes from Systems Manager.

## Lab 3.3: Pipeline and container security (tasks 3.2.3, 3.2.6)

- Push a deliberately vulnerable container image to ECR and a Lambda function with an outdated dependency; use Inspector scanning on both.
- Add a CodeGuru Security or Amazon Q Developer scan stage to a build, and fail the build on high-severity findings.

## Lab 3.4: Network controls and segmentation (tasks 3.3.1-3.3.5)

- Build a three-tier VPC. Use security group references between tiers, and a network ACL that you break by forgetting **ephemeral ports** (NACLs are stateless).
- Deploy **AWS Network Firewall** with a Suricata-compatible rule and a domain allow list for egress. Billed hourly: build, test and tear down in one session.
- Run **Reachability Analyzer** and **Network Access Analyzer** to find unintended paths. Turn on **Route 53 Resolver DNS Firewall** and block a test domain.
- Study (read-only): Site-to-Site VPN, Direct Connect with MACsec, Verified Access.

## Lab 3.5: Guardrails for generative AI applications (task 3.2.7)

- Create an **Amazon Bedrock Guardrail** with prompt-attack filtering, PII masking and a denied topic. Call a model with and without it. Map each control to an item in the OWASP Top 10 for LLM Applications.
- Write a least-privilege IAM policy for invoking one model only, put Bedrock behind an interface VPC endpoint, and enable model invocation logging to a KMS-encrypted bucket.
