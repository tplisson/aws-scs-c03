# Week 0: Sandbox and Diagnostic (about 4 hours)

## Lab 0.1: Build the lab estate

- Create a fresh AWS Organization with three accounts: **management**, **security-tooling** (delegated admin for security services) and **workload**. Use email aliases, MFA on every root user, and no long-lived IAM user keys. Use IAM Identity Center and CLI SSO profiles.
- In the management account, set a Budgets alert at a threshold you are comfortable with, plus an alert on forecasted spend.
- Pick one or two Regions for all work. You will enforce this with an SCP later (Lab 6.1).
- Keep everything in IaC where practical (CloudFormation or Terraform) so teardown is one command.

## Diagnostic

Take a timed set of official practice questions (AWS Skill Builder publishes an official SCS-C03 practice question set) **cold**. Record the score per domain in [../progress-tracker.md](../progress-tracker.md). Do not study for it; the result tells you which weeks to shorten.
