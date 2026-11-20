# Domain 6: Security Foundations and Governance (14%) - Week 1

## Lab 6.1: Organization guardrails (tasks 6.1.1-6.1.4)

- Enable AWS Organizations features, register a delegated administrator for GuardDuty and Security Hub, and optionally stand up Control Tower to see what a landing zone deploys.
- Write three SCPs: deny leaving the organization, deny use of non-approved Regions (exempt global services), and deny disabling CloudTrail and GuardDuty.
- Write a **resource control policy (RCP)** restricting access to your S3 buckets to principals in your organization, and a **declarative policy** that enforces an account-wide setting.
- **Break it:** confirm the SCPs do not apply to the management account, and that an SCP never grants permissions; it only sets the ceiling.

## Lab 6.2: Root user and break-glass (task 6.1.5)

- Use centralized root access management to remove root credentials from a member account, then perform a privileged root task through a short-lived root session.
- Design and document a break-glass role: who can assume it, how it is alarmed in CloudTrail and EventBridge, how it is tested.

## Lab 6.3: Secure, repeatable deployment (task 6.2)

- Deploy a baseline (an S3 log bucket with a KMS key, an IAM role, a Config recorder) to both member accounts with **CloudFormation StackSets**.
- Write two **CloudFormation Guard** rules (reject unencrypted S3 buckets; reject security groups open to 0.0.0.0/0 on port 22) and run them with cfn-lint locally against a good and a bad template.
- Share a subnet or prefix list with **AWS RAM**, and publish one approved product in **Service Catalog**.
- Create a tag policy and use tags for cost allocation and, later, ABAC.

## Lab 6.4: Compliance evaluation and auto-remediation (task 6.3)

- Deploy an AWS Config conformance pack organization-wide, aggregate to the security-tooling account, and enable a Security Hub standard.
- Create a Config rule for public S3 buckets with an SSM Automation remediation. **Break it:** make a bucket public and time detection plus remediation.
- Browse AWS Artifact reports, create an Audit Manager assessment, and run the Well-Architected Tool security review on a sample workload.
