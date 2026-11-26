<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# Version history

**1.0 (release candidate, November 2026).** First version in canonical English and under the CC BY-SA 4.0 licence. The method is split into this Guide, which changes only by RFC, and an Extended Framework governed by the community. The Guide includes community-maintained sections on the Digital Seniority catalogue, test practices and adoption levels, and states no numeric values: the mandate sets them and the Extended Framework gives indicative values. Normative rules use the RFC 2119 key words. Version 1.0 supersedes the Italian specification 0.3, which remains the historical source and is kept, non-normative, in `history/`; a curated Italian translation will follow.

**0.3 (November 2026).** Restored elements of the founding drafts that 0.2 had condensed: the operating model and framework map, AI Squads and agentic Scrum, Design Thinking delegated to AI, the detail of proof of concept, design and planning, DevSecOps and tests, the composable architecture, the governance artifacts and the full content of Role Profiles. Added the High Level Architectural View, the Work Package tree with cost estimates, the rule that the shape of control artifacts is a project decision, and Digital Seniority (levels SD1–SD5, a task catalogue in every Role Profile, a default level for tasks outside the catalogue).

Changes from 0.2 to 0.3 that the paragraph above does not list (added by RFC 0003):

| Change | Section of 0.3 | Origin |
|---|---|---|
| "Product Owner" becomes "Human Manager" and "coordinator" becomes "AI Coordinator" | Whole text | Decision of the Human Manager, 25 November 2026 |
| "Why Eiraman exists", with the definitions of human-in-the-loop and human-on-the-loop | §1 | Founding drafts; definitions requested on 25 November 2026 |
| Founding principle, management applied to AI, and the table of management practices | §1 | Decision of the Human Manager, 25 November 2026 |
| First context principle rewritten: from "no specialist in the projects" to "specialist competence lives in Role Profiles" | §1, §10 | Decision of the Human Manager, 25 November 2026 |
| The Human Manager holds the Product Owner and Business Architect roles | §2 | Independent review of 0.3 |
| Rationale of competitive mechanisms | §4 | Founding drafts |
| Explicit independence rule for the tester on security and personal data | §4 bis | Independent review of 0.3 |
| Success criteria of a version and of the project based on KPIs measurable in the test procedures | §5 | Independent review of 0.3 |
| Decisions cannot violate a Principle; Decisions are linked, and changing one can require re-examining the linked ones | §5 | Independent review of 0.3 |
| Test table in place of the line on tests; the sentence "security and performance are consistent with the risk" was **removed** without a changelog entry and is restored in Guide 1.0.0-rc.3 | §6 | Founding drafts; undeclared removal |
| Brain tasks catalogued as trusted or untrusted, with a control on untrusted ones | §6 bis, §7 | Founding drafts; independent review of 0.3 |
| Content of the Security Risk Posture | §7 | Founding drafts; independent review of 0.3 |
| Outcomes of the independent review of 0.3, applied before approval: the equivalence of the coordinator's names, the Business Architect role, KPIs, Principles that cannot be violated and linked Decisions, the Risk Log and the content of the Security Risk Posture, the explicit rule for the tester, the reference for trusted and untrusted tasks | Various | Independent review of 0.3 |
| Five integrations by the AI Coordinator that completed truncated sentences of the founding drafts | Various | Confirmed by the Human Manager on 25 November 2026; not listed one by one |

**0.2.** Revised accountabilities, applicability levels, the governance cycle, escalation, competitive mechanisms, documentation, Role Profiles and conformance. Introduced: stop criteria in the mandate; executable acceptance criteria and a definition of ready; Deny on non-corrective releases when the error budget is exhausted; agent security rules (Agents section, hostile-input test, profile and model hashes, SBOM); data classes per provider; minimum levels of verification independence; the local and external boundary of the Development Environment; calibration of the process reviewer in the first project of every new adoption.

**0.1.** First version of the method.
