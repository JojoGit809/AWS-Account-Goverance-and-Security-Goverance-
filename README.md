# AWS-Account-Goverance-and-Security-Goverance-
Showing AWS Security Architecture 

# AWS Security Governance & Monitoring Lab

## Overview
This lab demonstrates the implementation of foundational AWS security, identity management, logging, compliance monitoring, and cost governance controls using core AWS services.

---

## Module 1: Identity Center and IAM Security Foundations

### Root Account Security
- Enabled Multi-Factor Authentication (MFA) for the root user
- Verified MFA assignment in Security Credentials
- Secured privileged access following least privilege principles

### AWS IAM Identity Center Configuration
- Enabled IAM Identity Center using default directory
- Created administrative user
- Enforced MFA registration for Identity Center user
- Created permission sets:
  - `AdministratorAccess`
  - `ReadOnlyAccess`
- Assigned permission sets to AWS account
- Deployed IAM Access Analyzer (Zone of Trust: Current Account)

**Security Impact:** Strengthened identity governance, enforced MFA, and implemented role-based access control (RBAC).

---

## Module 2: Logging and Monitoring Setup

### CloudTrail Configuration
- Created multi-region trail: `AccountTrail`
- Enabled:
  - Log file validation
  - Management events (Read/Write)
  - CloudTrail Insights
  - SSE-KMS encryption (KMS alias: `cloudtrail-key`)
- Configured secure S3 log storage

### CloudWatch Security Alarms
Created alarms for:
- CloudTrail API activity
- Root account usage
- IAM policy changes
- Console login failures (≥3 within 5 minutes)

Integrated with Amazon SNS topic `SecurityAlerts` for real-time notifications.

**Security Impact:** Enabled continuous monitoring and real-time alerting of suspicious activity.

---

## Module 3: AWS Config and Compliance Automation

### AWS Config Setup
- Enabled recording for all supported resources
- Included global resources
- Configured delivery to dedicated S3 bucket
- Enabled SNS notifications (`ConfigAlerts`)

### CloudFormation Deployment
Deployed `account-governance.yaml` stack to implement automated compliance rules:

- IAM Password Policy Check
- Root Account MFA Check
- IAM User MFA Check
- CloudTrail Enabled Check
- S3 Bucket Public Write Protection Check

**Compliance Impact:** Established automated continuous compliance monitoring aligned with security best practices.

---

## Module 4: Security Hub Implementation

### Enabled Security Standards
- AWS Foundational Security Best Practices
- CIS AWS Foundations Benchmark
- PCI DSS v3.2.1

### Configurations
- Enabled automatic control updates
- Enabled Security Hub across new accounts
- Integrated with:
  - GuardDuty
  - Inspector
  - IAM Access Analyzer
  - AWS Config

Reviewed findings via Summary Dashboard and Insights panel.

**Security Impact:** Centralized visibility into security posture and compliance findings.

---

## Module 5: Cost Governance and Budget Controls

### AWS Budgets
- Created monthly cost budget
- Configured alert thresholds:
  - 50%
  - 80%
  - 100%
- Configured email notifications

### Cost Explorer
- Enabled cost analysis
- Created saved reports:
  - Monthly cost by service
  - Cost by tag

**Governance Impact:** Implemented financial monitoring and proactive cost management controls.

---

## Skills Demonstrated

- AWS Identity & Access Management (IAM)
- MFA Enforcement & Privileged Access Security
- Role-Based Access Control (RBAC)
- CloudTrail Logging & Encryption
- CloudWatch Monitoring & Alerting
- SNS Notification Configuration
- AWS Config Rule Deployment
- CloudFormation Infrastructure as Code
- Security Hub & Compliance Standards
- Continuous Security Monitoring
- Cloud Cost Governance

---

## Outcome

This lab demonstrates hands-on implementation of enterprise-grade AWS security architecture including identity governance, logging, threat detection, compliance automation, and cost controls aligned with industry standards and cloud security best practices.
