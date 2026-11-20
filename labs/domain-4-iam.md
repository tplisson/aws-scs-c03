# Domain 4: Identity and Access Management (20%) - Weeks 2-3

## Lab 4.1: Workforce identity and ABAC (tasks 4.1.1, 4.2.2)

- In IAM Identity Center, create groups, permission sets and session duration limits. Federate an external IdP if you have one; otherwise use the built-in directory.
- Implement **ABAC**: users and resources carry a `project` tag, and one policy using `aws:PrincipalTag/project` and `aws:ResourceTag/project` grants access to matching resources. Compare to the RBAC version and count the policies each needs.
- **Break it:** remove the tag from a resource and diagnose the AccessDenied from CloudTrail alone.

## Lab 4.2: Policy evaluation workout (tasks 4.2.1, 4.2.3, 4.2.4)

- Build one scenario with all layers: identity policy, **permissions boundary**, SCP, **session policy** and resource policy. Before each test, predict allow or deny in writing, then verify with the IAM Policy Simulator and a real call.
- Set up a cross-account role with a trust policy using `sts:ExternalId` and `aws:PrincipalOrgID`. Learn which side's policy is needed for same-account versus cross-account access.
- Build a table for yourself: implicit deny, explicit deny, and which policy types can only restrict.

## Lab 4.3: Find and fix unintended access (tasks 4.2.4-4.2.5)

- Enable **IAM Access Analyzer** for external access and unused access. Deliberately create a bucket policy and a KMS key policy granting external access, and a role that goes unused.
- Generate a least-privilege policy from CloudTrail activity for a test role, then use a custom policy check to validate a proposed policy against a rule such as "no wildcard actions on KMS".

## Lab 4.4: Temporary credentials (tasks 4.1.2-4.1.3)

- Assume a role through a chain of two roles and observe the session limits.
- Create an S3 presigned URL using an assumed role's credentials and observe that it dies when the role session expires, regardless of the URL's stated expiry.
- Set up a **Cognito** user pool with an identity pool giving users scoped S3 access. Troubleshoot a deliberately broken trust relationship.

## Lab 4.5: Machine identity and fine-grained authorization (task 4.2.1)

- Configure **IAM Roles Anywhere** with a private CA (delete the CA right after; it is billed monthly) so a workload gets temporary credentials without access keys.
- Optional: build a small **Amazon Verified Permissions** policy store with a Cedar policy and test authorization decisions.
