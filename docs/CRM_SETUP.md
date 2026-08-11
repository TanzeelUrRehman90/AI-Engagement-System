# CRM Setup

## 1. Purpose

This document defines the sanitized CRM setup requirements for the AI Engagement System.

The CRM should provide a consistent structure for:

- Lead management
- Contact ownership
- Pipeline tracking
- AI conversation logging
- Follow-up management
- Human handoffs
- Reporting

---

## 2. Lead Data

The CRM should maintain the information required to identify and manage leads.

Recommended fields include:

- First name
- Last name
- Email
- Phone
- Lead source
- Lead status
- Lead owner
- Pipeline stage
- Conversation status
- Follow-up status
- Human handoff status
- Created date
- Last activity date

Do not store unnecessary sensitive information.

---

## 3. Lead Sources

Lead sources should be recorded consistently so that reporting can identify where leads originated.

Examples include:

- Website
- Web chat
- Email
- SMS
- Referral
- Import
- Other approved sources

---

## 4. Pipeline Stages

The CRM pipeline should support clear lead progression.

Example stages:

1. New
2. Contacted
3. Engaged
4. Human Follow-Up Required
5. Qualified
6. Closed
7. Not Interested

Pipeline stages should be adapted to the approved business process.

---

## 5. Lead Ownership

Each active lead should have an appropriate owner.

Ownership should be used to:

- Identify responsible staff
- Route human handoffs
- Manage follow-up queues
- Support reporting
- Prevent duplicate work

If ownership is unavailable, the system should follow the configured fallback process.

---

## 6. Tags

Tags can be used to identify important lead states and workflow conditions.

Example tags:

- `ai-active`
- `human-handoff`
- `credit-request`
- `appointment-request`
- `pricing-question`
- `follow-up-required`
- `opted-out`

Tags should be applied consistently and removed or updated when the lead state changes.

---

## 7. AI Conversation Status

The CRM should make it possible to distinguish between AI-managed and human-managed conversations.

Suggested statuses:

- AI Active
- Human Handoff Required
- Human Active
- Resolved
- Opted Out

When a human takes over a conversation, AI follow-up automation should be paused where required.

---

## 8. Duplicate Handling

Duplicate contacts should be detected and handled before creating unnecessary records.

The system should check available identifiers such as:

- Email
- Phone
- Existing contact identifiers

Duplicate handling should avoid overwriting valid existing information.

---

## 9. Lead Synchronization

New leads should be synchronized into the CRM with the required information.

Synchronization should account for:

- Successful creation
- Existing contacts
- Duplicate records
- Missing required fields
- Failed synchronization
- Retry handling

Failures should be logged so they can be investigated.

---

## 10. Human Handoff

Human handoff should be triggered for situations such as:

- Pricing questions
- New appointment requests
- Credit-related requests
- Requests to speak with a person
- Complaints
- Unsupported questions

A handoff should preserve relevant conversation context for staff.

---

## 11. Follow-Up Management

The CRM should track whether a lead is eligible for automated follow-up.

Follow-up should stop when:

- The contact opts out
- The contact replies or engages
- A human takes over
- A confirmed outcome is reached
- The contact is excluded from automation

---

## 12. Reporting Fields

CRM data should support reporting for:

- Lead volume
- Lead source
- Pipeline stage
- Active conversations
- Human handoffs
- Follow-up activity
- Engagement
- Response status

---

## 13. Error Handling

CRM automation should account for common failures, including:

- Missing lead data
- Duplicate contacts
- Synchronization failures
- Invalid field values
- Failed workflow actions

Errors should be logged and routed to the appropriate operational process.

---

## 14. Security

The repository must not contain:

- API keys
- Passwords
- Access tokens
- Private credentials
- Real customer records
- Production secrets

Use secure configuration and approved credential storage for production systems.

---

## 15. Validation Checklist

Before considering the CRM setup complete, verify:

- [ ] Required lead fields are available
- [ ] Lead ownership works
- [ ] Pipeline stages are configured
- [ ] Tags are consistent
- [ ] AI and human statuses are distinguishable
- [ ] Duplicate handling is defined
- [ ] Lead synchronization is tested
- [ ] Handoff workflows are tested
- [ ] Follow-up stop conditions are tested
- [ ] Reporting fields are available
- [ ] Error handling is documented
- [ ] No production secrets are stored in the repository
