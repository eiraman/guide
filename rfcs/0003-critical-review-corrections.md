<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# RFC 0003: Corrections from the critical review of specification 0.3

- **Author(s):** the Steward, also on behalf of the working groups not yet formed
- **Accountable human:** Paolo Ungari (Steward)
- **AI-Use:** substantial (CONTRIBUTING.md §3)
- **Assisted-by:** Claude Fable 5.2
- **Assisted-by:** Claude Opus 5.5 (independent review)
- **Conflicts of interest:** none
- **Owner of the decision:** Author (Guide)
- **Affected artifacts:** Guide §1, §2, §5, §6, §7, §7.1, §8, §8.1, §9, §9.1, §10, §11, §14, §14.1; `HISTORY.md`, `TRACEABILITY.md`. After acceptance, in separate releases: Role Profiles (AI Coordinator, functional tester, Design Thinking Facilitator, application and data architecture reviewer, Digital Seniority map), Extended Framework (Guidance values), Tools (Manager View, role label in run records)
- **State:** accepted
- **Dates:** opened 2026-11-26 · comment period ends 2026-12-10 · accepted 2026-11-26, before the end of the comment period (deviation, see Decision)
- **Change request:** CR-009 of the project "Eiraman Open Framework"; decided by Do-S19

## Summary

An independent critical review of the Italian specification 0.3 raised sixteen findings. Checked against Guide 1.0.0-rc.2, three were already closed, five were reduced, seven were still present word for word and one had grown. The Human Manager decided on each of them on 26 November 2026 (decisions D0 to D10 of the scope register) and approved a set of editorial corrections. By decision D0 the corrections go into the Guide only; specification 0.3 stays the historical source.

This RFC proposes the resulting changes to the Guide. Two rules are replaced: a test agent no longer fixes anything on its own, and the Backbone is no longer built before every other component. The other changes add or clarify: under-escalation is reported as an estimate with its uncertainty; Discovery convergence follows K1, with a judge of its own; tasks outside the catalogue are promoted at the first failure; the mandate sets the criteria for trusted and untrusted tasks; the documents due at each adoption level are listed; the governance share of cost is recorded and reported in the cycle review. The change affects every project that applies the Guide, its AI Coordinator and the Role Profiles listed under Impact.

The RFC touches three community-maintained sections: the Digital Seniority catalogue (§7.1), the test practices (§9.1) and applicability (§14, §14.1). Their working groups do not exist yet, so the Steward proposes that text here; the Author accepts it by RFC as for any community-maintained section (Guide §0, §15).

## Motivation

The findings are in the review of 26 November 2026 and in the answer prepared for the Human Manager; both are internal documents of the project. The evidence below is in the text of Guide 1.0.0-rc.2 itself.

- **A verifier that modifies what it verifies.** §9.1 says "Gross errors that touch neither quality nor Decisions are fixed by the agent on its own", while §9 says "A change to the candidate MUST reopen the affected checks" and §3 requires testers to be independent of executors. The text does not say what the agent may fix.
- **Two orders of construction.** §10 says the Backbone "MUST be built before all other components", and also that "The first usable path runs through Backbone and Brain and includes the essential interfaces". Both cannot hold.
- **A measure without a denominator.** E6 divides the reserved decisions not escalated by "all reserved decisions", which include the ones nobody recorded. §14.1 uses that measure as evidence for moving up to level 1. The text does not say that it is an estimate, nor on how many decisions.
- **Convergence outside K1.** §8 runs all phases under the rules of competition, but Discovery convergence has no criteria fixed in advance and no judge on a different model. The AI Coordinator profile applies K1 "where possible".
- **A rule that cannot be applied.** §10 requires Brain tasks to be "catalogued as trusted or untrusted" and §11 attaches a control to the result. Neither says by which criteria nor who decides.
- **Indeterminate load at level 0.** §12 lists the managerial documents, §14.1 lists four for level 0, and §9 requires the High Level Architectural View to be kept up to date. It is not stated which documents are due at which level.
- **The cost of governance is not measured.** No rule records which runs are governance and which are production, so nobody can tell whether governance costs more than it returns.
- **Levels with no admission criterion.** §7.1 requires a single map from SD levels to configurations. It does not say on what basis a configuration is admitted to a level.
- **Terms and metrics left open.** "Beats a single executor" (K6), "unchanged quality" (§7.1) and the drift budget (E5) have no unit, sample or definition; "business owner" and "Manager View" are used without a definition; a sentence of specification 0.2 on security and performance testing was lost on the way to 0.3 and to the Guide, with no changelog entry.

