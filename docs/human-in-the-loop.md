# Human-in-the-Loop Design

## Overview

NexusOS AI is designed to augment human judgment, not replace it.

For routine, low-stakes, and reversible tasks, agents can act with minimal oversight. But enterprise operations regularly involve decisions that are customer-facing, financially significant, legally sensitive, or irreversible. In these cases, the platform requires a human to review, edit, and approve before any action is executed.

This is not a limitation of the platform. It is a deliberate design choice that builds trust, maintains accountability, and ensures the system can operate safely at scale within enterprise environments.

---

## Core Design Principle

**Agents recommend. Humans decide. The system executes.**

This sequence ensures that AI capabilities are applied at scale without removing human accountability from outcomes that matter.

---

## When Human Approval Is Required

The following categories of actions require explicit human approval before execution:

### Customer-Facing Communications
- Sending emails to customers
- Drafting and sending Slack messages to customer stakeholders
- Sharing executive summaries or briefings with external parties
- Responding to customer escalations on behalf of the organization

### Account and Relationship Status Changes
- Updating CRM health status for a customer account
- Changing renewal risk classification
- Marking an account as at-risk or a priority in the leadership view
- Escalating an account to executive leadership attention

### Financial and Forecast Actions
- Changing a deal's forecast category
- Submitting a revised revenue forecast
- Flagging a deal as lost or at-risk in an official report
- Adjusting financial planning inputs

### Engineering and Product Actions
- Creating high-priority engineering tickets linked to customer issues
- Tagging a support pattern as a product defect requiring immediate attention
- Recommending a roadmap reprioritization based on customer signals

### Governance and Compliance Actions
- Updating compliance status for an account or workflow
- Responding to RFP or security questionnaire items involving policy or legal content
- Triggering HR-related workflows such as performance flagging or policy enforcement actions

---

## Approval Model

The approval flow follows a consistent six-step model:

```
1. Agent completes reasoning and generates recommendation
         |
         v
2. System surfaces recommendation with explanation, evidence, and confidence score
         |
         v
3. User reviews recommendation in the approval queue
         |
         v
4. User selects: Approve / Reject / Edit and Approve
         |
         v
5. System executes approved action and logs the decision
         |
         v
6. Outcome is tracked and memory is updated
```

---

## Approval Interface Design

Each approval request surfaces:

- **Recommended action:** A plain-language description of what the system proposes to do
- **Reasoning summary:** A concise explanation of why the action is recommended
- **Supporting signals:** The specific signals from memory that informed the recommendation
- **Source citations:** Links or references to the original source data
- **Confidence score:** A calibrated indicator of the system's certainty
- **Edit option:** The user can modify the recommendation before approving
- **Rejection notes:** When a user rejects a recommendation, they can record why, which feeds back into agent learning

---

## Approval Roles and Permissions

Not every user can approve every type of action. Role-based permissions determine who can approve what:

| Action Category | Required Role |
|---|---|
| Customer email | CSM, Account Executive, or VP CS |
| Account health update | CSM or CS Manager |
| Revenue forecast change | RevOps or Finance |
| Engineering ticket creation | PM or Engineering Manager |
| Executive briefing share | VP or C-level |
| RFP policy response | Sales Ops or Legal |
| HR workflow action | HR Business Partner or Head of People |
| Compliance status update | Compliance or Legal |

Permission policies are configurable by workspace administrators.

---

## Confidence Thresholds and Auto-Execution

For low-stakes, reversible, and well-defined actions, the system can be configured to auto-execute above a defined confidence threshold. Examples include:

- Logging a follow-up task in the CRM after a call
- Tagging a support ticket with a product area
- Sending an internal Slack notification (not a customer communication)

High-stakes or customer-facing actions always require human approval regardless of confidence level.

Confidence thresholds are configurable per action type and can be adjusted by administrators as the system demonstrates accuracy over time.

---

## Feedback Loop

When a user rejects or edits a recommendation, the platform captures the correction:

- The original recommendation and the edited or rejected outcome are both stored in workflow memory
- Rejection reasons are categorized to identify patterns in where agents are underperforming
- This feedback is used to improve recommendation quality over time

This creates a continuous feedback loop where human judgment improves agent performance without requiring formal model retraining.

---

## Why This Design Matters for Enterprise Adoption

Enterprise organizations cannot adopt AI platforms that operate as black boxes. Procurement, legal, compliance, and security teams require visibility into what the system does and the ability to maintain oversight.

The human-in-the-loop model provides:

- **Accountability:** Every consequential action has a named human approver
- **Auditability:** Every recommendation, approval, and outcome is logged
- **Trust:** Users develop confidence in the system by seeing its reasoning before approving
- **Control:** Organizations can set policy boundaries on what agents can propose and what requires review
- **Improvement:** Human feedback continuously improves recommendation quality

---

## Related Documents

- [AI Governance](ai-governance.md)
- [Requirements](requirements.md)
- [Platform Architecture](platform-architecture.md)
- [Agentic Workflows](agentic-workflows.md)
