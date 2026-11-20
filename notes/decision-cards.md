# Decision Cards

One card per lab or per missed question. Format:

> **Requirement:** what the scenario demands (constraint words matter: least operational overhead, cross-account, no internet, immutable, near real time)
> **Choose:** the service/feature
> **Why:** the deciding reason
> **Not:** the tempting alternatives and why they fail

## Examples (replace with your own)

> **Requirement:** Prevent any principal in member accounts from disabling CloudTrail, even administrators.
> **Choose:** SCP denying `cloudtrail:StopLogging` and `cloudtrail:DeleteTrail`.
> **Why:** SCPs set an organization-wide ceiling that account admins cannot override.
> **Not:** IAM policies (admins can edit them); permissions boundaries (apply only to attached roles/users); note SCPs do not affect the management account.

> **Requirement:** Role in account B must read an SSE-KMS encrypted object in account A.
> **Choose:** Key policy in A allowing the role, plus the role's own IAM policy allowing `kms:Decrypt`.
> **Why:** Cross-account KMS use needs both sides to allow it.
> **Not:** Bucket policy alone; IAM policy alone.

## Cards

<!-- Add cards below, grouped by domain -->

### Domain 1: Detection

### Domain 2: Incident Response

### Domain 3: Infrastructure Security

### Domain 4: IAM

### Domain 5: Data Protection

### Domain 6: Governance
