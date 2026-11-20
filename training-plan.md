# Training Plan

An 8-week, hands-on plan: about 8-10 hours per week, roughly 60% labs. Compress any domain the diagnostic shows you already know.

## Design principles

1. **Break it, then fix it.** Every lab ends with a deliberate misconfiguration. The exam is heavy on troubleshooting (tasks 1.3, 3.1-3.3, 4.1, 4.2).
2. **Governance first.** Domain 6 labs create the multi-account sandbox every later lab reuses.
3. **Weight time by domain weight**, with IAM getting the most.
4. **Decision cards.** After each lab write one card: requirement -> service chosen -> why not the alternatives. Scenario questions are almost always "which option best meets the constraint".
5. **Ordering and matching questions** reward knowing workflow sequences (for example, steps to contain a compromised instance). Practise stating workflows out loud.

## Schedule

| Week | Focus | Weight | Labs |
|---|---|---|---|
| 0 | Sandbox and diagnostic | n/a | [00](labs/00-sandbox-setup.md) |
| 1 | Domain 6: Foundations and Governance | 14% | [6.1-6.4](labs/domain-6-governance.md) |
| 2-3 | Domain 4: IAM | 20% | [4.1-4.5](labs/domain-4-iam.md) |
| 4 | Domain 5: Data Protection | 18% | [5.1-5.4](labs/domain-5-data-protection.md) |
| 5 | Domain 3: Infrastructure Security | 18% | [3.1-3.5](labs/domain-3-infrastructure-security.md) |
| 6 | Domain 1: Detection | 16% | [1.1-1.4](labs/domain-1-detection.md) |
| 7 | Domain 2: Incident Response and capstone | 14% | [2.1-2.4](labs/domain-2-incident-response.md) |
| 8 | Timed practice exams, weak-spot labs, review | all | repeat failed labs |

**Weekly rhythm:** two or three 2-hour lab blocks, one 1-hour reading block on the official docs for that domain's services, one 45-minute timed question set, and 30 minutes writing decision cards.

## Week 8: consolidation

- **Days 1-2:** full timed practice exam (official practice questions plus one reputable third-party set). Aim for consistently above 80% before booking the real exam.
- **Days 3-5:** for every wrong answer, rebuild the relevant lab in 20 minutes or less, then rewrite the decision card.
- **Days 6-7:** second timed exam, review ordering and matching questions especially, rest the day before.
- Review the exam guide's in-scope and out-of-scope service lists so you do not spend time on excluded services.

## Cost and safety guardrails

- Use a dedicated sandbox organization with no production data, a billing alarm, and one or two approved Regions.
- Build, test and delete in the same session: Network Firewall, Private CA, Verified Access, Client VPN, NAT gateways, and Security Lake or Macie after any free trial. Check current pricing and trial terms before enabling each.
- Do not provision CloudHSM or subscribe to Shield Advanced; learn them from documentation.
- Never use real credentials, real PII or a production account for break-it exercises. Use canary data only.
- At the end of each week, list resources (Resource Explorer or Billing console) and confirm teardown.
