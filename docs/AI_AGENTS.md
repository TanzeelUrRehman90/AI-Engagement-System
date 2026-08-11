# AI Agents

## 1. Purpose

The AI Agents component supports customer engagement while keeping all interactions within approved business rules.

AI agents may assist with:

- Email conversations
- SMS conversations
- Website chat
- Lead follow-up
- Information requests
- Approved workflow actions
- Human handoff

---

## 2. Agent Responsibilities

The AI should:

- Respond using approved business information
- Maintain a professional and helpful tone
- Identify when a request requires human assistance
- Follow configured workflow rules
- Respect opt-out requests
- Preserve relevant conversation context
- Stop automation when a human takes over

---

## 3. Supported Channels

AI engagement may operate through:

### Email

The agent can:

- Respond to inbound emails
- Provide approved information
- Continue eligible conversations
- Trigger appropriate follow-up workflows
- Route unsupported requests to staff

### SMS

The agent can:

- Respond to inbound SMS
- Provide approved information
- Continue eligible conversations
- Trigger approved follow-ups
- Respect STOP / opt-out requests

### Web Chat

The agent can:

- Respond to website visitors
- Capture contact information
- Answer approved questions
- Create or update CRM information where configured
- Escalate conversations to human staff

---

## 4. AI Boundaries

The AI must not independently:

- Provide pricing quotes
- Negotiate pricing
- Approve credit
- Make lending decisions
- Schedule a new appointment
- Override human decisions
- Provide unsupported business information

These situations must be routed to the appropriate human workflow.

---

## 5. Human Handoff

The AI should initiate a human handoff when the conversation involves:

- Pricing questions
- New appointment requests
- Credit-related requests
- A request to speak with a person
- Complaints
- Unsupported questions
- Any situation outside the approved AI scope

The handoff should include relevant conversation context so staff can continue without unnecessary repetition.

---

## 6. AI to Human Transition

When a human handoff is triggered:

1. Identify the handoff reason.
2. Preserve the relevant conversation history.
3. Update the CRM conversation status.
4. Notify or queue the appropriate staff.
5. Pause automated follow-up where required.
6. Allow the human to take control of the conversation.

AI automation should not continue sending messages when the workflow requires human control.

---

## 7. Follow-Up Rules

Follow-up automation may use email and SMS.

A maximum of three touches per day should be observed.

Follow-up should stop when:

- The contact opts out
- The contact replies or engages
- A human takes over
- A confirmed outcome is reached
- The contact is on an exclusion list

---

## 8. Credit Requests

For credit-related conversations, the AI may:

- Provide the approved credit application link
- Explain the next approved step
- Notify or route the request to staff

The AI must not:

- Approve credit
- Reject credit
- Make lending decisions
- Negotiate credit terms

---

## 9. Appointment Requests

For existing appointments, the AI may provide approved confirmation information.

For new appointment requests, the AI must:

1. Identify the request.
2. Collect only the information permitted by the workflow.
3. Route the request to human staff.
4. Avoid selecting or confirming a new appointment time.

---

## 10. Opt-Out Handling

The AI must respect opt-out requests.

Examples include:

- STOP
- Unsubscribe
- Do not contact me
- Similar clear requests to stop communication

After an opt-out request, automated follow-up must stop according to the configured workflow.

---

## 11. Response Guidelines

AI responses should be:

- Clear
- Concise
- Professional
- Relevant to the user's request
- Based on approved information

The AI should not invent:

- Prices
- Policies
- Appointment availability
- Credit decisions
- Business facts
- Unsupported answers

When information is unavailable or outside scope, the AI should use the appropriate human handoff process.

---

## 12. Conversation States

Suggested conversation states include:

- AI Active
- Follow-Up Active
- Human Handoff Required
- Human Active
- Resolved
- Opted Out

State changes should be reflected in the CRM where configured.

---

## 13. Error Handling

The system should account for:

- Failed message delivery
- Missing contact information
- CRM synchronization failures
- Duplicate contacts
- Unsupported requests
- Workflow failures

Errors should be logged and routed to the appropriate operational process.

---

## 14. Testing Requirements

AI agents should be tested for:

- Email responses
- SMS responses
- Web chat
- Human handoffs
- Pricing questions
- Credit requests
- Appointment requests
- Complaint escalation
- STOP / opt-out behavior
- Follow-up stop conditions
- Human takeover
- Unsupported questions
- Error handling

---

## 15. Security

Do not store the following in this repository:

- API keys
- Passwords
- Access tokens
- Private credentials
- Production secrets
- Real customer information

Production credentials must be managed through approved secure systems.

---

## 16. Agent Validation Checklist

Before deployment, verify:

- [ ] AI responses follow approved rules
- [ ] Email workflow is tested
- [ ] SMS workflow is tested
- [ ] Web chat is tested
- [ ] Human handoff works
- [ ] Pricing requests are escalated
- [ ] Credit requests follow approved boundaries
- [ ] New appointment requests are escalated
- [ ] STOP / opt-out behavior works
- [ ] Follow-up stops correctly
- [ ] Human takeover pauses automation
- [ ] Unsupported questions are handled safely
- [ ] No production secrets are stored in the repository
