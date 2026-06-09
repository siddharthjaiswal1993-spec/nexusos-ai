# Prototype Screens

## Overview

The NexusOS AI prototype is available at:
[https://nexus-strategic-center.lovable.app](https://nexus-strategic-center.lovable.app)

This document describes the key screens included in the prototype and the design intent behind each.

---

## 1. Executive Command Center

**Purpose:** Give leadership a single, prioritized view of business health across all functions.

**What it displays:**
- Business health scorecard with status indicators across Revenue, Customer Success, Product, Support, and Engineering
- Summary of active revenue risks, sorted by impact
- Summary of active churn risks, sorted by ARR at risk
- Operational bottleneck alerts from engineering and customer success
- Product gap alerts based on recurring customer signals
- AI-recommended top actions for the current week
- Trend indicators showing directional change from the prior period

**Design intent:**
This screen is designed for the CEO, COO, CRO, and CPO. It should deliver immediate situational awareness without requiring drill-down. The executive should be able to open this screen and know within 60 seconds where to focus attention.

---

## 2. Agent Hub

**Purpose:** Provide visibility into all active AI agents and their current workflow states.

**What it displays:**
- Grid view of all specialized agents (Sales, CS, Product, Support, Marketing, Finance, HR, Engineering, Governance, Executive)
- Status indicator per agent: active, idle, pending approval, or attention required
- Recent workflow activity per agent
- Shortcut to launch a new workflow for any agent

**Design intent:**
This screen is designed for power users and platform administrators. It provides oversight across the full agent layer and serves as a starting point for drilling into any specific agent's recent activity.

---

## 3. Revenue Intelligence Screen

**Purpose:** Give sales and revenue operations leadership a real-time view of pipeline health and deal risk.

**What it displays:**
- Pipeline summary by stage with movement indicators
- List of at-risk deals with risk score, risk driver explanation, and recommended recovery action
- Forecast gap analysis: plan vs. current projection
- Next-best actions ranked by expected revenue impact
- Account-level deal insights for priority opportunities

**Design intent:**
This screen is designed for the VP Sales, CRO, and RevOps. It replaces the manual pipeline review by surfacing what matters before the weekly meeting.

---

## 4. Customer Success Intelligence Screen

**Purpose:** Help CS teams prioritize their accounts based on real-time health signals and renewal timelines.

**What it displays:**
- Account health distribution across the portfolio
- Churn risk list sorted by ARR at risk, with risk driver summaries
- Renewal readiness view: accounts by renewal date with health status
- Expansion opportunity list with confidence score and recommended next step
- QBR preparation summaries for upcoming accounts

**Design intent:**
This screen is designed for the VP CS and CS managers. It surfaces the accounts that need attention first and provides CSMs with the context they need to act confidently.

---

## 5. Product Intelligence Screen

**Purpose:** Give product leaders a synthesized view of customer feedback, roadmap gaps, and strategic themes.

**What it displays:**
- Feedback cluster view: top themes by frequency, severity, and customer segment
- PRD draft previews generated from feedback clusters
- Feature demand heatmap by product area and customer tier
- Roadmap risk alerts: areas where feedback volume is rising but roadmap coverage is low
- Product opportunity areas with supporting evidence

**Design intent:**
This screen is designed for the CPO and product managers. It converts scattered feedback into structured roadmap input, reducing the time from signal to planning artifact.

---

## 6. Support Intelligence Screen

**Purpose:** Improve ticket prioritization, routing accuracy, and product quality signal flow.

**What it displays:**
- Ticket volume trends by category and severity
- Emerging issue alerts: clusters that have grown significantly in the past 7 days
- Escalation risk list: tickets showing high-risk signals (sentiment, customer tier, issue type)
- Recurring issue patterns linked to product areas or recent releases
- Product quality signals ready to route to the product and engineering teams

**Design intent:**
This screen is designed for VP Support and support operations leaders. It reduces manual triage burden and ensures that product quality signals do not stay trapped in the support queue.

---

## 7. Workflow Approval Queue

**Purpose:** Provide a centralized interface for reviewing and approving AI-recommended actions before execution.

**What it displays:**
- Queue of pending approval requests organized by urgency and action type
- Per-request view: recommended action, reasoning summary, supporting signals, source citations, and confidence score
- Approve / Reject / Edit controls for each request
- History of recently approved, rejected, and edited actions

**Design intent:**
This screen is the primary governance interface for NexusOS AI. It ensures that humans remain in control of consequential decisions while giving them the full context they need to review quickly and confidently.

---

## 8. Memory and Signal Timeline

**Purpose:** Show users how the system reached a recommendation using historical signals over time.

**What it displays:**
- Chronological timeline of signals that contributed to the current recommendation or account state
- Source labels: which system each signal came from
- Contribution weight: which signals had the greatest influence on the recommendation
- Memory state summary: what the system currently knows about this account, deal, or workflow

**Design intent:**
This screen is the explainability interface for NexusOS AI. It allows users to audit the reasoning behind any recommendation and builds trust by making the system's logic transparent and traceable.

---

## 9. Executive Brief Generator

**Purpose:** Generate leadership-ready summaries of business performance, risk, and recommended priorities.

**What it displays:**
- Brief type selector: weekly summary, board update, QBR summary, strategic decision brief
- Generated brief preview with structured sections and supporting data
- Edit controls to adjust framing, emphasis, or detail level
- Approval and distribution controls

**Design intent:**
This screen reduces the time executives and chiefs of staff spend assembling leadership briefings. The system drafts from real operational context; the human refines and approves.

---

## 10. Governance and Audit Screen

**Purpose:** Provide administrators and compliance teams with full visibility into AI activity and decision history.

**What it displays:**
- Approval log: all approvals, rejections, and edits with timestamps and approver identity
- Confidence score distribution across recent recommendations
- Source citation audit: verify that recommendations are grounded in cited context
- Permission check log: which users took which actions on which workflows
- Action history: every system-executed action with its approval chain

**Design intent:**
This screen is designed for compliance, legal, and security reviewers during procurement, audit cycles, or incident review. It demonstrates that NexusOS AI operates with full accountability.

---

## Related Documents

- [Product Vision](product-vision.md)
- [Agentic Workflows](agentic-workflows.md)
- [Human-in-the-Loop Design](human-in-the-loop.md)
- [Demo Script](demo-script.md)