Decisions applied, as recorded in the scope register: **D0** (corrections go into the Guide only), **D1** (estimates with their uncertainty), **D2** (Discovery convergence follows K1; the judge is distinct from the Discovery reviewers), **D3** (the test agent fixes nothing on its own; fixing the test script is a task of its own), **D4** (tasks outside the catalogue: lower Guidance value, promotion at the first failure, exception for tasks that by nature belong to a higher level, share reported), **D5** (the map is the maintainers' assessment, declared as such), **D6** (the mandate sets the criteria for trusted and untrusted tasks), **D7** (documents per level), **D9** (the founding sentence stays and two practices are added), **D10** (first a minimal path, then the whole Backbone). D2 amends the Discovery convergence introduced by RFC 0001 (CR-003, Do-S09). **D8** keeps one AI Scrum Master per team and does not change the Guide; the missing Role Profile is written under CR-008. Later decisions of the Human Manager, on 2026-11-26: the governance share (B12) enters the Guide; B1 to B11 stay out; the Discovery judge works under hard blinding and a missing different model goes to a Do; the AI Coordinator sets the gates of Discovery.

Editorial points that stay: PA-2 (no numbers: every value goes to the mandate or to the Extended Framework), PA-3 (vendor neutrality), PA-6 B (different model as a recommendation), PA-7, PA-8, PA-12 (RFC 2119 capitals).

## Proposal

The proposed text is below, item by item. The accepted items are applied in `EIRAMAN-GUIDE.md` at version 1.0.0-rc.3.

| Section | Change | Kind | Source |
|---|---|---|---|
| §2 Eiraman theory | Two transpositions added to the list | Modified line; new lines | D9 |
| §5 3D escalation | New item in the Do list; E5 gains a unit; E6 Measurement is reported as an estimate | New line; modified lines | R13, R15, D1 |
| §6 Competition | K6 names the values the mandate sets | Modified line | R14 |
| §7 AI Squads | Retrospective states its limits; Hard blinding covers the Discovery judge | Modified lines | R9, D2 (judge: decision of 2026-11-26) |
| §7.1 Digital Seniority catalogue | Catalogue, Fallback, Team participation, Promotion and reduction | Modified lines | D5, D4, R5, R14 |
| §8.1 Phase playbooks | Discovery procedure gains the step Judge | New line | D2 (decision of 2026-11-26) |
| §8 Lifecycle | Gates; Convergence follows K1; Governance cycle reports the governance share and the share of tasks outside the catalogue | Modified lines | R4, D2, D4; B12 (decided by the Human Manager on 2026-11-26) |
| §9 Commitments and artifacts | New paragraphs Risk Log and Manager View; cross-reference in High Level Architectural View | New paragraphs; modified line | D7, R18, R13 |
| §9.1 Test practices | Test levels; scripted functional tests | Modified line; replaced rule | R2, D3 |
| §10 Composable architecture | Backbone; Brain; Component contract | Replaced rule; modified lines | D10, D6 |
| §11 Environment | Run traceability records the role | Modified line | R1 |
| §1, §14 | "business owner" becomes "Human Manager" | Modified lines | R18 |
| §14.1 Requirements per level | Documents due at level 0 and level 1; operational layer | Modified lines; new paragraph | D7 |
| `HISTORY.md` | Table of changes from 0.2 to 0.3 | New table | R16 |

No section number changes. No paragraph label is removed.

### Rules replaced

**1. §9.1, Test types, scripted functional tests** (D3). Community-maintained section.

> Old: *Scripted functional tests:* an agent runs the test script, records the logs and checks completion or failure. Gross errors that touch neither quality nor Decisions are fixed by the agent on its own, as a two-way door.
>
> New: *Scripted functional tests:* an agent runs the test script, records the logs and checks completion or failure. The test agent MUST NOT fix on its own either the candidate or its own test script: it MUST report every error to the AI Coordinator, which assigns the fix; for the test agent this limits the autonomy of Delegate (§5). Fixing the test script is a task of its own, assigned and recorded by the AI Coordinator; the same test agent MAY receive it. Every fix reopens the affected checks (§9).

What is replaced: the autonomy of the test agent to fix gross errors. What is kept: running the script, recording the logs, checking completion or failure. Executors keep the ordinary two-way-door autonomy of §5 on their own work.

**2. §10, Backbone** (D10).

> Old: **Backbone.** The core components needed for the core deliverable. The Backbone MUST be built before all other components, and it covers, in minimal form, all the main paths of the core deliverable.
>
> New: **Backbone.** The core components needed for the core deliverable. The Backbone has the highest priority. The first usable path MUST run through it in minimal form, together with the Brain and the essential interfaces. The Backbone MUST then be completed over all the main paths of the core deliverable before the other components are extended.

What is replaced: "before all other components". What is kept: the Backbone as first priority and its coverage of all the main paths. In the same section, **Component contract** changes its last sentence to refer to the rule above:

> Old: The first usable path runs through Backbone and Brain and includes the essential interfaces.
>
> New: The first usable path runs through Backbone and Brain and includes the essential interfaces (see Backbone).

### Rules added or clarified

**3. §2, Management applied to AI** (D9). Two items are added at the end of the list; the sentence "Every rule transposes a known management practice" is unchanged.

> New: - *Internal control and segregation of duties* become the escalation classifier on a different model (E4) and verifiers independent of executors.
> - *Bills of materials and supply-chain traceability* become the software bill of materials and the run records.

**4. §5, Do** (R13). One item is added to the list of what MUST go to the Human Manager, after "new access;". It repeats, in the general list, the rule already in §9 High Level Architectural View, without widening or narrowing it.

> New: - changes that add an external service or move data outside the organisation (§9);

In §9 High Level Architectural View, "MUST go to the Human Manager as a Do." becomes "MUST go to the Human Manager as a Do (§5)."

**5. §5, E5 Drift budget** (R15).

> Old: **E5 · Drift budget.** Deviations from plan, class changes included, MUST add up in a drift budget cumulated over the project and reported every governance cycle. Beyond the threshold the mandate sets, a mandate review MUST be triggered.
>
> New: **E5 · Drift budget.** Deviations from plan, class changes included, MUST add up in a drift budget cumulated over the project, expressed in spending and in time, and reported every governance cycle. Class changes MUST also be reported as an item of their own. Beyond the threshold the mandate sets, a mandate review MUST be triggered.

**6. §5, E6 Measurement** (D1).

> Old: **E6 · Measurement.** The process reviewer MUST measure under-escalation (reserved decisions not brought to the Human Manager, over all reserved decisions) and over-escalation (Do escalations that fell within delegation, over all Do escalations).
>
> New: **E6 · Measurement.** The process reviewer MUST measure under-escalation (reserved decisions not brought to the Human Manager, over all reserved decisions) and over-escalation (Do escalations that fell within delegation, over all Do escalations). Both measures are estimates over a sample of micro-decisions (E3) and Do escalations. They MUST be reported with the number of decisions examined and with their confidence interval. A threshold is met only if the unfavourable bound of the interval stays within it.

Effect on §14.1 Level 1 · Evidence, whose text does not change: "under-escalation within the threshold" is now demonstrated only when the unfavourable bound is within the threshold.

**7. §6, K6 Measure the mechanism** (R14). One sentence is added at the end.

> New: The mandate MUST set what counts as a type of package, the minimum number of packages and the minimum margin over a single executor.

**8. §7, Retrospective** (R9).

> Old: **Retrospective.** At the end of each cycle the AI Coordinator MUST analyse the Scrum Masters' reports. It optimises the composition of the teams, for example by raising a role's seniority or changing its model, and reviews operational decisions.
>
> New: **Retrospective.** At the end of each cycle the AI Coordinator MUST analyse the Scrum Masters' reports. It optimises the composition of the teams, for example by raising a role's seniority or changing its model among those that its Role Profile enables and the mandate admits, and reviews operational decisions, that is the micro-decisions (E3) that touch neither approved Decisions nor reserved matters.

**9. §7.1, Catalogue** (D5). Community-maintained section. One sentence is added at the end. It clarifies and carries no key word, as decided.

> New: The correspondence is an assessment by the maintainers of the map; configurations not yet tested are marked as such.

**10. §7.1, Fallback** (D4). Community-maintained section.

> Old: **Fallback.** A task outside the catalogue MUST run at the fallback level that the mandate sets. The AI Coordinator MUST record the task and propose adding it to the catalogue (§15).
>
> New: **Fallback.** A task outside the catalogue MUST run at the fallback level that the mandate sets. The AI Coordinator MUST record the task, propose adding it to the catalogue (§15) and report in the cycle review the share of tasks run outside the catalogue.

The only change to this paragraph is the report of the share of tasks run outside the catalogue. The Guidance value of the fallback level moves down by one level, except for tasks that by their nature belong to the Lead level (architecture, security, effects hard to undo), which start at that level. Value and exception were approved as Guidance: both go in the Extended Framework and in the Digital Seniority map, and the Guide states no value (PA-2).

**11. §7.1, Team participation** (R5). Community-maintained section. One sentence is added at the end.

> New: The AI Coordinator MAY give tasks of different levels to different agents when the saving exceeds the cost of handing over the context.

**12. §7.1, Promotion and reduction** (D4, R14). Community-maintained section.

> Old: **Promotion and reduction.** When an agent has failed for lack of capability as many times as the mandate allows, the AI Coordinator MUST raise it to the next SD level and record the change. Promotion uses the attempts allowed by the Work Package record (§9); when they are exhausted, the AI Coordinator MUST open a decision point. In the retrospective the AI Coordinator MAY lower the level of a task when evidence shows unchanged quality at lower cost. That reduction is a two-way door within the mandate's tolerance; beyond it, it is a Do.
>
> New: **Promotion and reduction.** When an agent has failed for lack of capability as many times as the mandate allows, the AI Coordinator MUST raise it to the next SD level and record the change. For a task outside the catalogue, the AI Coordinator MUST raise the level at the first failure for lack of capability. Promotion uses the attempts allowed by the Work Package record (§9); when they are exhausted, the AI Coordinator MUST open a decision point. In the retrospective the AI Coordinator MAY lower the level of a task when evidence shows unchanged quality at lower cost, that is no increase in defects found after closure or in rework. That reduction is a two-way door within the mandate's tolerance; beyond it, it is a Do.

**13. §8, Gates** (R4).

> Old: **Gates.** At predefined gates the Human Manager MAY give new inputs, which start a new round of divergence.
>
> New: **Gates.** At the gates that the AI Coordinator sets and communicates at the start of Discovery, the Human Manager MAY give new inputs, which start a new round of divergence.

**14. §8, Convergence** (D2; decision of 2026-11-26 on the Discovery judge). Three sentences are added at the end of the paragraph, after "The Human Manager MUST then approve the Vision or relaunch the exploration."; the rest of the paragraph is unchanged.

> New: Convergence follows K1 (§6): the convergence criteria MUST be fixed before divergence, and, after the Discovery reviewers, the result MUST be assessed against them by a judge that runs on a model different from those of the members of the group, before the result reaches the Human Manager. The judge MUST be an agent distinct from the Discovery reviewers and MUST work under hard blinding (§7). When no model different from those of all the members of the group is available, the AI Coordinator MUST bring the choice of the judge's model to the Human Manager as a Do, presented in functional and economic terms (§5, Content of a Do); the judge then runs on the model the Human Manager chooses, and the level of independence achieved is recorded (§6).

In §8.1 **Discovery procedure**, a step is added after *Review.* (descriptive; the obligations are in §8):

> New: - *Judge.* The K1 judge assesses the result against the convergence criteria fixed before divergence.

In §7 **Hard blinding**, the last sentence changes accordingly:

> Old: Hard blinding MUST apply to the AI Coordinator, the AI Reviewer, the Design Thinking Facilitator and the Discovery reviewers (§8).
>
> New: Hard blinding MUST apply to the AI Coordinator, the AI Reviewer, the Design Thinking Facilitator, the Discovery reviewers and the Discovery judge (§8).

**15. §8, Governance cycle** (B12, D4). Two items are added to the content of the management review, after "spending and cost per accepted increment". The first carries into the Guide rule B12 of the working copy of specification 0.3; the Human Manager decided on 2026-11-26 that it enters the Guide. Item 20 depends on it. The second follows from item 10.

> New: the governance share, that is the cost of the AI Coordinator, the AI Scrum Masters, the reviewers, the escalation classifier (E4), the judges (K1), the applicability gate (§14) and the drafting of managerial documents (§12), over the total cost of the cycle;
> the share of tasks run outside the catalogue (§7.1);

**16. §9, new paragraph Risk Log** (D7; text of specification 0.3 §8), after **Log Tracker**.

> New: **Risk Log.** The risks of failure of the project and how they are managed. Business risks go to the Human Manager; the detail stays operational.

**17. §9, new paragraph Manager View** (R18), after **Shape of control artifacts**.

> New: **Manager View.** The tool through which the Human Manager reads the progress dashboard, the Do records and the findings addressed to them.

**18. §9.1, Test levels** (R2). Community-maintained section. One sentence is added at the end. It restores a sentence of specification 0.2 that was dropped without a changelog entry. It is proposed without a key word, as approved, so it adds no obligation; making it a SHOULD is for the Author.

> New: Security and performance testing is proportionate to the risk.

**19. §10, Brain** (D6). One sentence is added at the end.

> New: The mandate MUST set the criteria by which a Brain task is trusted or untrusted, and the role that applies them.

**20. §11, Run traceability** (R1).

> Old: **Run traceability.** Each run MUST record the profile hash, the exact model identifier, the effective configuration and the Unit Cost.
>
> New: **Run traceability.** Each run MUST record the profile hash, the exact model identifier, the effective configuration, the Unit Cost and the role of the agent, labelled as governance or production (§8, Governance cycle).

The rest of the paragraph is unchanged.

**21. §1 and §14, "business owner"** (R18). The term is replaced by "Human Manager" in the three places where it appears: §1 Development Environment ("on behalf of the business owner"), §14 Principle ("The risk that the business owner cannot assess") and §14 Applicability gate ("and the business owner informed"). §14 is a community-maintained section.

**22. §14.1, documents per level** (D7). Community-maintained section.

> Old: **Level 0 · Method.** A personal-use adoption MUST use qualified base Role Profiles and run the deterministic anchors at every release (§9). Its documents for the Human Manager MUST include the project record, the decision records, the governance cycle review and an installation and user manual.
>
> New: **Level 0 · Method.** A personal-use adoption MUST use qualified base Role Profiles and run the deterministic anchors at every release (§9). Its documents for the Human Manager MUST include the project record with the milestone plan, the decision records, the governance cycle review with the business risks, the High Level Architectural View, the progress dashboard and an installation and user manual.

In **Level 1 · Method**, the last item of the list changes:

> Old: - for the Human Manager, a management summary of the Security Risk Posture, a record of processing for the controller and an Executive Description.
>
> New: - for the Human Manager, a management summary of the Security Risk Posture, a record of processing for the controller, an Executive Description, the milestone plan as a document of its own and the business risks of the Risk Log as a register of its own.

A new paragraph is added after **Release documents**:

> New: **Operational documents.** At every level the operational layer MUST include the Product Backlog, the Work Package records, the run records and, for each team, the staffing plan and the Log Tracker.

**23. `HISTORY.md`, changes from 0.2 to 0.3** (R16). The paragraph on version 0.3 lists the restorations and the integrations only. A table is added with the other changes, one row each: the terms Human Manager and AI Coordinator; the "why Eiraman exists" paragraph with the definitions of human-in-the-loop and human-on-the-loop; the founding principle and its table; the first context principle rewritten; the Human Manager holding the Product Owner and Business Architect roles; the rationale of competitive mechanisms; the explicit independence rule for the tester; success criteria as KPIs; linked Decisions and Decisions that cannot violate a Principle; trusted and untrusted Brain tasks; the content of the Security Risk Posture; the test table, with the sentence on security and performance removed; the outcomes of the independent review of 0.3; the five integrations confirmed on 25 November. Origins confirmed from the project plan: the terms, the rewritten first principle and the management framing are decisions of the Human Manager of 25 November 2026; the five integrations completed truncated sentences of the founding drafts and were confirmed on the same day, without being listed one by one.

### Not included

- Corrections R6, R7, R8, R10 and R17 of the answer to the review: Guide 1.0.0-rc.2 already has that text (PA-6 B, PA-7, PA-8, Do-S03, Do-S04).
- Correction R12 (progress of a Work Package as mandatory checks passed over the total): the Guide does not describe the dashboard; §12 Percentages already applies. It goes to the AI Coordinator profile and to the Manager View tool.
- Decision D8: no change to the Guide.
- The rules on measuring the method (B1 to B11 of the working copy of specification 0.3): by decision of the Human Manager on 2026-11-26 they stay out of the Guide until the test bench has completed at least one campaign; a dedicated RFC will then decide.

## Reversibility

A change to the Guide text is a one-way door (GOVERNANCE §6.2). Most items add or clarify obligations; removing them later would be MAJOR under VERSIONING §2.1. Items 1 and 2 replace rules. While the Guide is a release candidate, not in force, rolling back costs a new candidate that restores the rc.2 text of the items above. Projects that already applied the new rules would keep them as project practice.

## Impact

- **Adopters.** Every Discovery gains a judge under hard blinding, on a model different from all the members of the group, in addition to the Discovery reviewers; when no such model is available, the choice becomes one more Do at the start of the project. Every error found by a test agent, including an error in its own script, goes through the AI Coordinator: one more hand-over each time. Tasks outside the catalogue start one level lower as Guidance, except those that by nature belong to the Lead level, and are promoted at the first failure; more rework is possible. At level 0 the documents for the Human Manager become six. Demonstrating under-escalation within a threshold needs more observed decisions, so the stay at level 0 before moving up becomes longer. The mandate gains values to set: criteria for trusted and untrusted tasks, type of package, minimum number of packages and margin for K6, and the threshold of the drift budget in spending and in time.
- **Role Profiles.** AI Coordinator: governance share in the cycle review, role label in run records, fallback wording, gates of Discovery, the K1 judge as an obligation, the new mandate items, progress shown with its denominator. Functional tester: the permission to fix its own script on its own is removed. Design Thinking Facilitator: convergence criteria fixed before divergence. Application and data architecture reviewer: it checks the classification of Brain tasks against the criteria of the mandate. Digital Seniority map: Guidance value of the fallback level, description of the Lead level, mark for untested configurations. Released separately.
- **Extended Framework.** Guidance values for the fallback level, the minimum number of packages for K6 and the sample for E6.
- **Tools.** Run records gain the role label. The Manager View shows the governance share and progress with its denominator. The traceability check gains the RFC rows; the count of transpositions in §2 changes from nine to eleven.
- **Translations.** None published yet.
- **Version.** Obligations are added or broadened and two rules are replaced. The Guide is a pre-release of 1.0.0, not in force, so the change is released as the next candidate, rc.3.

## Alternatives

Each decision was taken among alternatives recorded in the answer to the review; the main ones:

- **Do nothing.** Leaves two contradictions in the text (items 1 and 2) and a level-1 evidence that cannot be verified (item 6).
- **Correct specification 0.3 as well.** Rejected by D0: the specification is the historical source and receives only a note of its known defects.
- **Let the test agent fix its own script** (the reading of the current functional tester profile). Not chosen by D3: the Human Manager prefers that the test agent fixes nothing on its own.
- **Treat Discovery as exploration, outside K1.** Not chosen by D2: the Human Manager prefers an independent check before the result reaches them.
- **Common criteria for untrusted tasks, in the Guide.** Not chosen by D6: each project sets them in its mandate. The criteria considered (effects on people, personal data, money or irreversible actions; result not verifiable automatically; content coming from outside the organisation) can be published as Guidance.
- **A qualification test per SD level, common to all providers.** Not chosen by D5: the map stays the maintainers' assessment, declared as such.
- **A minimal team without an AI Scrum Master.** Not chosen by D8.

## Acceptance evidence

- `tools/release_diff.py` from `v1.0.0-rc.2` to the candidate: every removed line corresponds to an item above: an "Old" text, a paragraph whose only change is the sentence or reference stated in the item, or the replacements of item 21; no heading removed; the RFC 2119 counts rise only; item 1 turns an unkeyed permission into a prohibition.
- `TRACEABILITY.md`: all rc.2 rows kept; one row per new or changed paragraph, marked "RFC 0003".
- Independent scope review: every change maps to a decision D1 to D10, to a later decision of the Human Manager recorded in CR-009, or to an approved correction; no approved item is missing; no conflict with PA-2, PA-3, PA-6, PA-7, PA-8 and PA-12.
- The Author's decision on this RFC, with written reasons, before the release Do.

## Open questions

None. The questions of the draft were decided on 2026-11-26. Before acceptance, by the Human Manager: the governance share enters the Guide (items 15 and 20); the other rules on measuring the method stay out for now (Not included); the Discovery judge works under hard blinding and a missing different model goes to a Do (item 14); the AI Coordinator sets the gates of Discovery (item 13). At acceptance, by the Author: the two deviations recorded under Decision. After acceptance, by the Author: the K1 judge works after the Discovery reviewers (item 14); the applicability gate counts in the governance share (item 15); the origins of the rows of the history table were confirmed from the project plan (item 23).

## Decision

**Accepted**, on 2026-11-26, by the Author (Do-S19).

Written reasons: the corrections remove two contradictions and several rules that could not be applied, and every item follows a decision the Human Manager took on the findings of the critical review. No community member is active yet; founding contributors may reopen any item with a new RFC.

**Deviation from the comment period.** The decision was taken before the end of the comment period (2026-12-10), which `rfcs/README.md` sets at no less than fourteen days. The deviation is recorded here and in the changelog; it does not change the process for later RFCs.

**Deviation for community-maintained sections.** Items 1, 9, 10, 11, 12, 18, 21 and 22 change §7.1, §9.1, §14 and §14.1, which their working groups propose. The groups do not exist yet, so the Steward proposed the text and the Author accepted it, as for RFC 0001 (Do-S07). The working groups may revise it by RFC once they are formed.

**Decided after acceptance**, on 2026-11-26, by the Author: the K1 judge works after the Discovery reviewers; the applicability gate counts in the governance share; the origins of the rows of the history table are confirmed (Open questions).

**Implementation.** The items are applied in candidate 1.0.0-rc.3 of the Guide.
