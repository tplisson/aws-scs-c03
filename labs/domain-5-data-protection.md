# Domain 5: Data Protection (18%) - Week 4

## Lab 5.1: KMS deep dive (tasks 5.2.1, 5.3.2, 5.3.3, 5.3.5)

- Create a customer managed key, then test: key policy only, versus key policy enabling IAM, versus a **grant**. Understand why IAM permissions alone do nothing if the key policy does not allow it.
- Reproduce the classic failure: an S3 bucket encrypted with SSE-KMS in account A, read by a role in account B. Fix it with both the key policy and the caller's IAM policy.
- Create a **multi-Region key** and replicate it. Create a key with **imported key material** and note that rotation of imported material is manual. Read about external key stores and CloudHSM but do not provision CloudHSM (hourly cost).
- Add a `kms:ViaService` condition and watch direct use fail.

## Lab 5.2: Integrity, retention and backup (tasks 5.2.2-5.2.4)

- Enable versioning and **S3 Object Lock** in governance mode, then compliance mode on a test bucket. Learn what even the root user cannot do in compliance mode; do not use it on anything you want to delete soon.
- Add lifecycle rules. Build an **AWS Backup** plan with a vault, cross-account copy and **Backup Vault Lock**. Run a restore.
- Write the ransomware story in a decision card: which controls stop an attacker with admin credentials, and which do not.

## Lab 5.3: Encryption in transit and private access (tasks 5.1.1-5.1.3)

- Put an ALB in front of a test instance with an ACM certificate, a modern TLS security policy and HTTP-to-HTTPS redirect. Prove old TLS versions are rejected with `openssl s_client`.
- Create gateway and interface **VPC endpoints** with endpoint policies, and an S3 bucket policy that only allows access through your endpoint (`aws:SourceVpce`).
- Expose a service to the other account via **PrivateLink**.

## Lab 5.4: Secrets and sensitive data (tasks 5.3.1, 5.3.4)

- Store a database credential in **Secrets Manager** with automatic rotation. Break the rotation Lambda's network path and diagnose it.
- Create a **CloudWatch Logs data protection policy** that masks sample card numbers, and an **SNS message data protection** policy. Confirm masking from the log output.
