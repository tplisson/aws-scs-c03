# AWS Certified Security - Specialty (SCS-C03): Exam Prep Notes

<a align="center" href="https://aws.amazon.com/certification/certified-security-specialty/">
  <img src="images/aws-scs-badge.png" {:height="25%" width="25%"}>
</a>

Private notes, labs and progress tracking for the AWS Certified Security - Specialty exam (SCS-C03). The approach is hands-on first: every exam task statement that can be practised in a sandbox has a lab, and every lab ends with a "break it, then fix it" step.

## Exam snapshot

| Domain | Weight | Lab guide |
|---|---|---|
| 1. Detection | 16% | [labs/domain-1-detection.md](labs/domain-1-detection.md) |
| 2. Incident Response | 14% | [labs/domain-2-incident-response.md](labs/domain-2-incident-response.md) |
| 3. Infrastructure Security | 18% | [labs/domain-3-infrastructure-security.md](labs/domain-3-infrastructure-security.md) |
| 4. Identity and Access Management | 20% | [labs/domain-4-iam.md](labs/domain-4-iam.md) |
| 5. Data Protection | 18% | [labs/domain-5-data-protection.md](labs/domain-5-data-protection.md) |
| 6. Security Foundations and Governance | 14% | [labs/domain-6-governance.md](labs/domain-6-governance.md) |

- 50 scored questions plus 15 unscored.
- Pass mark: 750 on a 100-1000 scale; scoring is compensatory (you pass the exam overall, not per domain).
- Question types: multiple choice, multiple response, ordering, matching.
- Target candidate: roughly 3-5 years of experience securing cloud solutions.

## Repository layout

```
.
├── README.md                  # this file
├── training-plan.md           # 8-week schedule, principles, guardrails
├── progress-tracker.md        # diagnostic/practice scores and lab checklist
├── labs/
│   ├── 00-sandbox-setup.md    # Week 0: lab estate and diagnostic
│   ├── domain-1-detection.md
│   ├── domain-2-incident-response.md
│   ├── domain-3-infrastructure-security.md
│   ├── domain-4-iam.md
│   ├── domain-5-data-protection.md
│   └── domain-6-governance.md
└── notes/
    └── decision-cards.md      # requirement -> service -> why not the alternatives
```

## How to use this repo

1. Read [training-plan.md](training-plan.md) once, then do [labs/00-sandbox-setup.md](labs/00-sandbox-setup.md).
2. Take the diagnostic exam cold and record domain scores in [progress-tracker.md](progress-tracker.md).
3. Work through the weeks in order. For each lab: build it, break it, fix it, then write a decision card in [notes/decision-cards.md](notes/decision-cards.md).
4. Tick off labs in the tracker. Re-run any lab you fail on a practice question.
5. Finish with timed practice exams (Week 8).

## Repo hygiene (private repo, but still)

- Never commit AWS account IDs, access keys, session tokens, ARNs of real resources, IdP metadata or screenshots showing them. Use placeholders such as `111111111111`.
- Keep infrastructure-as-code in the repo only if it contains no secrets; use parameters for anything account-specific.
- Add a `.gitignore` for `*.pem`, `*.key`, `.env`, `.terraform/` and `*.tfstate`.

## Sources

- Official SCS-C03 exam guide and in-scope service list (AWS Certification).
- AWS Skill Builder: official SCS-C03 practice question set and exam prep plan.
- AWS service documentation, reading Troubleshooting and Security best practices sections first.

> [!NOTE]
> The per-domain task statements in the lab guides were taken from a secondary summary of the official exam guide. Verify them against the official domain pages and fix any drift.
