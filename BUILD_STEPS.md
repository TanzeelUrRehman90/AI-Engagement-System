# AI Engagement System
## Step-by-Step Build Guide (GoHighLevel)

Email + SMS + Web Chat AI · Follow-up · Handoffs · Credit/Appointment actions · Reporting.
NO voice AI. AI confirms existing appointments only (does NOT schedule new). AI never
quotes pricing, negotiates, or makes credit decisions — those go to human handoff.

---

## PHASE 0 — Before You Build (Prerequisites)

### 🔴 PRIORITY-0 — DO THESE FIRST (before any other work)
- [ ] **Remove all test/sample personal data** from EVERYWHERE in the sub-account —
      business profile, workflows, test contacts/records, and imported sample data.
- [ ] Sweep for any leftover default/sample data from the template and replace it
      with the correct client-provided details only after approval.

### 🚦 PROJECT GOVERNANCE RULE (non-negotiable)
> **Nothing goes OUT to the client without the designated project approver's approval first.**
> Build everything in **draft / internal / PAUSED** state. No live email, SMS, or automation
> may reach real customer or dealership contacts until explicit sign-off.
> Test only against approved internal test contacts.

### Correct business profile (use client-approved values)
- **Name:** Client-provided business name
- **Primary contact:** Client-provided contact
- **Contact emails:** Client-provided emails
- **Phone:** Client-provided business phone
- **Address:** Client-provided business address
- **Website:** Client-provided website
- **Timezone:** Client-provided timezone
- **GHL access:** Use approved account access only

### Prerequisites checklist
- [ ] **Sub-account profile** cleaned + set to the correct details above (test email removed).
- [ ] **Get the dealership inputs** (send the client the intake/access list — see INTAKE_LIST.md):
      CRM access, lead export, business hours, FAQs, escalation contacts, brand voice,
      approved links (credit app), privacy/terms pages, legal business details.
