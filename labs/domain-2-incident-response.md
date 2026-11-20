# Domain 2: Incident Response (14%) - Week 7

## Lab 2.1: Automated containment runbook (tasks 2.1.1, 2.1.2, 2.1.4, 2.2.4)

- Scenario: a GuardDuty finding says an instance's role credentials are being used from an unexpected place.
- Build an EventBridge rule that starts a Step Functions or SSM Automation runbook that: tags the instance, snapshots its volumes, swaps in an isolation security group, and revokes active role sessions (the IAM "revoke sessions" mechanism adds a deny based on `aws:TokenIssueTime`).
- Deploy AWS's **Automated Forensics Orchestrator for Amazon EC2** solution and compare it to your runbook.

## Lab 2.2: Forensics and root cause analysis (tasks 2.2.1-2.2.3, 2.2.5)

- Mount the evidence snapshot in an isolated forensic VPC with no internet path and a separate KMS key. Write down the chain-of-custody steps.
- Investigate the same event end to end with **Amazon Detective**, CloudTrail and Athena. Produce a timeline: initial access, actions taken, resources touched, blast radius.

## Lab 2.3: Test the plan (task 2.1.3)

- Run an **AWS Fault Injection Service** experiment in the workload account. Check that alarms fire, runbooks trigger and recovery works.
- Simulate an S3 data-destruction event and recover with versioning and AWS Backup. Record the recovery time.

## Lab 2.4: Capstone game day

- Using a low-privilege test role, perform realistic misuse with the CLI: enumerate resources, attempt privilege escalation, and read a canary bucket.
- Switch to defender: detect, scope, contain, eradicate, recover, and write a one-page post-incident report. Tie every step back to a task statement from Domains 1 and 2.
