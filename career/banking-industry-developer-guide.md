# Banking Industry Guide for Developers

This document provides broad, practical banking knowledge that helps software engineers build safer, compliant, and operationally reliable systems at a bank.

## Why Banking Engineering Is Different

Banks are high-trust, highly regulated institutions. Software changes can affect money movement, customer trust, legal obligations, and financial stability.

Typical engineering constraints in banking:
- Strong auditability and traceability requirements
- Strict security and privacy controls
- Heavy change management and release governance
- High availability and disaster recovery expectations
- Long-lived legacy systems alongside modern platforms

## Core Banking Domain Concepts

### Account Types

Common account categories:
- Demand deposit accounts (checking)
- Savings accounts
- Credit accounts (cards, lines of credit)
- Loan accounts (mortgage, auto, personal)

Key developer concept:
- Account balance is usually not just one number. Systems often track available balance, current balance, holds, pending transactions, and ledger balance.

### Ledger and Transactions

Banking systems depend on accurate ledgers.

Important principles:
- Double-entry accounting concepts influence many transaction systems.
- Transactions should be immutable events; corrections are often posted as reversing entries.
- Idempotency is critical to prevent duplicate posting.

### Posting and Settlement

A transaction can pass through stages:
1. Authorization or initiation
2. Pending or memo posting
3. Clearing and settlement
4. Final posting and reconciliation

Engineering implication:
- Build workflows that handle state transitions explicitly and safely.

### Interest, Fees, and Accruals

Many products involve periodic calculations:
- Daily interest accrual
- Monthly statement generation
- Fee assessment and waivers

Engineering implication:
- Time-based jobs and end-of-day/batch processes are core to banking operations.

## Common Banking Systems You May Integrate With

- Core banking platform
- Card processor and card network interfaces
- Payments rails (ACH, wire, RTP, SWIFT, etc.)
- Loan servicing systems
- Fraud and AML systems
- Customer identity and KYC systems
- General ledger and finance platforms
- Data warehouse, reporting, and regulatory reporting tools

## Payments Basics for Developers

### ACH (in many regions)
- Batch-oriented and typically lower-cost.
- Not generally immediate final settlement.

### Wire Transfers
- High-value and more urgent transfer path.
- Strong controls and approvals are common.

### Card Payments
- Authorization, clearing, and chargeback lifecycle.
- Often near-real-time authorization with later clearing.

### Real-Time Payments
- Faster funds movement with low tolerance for downtime.
- Requires robust fraud, limits, and availability controls.

Developer takeaway:
- Different rails have different SLAs, failure modes, cutoffs, and reconciliation patterns.

## Regulatory and Compliance Themes (High Level)

Regulations vary by country and product. Banks typically enforce controls aligned to:

- Customer identification and KYC requirements
- AML monitoring and suspicious activity reporting
- Data privacy and retention requirements
- Consumer protection and fair lending controls
- Sanctions screening and watchlist checks
- Financial and operational risk governance

Developer takeaway:
- Compliance is not just policy documentation. It is implemented in code, controls, logs, approvals, and evidence.

## Security Expectations in Banking Engineering

Common baseline expectations:
- Strong authentication and authorization
- Least privilege access model
- Encryption in transit and at rest
- Secrets management and key rotation
- Detailed audit logging for sensitive actions
- Segregation of duties for high-risk changes
- Secure SDLC with code scanning and dependency checks

Practical patterns:
- Tokenize or mask sensitive account and PII fields.
- Use immutable, tamper-evident audit trails for sensitive workflows.
- Build explicit approval and dual-control flows for high-risk operations.

## Data and Privacy Considerations

### Data Classification

Most banks classify data by sensitivity, such as:
- Public
- Internal
- Confidential
- Restricted

Developer takeaway:
- Classification should drive storage, transmission, access, retention, and monitoring controls.

### Data Lineage and Reconciliation

You should be able to answer:
- Where did this number come from?
- Which transformations changed it?
- Why does this report match the ledger?

Developer takeaway:
- Reconciliation and lineage are first-class features, not optional analytics extras.

## Reliability and Operations in Banking

### Availability and Recovery

Banking services often require:
- Strong uptime targets
- Clear RTO (recovery time objective)
- Clear RPO (recovery point objective)
- Tested backup and restore procedures

### Incident Management

Expect mature incident processes:
- Rapid triage and customer impact assessment
- Regulatory or partner notification workflows when required
- Post-incident reviews with corrective actions

### Change Management

Higher-risk changes may require:
- Formal approvals
- Deployment windows
- Rollback plans
- Evidence capture for audit

## Engineering Practices That Matter Most

1. Idempotency for all money movement operations
2. Deterministic state transitions and explicit status models
3. Strong observability (logs, metrics, traces, business event telemetry)
4. Reconciliation jobs and exception handling workflows
5. Back-pressure and retry strategies with guardrails
6. Feature flags and controlled rollout patterns
7. Comprehensive testing, including failure-path and replay tests
8. Runbooks and operational readiness checklists

## Common Banking Architecture Patterns

- Event-driven processing for transaction lifecycles
- Saga/workflow orchestration for long-running business flows
- CQRS-style read models for operational reporting (where appropriate)
- API gateway and service mesh controls for policy enforcement
- Batch plus streaming hybrid architectures

Important note:
- Legacy systems are common. Success often means integrating safely, not replacing everything quickly.

## Useful Business Terms Developers Should Know

- Ledger: Authoritative financial record
- Settlement: Final transfer of funds between parties
- Reconciliation: Matching records across systems to find discrepancies
- Float: Time gap where funds are in transit or pending
- Chargeback: Card dispute reversal process
- Exposure: Amount at risk in a credit or operational context
- Delinquency: Past-due payment status on credit products
- Write-off: Accounting treatment for uncollectible debt

## Documentation Artifacts a Bank Developer Should Keep Current

- API and event contracts
- Data dictionary and classification map
- Architecture decision records (ADRs)
- Runbooks and incident playbooks
- Reconciliation design and exception procedures
- Access control model and role matrix
- Compliance control mapping for key systems

## First 90 Days: Practical Ramp-Up Plan

1. Learn your bank's core products and transaction lifecycles.
2. Understand at least one end-to-end money movement flow.
3. Identify systems of record and reconciliation ownership.
4. Review major compliance controls for your application area.
5. Study incident history and postmortems for your services.
6. Confirm RTO/RPO targets and current operational readiness.
7. Improve one control surface: logging, idempotency, or runbooks.

## Final Guidance

In banking, high-quality software is not only feature-rich. It is correct, auditable, secure, resilient, and understandable under scrutiny. Engineers who design for those properties become high-impact contributors quickly.
