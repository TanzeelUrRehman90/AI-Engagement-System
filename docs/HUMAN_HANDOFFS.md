# Human Handoffs

## 1. Purpose

Human handoffs ensure that conversations outside the AI's approved scope are routed to the appropriate staff member.

The AI should recognize the handoff condition, preserve conversation context, notify staff, and pause relevant automation.

---

## 2. Handoff Triggers

The following situations require human handoff:

- Pricing questions
- New appointment requests
- Credit-related requests
- Requests to speak with a person
- Complaints
- Unsupported questions

---

## 3. Pricing Questions

When a customer asks about pricing:

1. Acknowledge the request.
2. Do not provide a price quote.
3. Notify or route the conversation to staff.
4. Pause relevant automated follow-up.
5. Mark the conversation as a pricing handoff.

Suggested status/tag:

```text
handoff-pricing