- [ ] **Buy a phone number** in the sub-account (local area code — the client's local area code).
- [ ] **Start A2P 10DLC** registration (legal business details + opt-in language + sample msgs).
      SMS will be filtered until approved — build everything else in the meantime.

---

## PHASE 1 — Foundation: CRM Structure (Milestone 1, Days 1–2)

1. **Custom Fields** — create the fields you'll capture/use:
   - Lead source, Vehicle of interest, Trade-in (Y/N), Preferred contact method,
     Consent/opt-in status, Appointment date (existing), Credit-app sent (Y/N).
2. **Tags** — create a consistent tag set:
   - `new-lead`, `engaged`, `nurturing`, `handoff-pricing`, `handoff-appointment`,
     `handoff-credit`, `handoff-complaint`, `human-takeover`, `opted-out`, `revived`.
3. **Pipeline** — build one clear pipeline (Opportunities → Pipelines):
   - Stages: **New Lead → Contacted → Engaged → Handoff to Staff → Appointment/Visit →
     Won / Lost**.
4. **User permissions** — add the dealership staff who need access; set roles.
5. **Integration map** — list every lead source and how it will enter GHL (see Phase 2.1).

✅ Output: CRM foundation approved by the client before moving on.

---

## PHASE 2 — Data & AI Agents (Milestone 2, Days 3–4)

**2.1 — Lead import + new-lead sync**
1. **Import existing leads** (Contacts → Import) from the dealership CRM export. Map every
   field; set tags (`revived` candidates), consent status, and owner.
2. **Connect new inbound leads** so they flow into GHL automatically:
   - Website forms → GHL form/webhook
   - Email leads → Inbound email parsing / lead-connector
   - Third-party lead sources (third-party lead sources, marketplaces) → their integration or email parse
3. Add **duplicate handling** and **error handling** on the sync.

**2.2 — AI Email/SMS agent (Conversation AI)**
1. Go to **Settings → Conversation AI** (or the AI Agent) and create the agent.
2. Write the **conversation prompt / response rules** using: business hours, FAQs, brand
   voice, approved links. Define exactly what it CAN answer and what it must HAND OFF.
3. Build the **instant inbound response** workflow:
   - Trigger: new inbound message / new lead → AI replies within seconds (email + SMS).
4. Add **stop/opt-out rules**: STOP/unsubscribe → tag `opted-out`, stop all messaging.

✅ Output: Lead sync + AI email/SMS agents working in staging.

---

## PHASE 3 — Handoffs & Web Chat (Milestone 3, Days 5–6)

**3.1 — Human handoff triggers** (build as workflow conditions on the AI conversation)
| Trigger | System behavior |
|---|---|
| Pricing question | Acknowledge (don't quote) → notify staff → pause automation → tag `handoff-pricing` |
| Appointment request | Capture → route to staff (confirm existing only) → tag `handoff-appointment` |
| Credit application | Send approved credit link → alert staff → tag `handoff-credit` |
| "Speak to a person" | Immediate handoff with contact + conversation context |
| Complaint / unsupported | Don't guess → mark priority → escalate → tag `handoff-complaint` |

For each: **create a task**, **assign ownership**, **notify staff** (internal notification /
email / Slack), and **pause the AI automation** for that contact.

**3.2 — Web Chat AI**
1. Create the **chat widget** (Sites → Chat Widget) using the SAME prompt/rules as email/SMS.
2. Set **contact capture** (name, phone/email) before/within the chat.
3. Log every chat into the **CRM conversation** for that contact.
4. Wire the same **staff escalation** as above.
5. Install the widget on the dealership **website** (embed code).

✅ Output: End-to-end customer journey functional (email, SMS, chat, handoffs).

---

## PHASE 4 — Follow-Up & Reporting (Milestone 4, Days 7–8)

**4.1 — Nurture / follow-up sequences**
1. Build **follow-up workflows** — up to **3 touches per day** max, across email + SMS.
2. Add **STOP conditions** (critical): stop when the contact **opts out**, **replies/engages**,
   **is handed to a human**, reaches a **confirmed outcome**, or is on an **exclusion list**.
3. Build a **database reactivation** campaign for the imported old prospects (`revived`).

**4.2 — Dashboards & reporting**
Build operational dashboards / views showing:
- **Active conversations** (engaged with AI)
- **Pending human action** (handoff queue)
- **Handoffs by type**
- **Engagement / response metrics**
- Staff follow-up **queues**

✅ Output: Automation + reporting complete.

---

## PHASE 5 — Credit & Appointment Actions

1. **Credit-link workflow** — when a lead asks about financing/credit → send the
   dealership's **approved credit application link** + alert staff. AI never approves credit.
2. **Existing-appointment confirmation workflow** — AI can **confirm an existing** appointment
   only. It does **NOT** schedule new times (route new-appointment requests to staff).

---

## PHASE 6 — Internal QA (Days 9–10)

Test and fix defects across:
- [ ] Email responses
- [ ] SMS responses (once A2P allows) 
- [ ] Web chat
- [ ] Every handoff trigger (pricing, appointment, credit, person, complaint)
- [ ] Opt-out / STOP behavior
- [ ] Staff takeover (automation pauses correctly)
- [ ] Duplicate contacts
- [ ] Failed / retried syncs

✅ Output: Critical issues resolved.

---

## PHASE 7 — Client Testing (Day 11)

- [ ] Run **client UAT** with the dealership's decision-maker.
- [ ] Collect **ONE consolidated feedback round** (protect the timeline).
- [ ] Apply approved changes.

✅ Output: UAT approval.

---

## PHASE 8 — Training & Go-Live (Days 12–13)

**Day 12 — Training & prep**
- [ ] Train the dealership team (how handoffs appear, how to take over, the queues).
- [ ] Deliver the **quick guide**.
- [ ] Validate production settings + final checklist.

**Day 13 — Go-Live & Handover**
- [ ] Activate approved workflows.
- [ ] Monitor initial activity.
- [ ] Hand over the completed system.

---

## GO-LIVE ACCEPTANCE CHECKLIST (the build is "done" when all true)
- [ ] Existing + new leads enter GHL with required data and ownership.
- [ ] Email, SMS, and web chat respond using approved prompts and boundaries.
- [ ] Follow-ups STOP after opt-out, confirmed outcome, human takeover, or exclusion.
- [ ] Handoff notifications + staff follow-up queues are visible and tested.
- [ ] Dashboards show active conversations, pending action, handoffs, engagement.
- [ ] Critical defects resolved; training + quick guide delivered.

---

## HARD BOUNDARIES (bake these into every AI prompt)
- ❌ Never quote pricing, negotiate, approve credit, or make lending decisions.
- ❌ Never schedule a NEW appointment time (confirm existing only).
- ✅ Always hand off pricing, new-appointment, credit, complaints, and "speak to a person."
- ✅ Always respect opt-out / STOP immediately.

## PROJECT BOUNDARIES (operational — not AI-prompt)
- 🚫 **No outbound to the client without the designated project approver's sign-off.** Everything stays draft/paused
     until approved (the designated client contact, the designated client contact, or any real dealership contact). Test on internal contacts only.
- 🚫 **Never reuse another dealership's data.** The `[REMOVED TEST EMAIL]` incident must
     not repeat — no real third-party emails/numbers anywhere in the build.

## NOT included (out of scope — needs separate approval)
Voice AI, new-appointment scheduling, pricing/credit decisions, website redesign, ongoing
campaign management, third-party fees (GHL, SMS, A2P, email, middleware).
```
