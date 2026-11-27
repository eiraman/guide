<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# RFC 0005: Security classification in two modes, and the question round of Discovery

- **Author(s):** the Steward, on behalf of the working groups not yet formed
- **Accountable human:** Paolo Ungari (Steward)
- **AI-Use:** substantial (CONTRIBUTING.md §3)
- **Assisted-by:** Claude Fable 5.2
- **Assisted-by:** Claude Sonnet 5.5
- **Assisted-by:** Claude Opus 5.5 (drafting and independent review)
- **Conflicts of interest:** none
- **Owner of the decision:** Author (Guide)
- **Affected artifacts:** Guide §2, §3, §4, §5, §8, §8.1, §9, §12, §13, §14, §14.2; `TRACEABILITY.md`. After acceptance, in separate releases: Role Profiles (Security Officer, AI Coordinator, security, privacy and legal and compliance reviewers, Design Thinking Facilitator, User Persona template), Extended Framework, Tools, site and kit
- **State:** accepted
- **Dates:** opened 2026-11-27 · comment period ends 2026-12-27 · accepted 2026-11-27, before the end of the comment period (deviation, see Decision)
- **Change request:** CR-022 and CR-023 of the project "Eiraman Open Framework"; decided by Do-S29

## Summary

Guide 1.0.0-rc.4 lets the security classification stop a project: when its class exceeds the qualified level, when an exclusion applies, when the case is in doubt. This RFC makes that behaviour one of two modes. In the **blocking** mode the classification works as in rc.4, with everything decided so far: classes, levels, exclusions, the Security Officer that proposes treatments, and the decision of the Human Manager to run a class 1 project from level 0. In the **informative** mode the same rules stop nothing: the Security Officer applies them in silence to find what the blocking mode would have stopped or asked, and records it in a **Security Report** that is delivered with the project. The Human Manager answers for proceeding. The requirements that only the adoption levels set become optional and are listed in the report when not met; such a project gives no evidence for moving up. In the informative mode the classification itself stops nothing; the mandate, Deny and the Do escalations that stay with the Human Manager still apply. In both modes an action that a model refuses is not performed, by any model. Personal data, third parties and changes of class are recorded in the report instead of going to the Human Manager as a Do.

The RFC also adds a **question round** at the start of Discovery (CR-023): every executor says what is not known and who should be asked, the User Personas give a first answer with its source and confidence, and the questions at the lowest confidence, up to the number the mandate sets, reach the Human Manager before divergence. It applies in both modes. The Human Manager decided to carry the two changes in one RFC (decision 40).

The Human Manager can choose the mode when the project opens, and the mandate records it. Without a choice, the informative mode applies when the adopter uses the method for themselves and the blocking mode applies in every other case, doubt included. An organisation can impose the blocking mode on the projects opened, and the new versions approved, while its rules are in force. The mode does not otherwise change during a project.

The informative mode has no limit of its own: AI systems that the law prohibits, data on health, children's data and the other cases out of scope are recorded and do not stop the project. The Human Manager decided this, on the ground that for personal use on external engines the limits of those engines already act as the limit of law. Where an engine runs locally those limits are missing: the mandate states the use of a local engine, so that the Human Manager approves it with the mandate, or by a Do when it is needed before the mandate is approved, and the report says so.

The change concerns every adopter, the AI Coordinator, the Security Officer and the security and privacy reviewers. For the informative mode it reverses a context principle of the Guide (§3, "Some uses are excluded"), the principle of the adoption levels and the rule on the cases out of scope at any level (§14).

The RFC changes §14, which is community-maintained and whose working groups do not exist yet; the Steward proposes the text here and the Author accepts it by RFC (Guide §0, §15). Because it relaxes requirements of the adoption levels, its comment period is thirty days (`rfcs/README.md`, step 3).

## Motivation

The evidence comes from the project's test bench, on 26 and 27 November 2026: one run per project, with a kit that included the Security Officer and Role Profiles still written for Guide 1.0.0-rc.3 (CR-018). The Human Manager received from five to fourteen security questions per project, against none to four needs of the work that emerged. Every run built a reduced version of what was asked. A family film was reduced to the photographs without people, and the Human Manager had the run stopped. A personal project with no data of other people still opened with five security questions. A pair of agents working without the method delivered what was asked for after one exchange, and noticed no risk on the data.

The Human Manager judged that the method "is becoming too concentrated on security" and decided (CR-022): "The security classification can be blocking or informative. In the blocking case it works as today. In the informative case it traces all the evidence found in a Security Report delivered with the project, and it is the responsibility of the Manager. In the informative case the only actions that are not carried out are those that by their nature the models used do not perform", copyright violations being the example given. The decisions that followed, all recorded in CR-022:

1. the Human Manager chooses the mode when the project opens, and the mandate records it; without a choice, the informative mode applies to personal use and the blocking mode applies when there is a formal mandate from the organisation;
2. the organisation can impose the blocking mode through its own rules;
3. the Security Report is delivered with the project; it is updated at every Wave and at every release; it opens with a fixed line on the responsibility of the Human Manager; it contains the class, the findings on data with where they were found, the exclusions touched, the protections applied by delegation, the protections recommended and not applied, and the actions the models refused with the reason;
4. in the informative mode the Security Officer is silent: it asks the Human Manager nothing and writes nothing to them; the scope is not reduced (request of CR-022); what it cannot determine goes in the report as not determined; the protections applied by delegation are recorded;
5. in the informative mode AI systems that the law prohibits are not excluded: they are recorded, like the other cases. The AI Coordinator had recommended keeping them excluded in both modes;
6. everything decided so far stays in the blocking mode, and in the informative mode it serves to generate the findings of the report; for personal use on external engines, the limits those engines place already act as the limit of law;
7. where an engine runs locally, in the informative mode the report says so, and the Security Officer notifies the risk when the project opens and asks the Human Manager for explicit approval to proceed; everything else is logged in the report;
8. in the informative mode personal data and third parties do not go to the Human Manager as a Do: they go in the report. Irreversible actions, spending, new access and changes of Decision stay with the Human Manager;
9. without a choice, the informative mode applies only when the adopter uses the method for themselves; in every other case the blocking mode applies. This specifies decision 1;
10. when a model refuses an action, the refusal stands: the AI Coordinator does not turn to another model;
11. the mode does not change during a project: a different mode needs a new project. The AI Coordinator had recommended allowing the change;
12. in the informative mode the class needs no approval of the Human Manager: it is recorded in the report;
13. the use of a local engine is stated in the mandate and approved once with it; a local engine added later is a change of mandate. This replaces the separate notification of decision 7;
14. the informative mode can be chosen also under a formal mandate, unless the rules of the organisation impose the blocking mode;
15. a model's refusal stands in both modes;
16. rules of the organisation that impose the blocking mode and reach a project already open in the informative mode do not change it: they apply to the following projects. The AI Coordinator had recommended stopping the project;
17. a local engine can be used before the mandate is approved, by a Do. This amends decision 13. The AI Coordinator had recommended keeping the prohibition;
18. in the informative mode the declared limits of the Security Officer and of the security, privacy and legal and compliance profiles are recorded in the report;
19. when competing candidates work on the same package, one refusal stops the action for all of them;
20. in the informative mode personal data and third parties do not go to the Human Manager as a Do on that ground, even where the mandate reserves them. This specifies decision 8. The AI Coordinator had recommended that the mandate prevail;
21. every refusal of a model stands, whatever its ground; the words "by their nature" of the request do not leave the AI Coordinator a judgement on it;
22. in the informative mode a change of class does not count towards the drift budget. The AI Coordinator had recommended counting it;
23. in the informative mode the requirements that only the adoption levels set become optional; what other rules of the Guide require stays due, the deterministic anchors, the qualified Role Profiles, the project record and the High Level Architectural View among them. The AI Coordinator had recommended keeping the requirements of level 0 due;
24. moving up rests on projects in the blocking mode only. The AI Coordinator had recommended admitting evidence from both modes;
25. in the informative mode personal data found by the security and privacy reviewers is recorded in the report; defects of the code still keep a package open;
26. the change does not change the Vision of the project;
27. when no mode is chosen and personal use is in doubt, the blocking mode applies;
28. "the only actions not carried out" concerns the classification: the mandate, the data classes per provider, irreversible actions and the other Do escalations still apply;
29. in the blocking mode a model's refusal is shown in the cycle review too;
30. confirmed together: a repeated gate may be recorded by reference; the report does not reproduce the data and names the engines used; protections applied by delegation are only the reversible ones that take nothing away from the request; a case with no class is recorded as out of scope; the report is part of the third-party evidence pack and is attached in the Manager View; the mode applies from the opening; after a refusal the package is closed or re-planned without the action, and the refusal does not count as a lack of capability.

31. in the informative mode every requirement that only the adoption levels set is optional, organisation and technical requirements included. The AI Coordinator had recommended limiting it to the documents;
32. the error budget applies in both modes;
33. in the informative mode, when a requirement that stays due lapses, the work that depends on it is suspended;
34. the findings of the legal and compliance reviewers on the class, the personal data and the exclusions go in the report too;
35. a new version approved after rules of the organisation impose the blocking mode adopts it. This amends decisions 11 and 16;
36. a refusal is what a model declines on the grounds of its own rules; what it cannot complete follows the rules on lack of capability;
37. the spending and time caused by a change of class count in the drift budget as any deviation;
38. local engines are stated in the mandate both when they run the agents and when they are part of the product;
39. for a case out of scope the report lists the requirements not met up to the highest level;
40. the question round of CR-023 is carried by this RFC. The AI Coordinator had recommended a separate RFC;
41. a refusal of a mandatory check keeps the package open and goes to the Human Manager as a Do; when refusal and incapacity are in doubt, it is a refusal;
42. until the mandate is approved, the number of questions that the AI Coordinator communicates at the start of Discovery applies;
43. with several User Personas the lowest confidence counts and the different answers reach the Human Manager with the question;
44. the documents that §12 lists stay due in the informative mode.

**The question round (CR-023).** In five runs on the test bench the Business Analyst and the User Personas raised as many doubts about the customer as the other members of the Discovery group, or more, and those questions did not reach the Human Manager: there was no channel for them, the Persona answered in place of the customer, the questions were chosen without seeing the contributions, and the summary lost the precise point. The Human Manager decided: every member asks first what is not known; the Persona gives a first answer with a confidence level that follows its source; the questions at the lowest confidence reach the Human Manager with the answer supposed, at equal confidence first those whose error costs most; the other answers are taken as correct and stay visible as assumptions; technical questions and questions for a member do not take those places; in the informative mode questions on security go to the Security Report. The Human Manager first spoke of five questions; the text leaves the number to the mandate, since the Guide states no values (§0).

**Limits of the evidence.** One run per project does not show a difference by the method's own rules on measurement, and the runs used a draft Security Officer profile written before the Guide named the role. The evidence shows a problem of proportion; it does not separate what comes from the method from what comes from that draft profile. The decision is a judgement of the Human Manager on what the method is for.

The management practice behind the change is the risk register: whoever decides is told what was found and answers for going on.

## Proposal

The proposed text is below, item by item. `EIRAMAN-GUIDE.md` is not changed by this draft; on acceptance the items are applied as candidate 1.0.0-rc.5.

| Section | Change | Kind | Source |
|---|---|---|---|
| §8 and §8.1 Discovery | Question round; a gate after it; User Personas and procedure | New paragraph and step; modified lines | CR-023; decisions 42 and 43 |
| §9 Shape of control artifacts | The minimum content of the adoption level binds in the blocking mode | Modified line | Decisions 23, 31 and 44 |
| §14 Applicability | New paragraph Classification mode; Principle, Deliverables, Out of scope at any level, Project classes and Applicability gate stop a project in the blocking mode only; new paragraphs Out of scope in the informative mode, Security Officer in the informative mode, Local engines in the informative mode | New paragraphs; modified lines | CR-022, decisions 1 to 7, 9 to 17, 19, 21, 23 to 25, 27, 29 to 36, 38, 39 and 41 |
| §3 Context principles | Some uses are excluded: in the blocking mode only | Modified line | Decisions 5 and 6 |
| §2 Eiraman theory | Adoption levels limit risk or make it known | Modified line | CR-022 and decision 26 |
| §4 Accountabilities | Internal accountability and Liability towards third parties in the informative mode | Modified lines | CR-022 |
| §5 3D escalation | Deny; reserved matters and class change in the informative mode; drift budget | Modified lines | Decisions 1, 6, 8, 12, 20, 22, 28 and 37 |
| §9 Commitments and artifacts | Project record names the classification mode | Modified line | Decision 1 |
| §12 Writing for the Human Manager | New paragraph Security Report; managerial layer; third-party evidence pack | New paragraph; modified lines | Decisions 3, 18 and 30 |
| §14.2 Moving between levels and classes | Class change in the informative mode | Modified line | Decisions 12, 22 and 37 |
| §4 and §8 | In the informative mode the class is recorded and needs no approval | Modified lines | Decision 12 |
| §13 Role Profiles | Declared limits of the Security Officer and of security, privacy and legal and compliance profiles in the informative mode | Modified line | Decision 18 |

No section number changes. No paragraph label is removed.

### Items

**1. §14, new paragraph Classification mode**, before **Principle**. Community-maintained section.

> New: **Classification mode.** The security classification of a project works in one of two modes. In the *blocking* mode the rules of this section stop a project, as each of them states. In the *informative* mode the same rules stop nothing: the Security Officer applies them to find what the blocking mode would have stopped or asked, and MUST record the class and every finding in the Security Report (§12); the Human Manager answers for proceeding. The Human Manager MAY choose the mode when the project opens, and the mandate MUST record the mode that applies. If no mode is chosen, the informative mode MUST apply when the adopter uses the method for themselves, and the blocking mode MUST apply in every other case. When no mode is chosen and it is in doubt whether the adopter uses the method for themselves, the blocking mode MUST apply; the AI Coordinator MUST record in the mandate the ground on which the mode applies. An organisation MAY impose the blocking mode through its own rules, which are a binding input of the mandate; the mode it imposes MUST apply to every project opened, and to every new version of a project approved, while those rules are in force. Rules that reach a project already open in the informative mode MUST NOT change the mode of the version in progress: the blocking mode they impose MUST apply only to the projects opened and the versions approved afterwards. The mode MUST apply from the opening of the project and MUST NOT change during it, at the approval of the mandate included, except for a new version under such rules; otherwise a different mode MUST have a new project. In the informative mode the classification MUST NOT stop or reduce any action. The rules of §14.2 that stop a project or limit its data or releases, Automatic downgrade and Running above the qualified level among them, MUST NOT stop the project or limit its data or releases, except that when a requirement that another rule of this Guide sets lapses, the environment MUST Deny the work that depends on it until the requirement is restored. Error budget (§14.1) MUST apply in both modes. A requirement of §14.1, at any level, other than Error budget, that no other rule of this Guide sets MAY be left unmet; the Security Report MUST list the requirements not met, up to the qualified level or the level of the same number as the class of the project, whichever is higher, and up to the highest level when the case is among those out of scope at any level or fits no class. Moving up (§14.2) MUST apply in both modes, and the evidence of a project in the informative mode MUST NOT count towards a higher level. In both modes an action that a model refuses MUST NOT be performed: the AI Coordinator MUST NOT have it performed by the same model with another request, or by another model, candidate or Digital Seniority level, and when competing candidates run the same Work Package, the output of every candidate for that action MUST be discarded; in the informative mode the refusal MUST be recorded in the Security Report with the reason, and in the blocking mode in the Log Tracker and in the cycle review; a refusal is an action that a model declines on the grounds of its own rules, and it MUST NOT count as a failure for lack of capability; an action that a model cannot complete MUST follow §7.1; the AI Coordinator MUST record a refused action as not performed and close the Work Package without it, when its mandatory checks pass, or re-plan it. When it is in doubt whether a model declines on the grounds of its own rules or cannot complete an action, the case MUST count as a refusal. When a refused action is a mandatory check, the Work Package MUST stay open, the check MUST NOT be repeated or assigned to another verifier under Dissent or missing proof (§9), and the AI Coordinator MUST bring the decision to the Human Manager as a Do. The other rules of this Guide MUST apply in both modes.

**2. §14, Principle.** Community-maintained section.

> Old: **Principle.** Specialist competence lives in qualified Role Profiles, not in specialists present in every project. The risk that the Human Manager cannot assess is therefore limited from the start. Every adoption of Eiraman MUST have a qualified adoption level and every project MUST have a class. A project MUST NOT run if its class exceeds the qualified level of the adopter, except by the decision of the Human Manager that §14.2 allows (Running above the qualified level). Whoever uses the method for themselves stays at level 0. To move up, an adopter MUST meet the requirements of the next level and demonstrate them with evidence.
>
> New: **Principle.** Specialist competence lives in qualified Role Profiles, not in specialists present in every project. In the blocking mode the risk that the Human Manager cannot assess is therefore limited from the start; in the informative mode it is made known in the Security Report. Every adoption of Eiraman MUST have a qualified adoption level and every project MUST have a class or, in the informative mode, the record that it fits none (Out of scope in the informative mode). In the blocking mode, a project MUST NOT run if its class exceeds the qualified level of the adopter, except by the decision of the Human Manager that §14.2 allows (Running above the qualified level). In the informative mode the class MUST NOT stop the project, and the Security Officer MUST record it in the Security Report. Whoever uses the method for themselves stays at level 0. To move up, an adopter MUST meet the requirements of the next level and demonstrate them with evidence.

**3. §14, Deliverables.** Community-maintained section.

> Old: **Deliverables.** Classes also apply to the deliverables a product generates. For example, a level 0 adoption MUST NOT use a document generator to produce documents for customers, which are class 2.
>
> New: **Deliverables.** Classes also apply to the deliverables a product generates. For example, in the blocking mode a level 0 adoption MUST NOT use a document generator to produce documents for customers, which are class 2. In the informative mode the Security Officer MUST record the class of the deliverables in the Security Report.

**4. §14, Out of scope at any level.** Community-maintained section. The opening sentence changes; the list is unchanged.

> Old: **Out of scope at any level.** The method MUST NOT be applied to projects that involve:
>
> New: **Out of scope at any level.** In the blocking mode the method MUST NOT be applied to projects that involve:

A new paragraph is added after "The Extended Framework maps these categories to the law of each jurisdiction, starting with the European Union.":

> New: **Out of scope in the informative mode.** In the informative mode the cases above MUST NOT stop the project: the Security Officer MUST record in the Security Report each case it finds. A case that fits no class MUST be recorded as out of scope, and the project record MUST state it in place of the class.

**5. §14, Applicability gate.** Community-maintained section.

> Old: **Applicability gate.** The Security Officer, an AI compliance role under its own qualified Role Profile, MUST assign the class, using a versioned checklist qualified by the maintainers. The AI Coordinator MUST invoke the Security Officer and MUST NOT assign the class itself. The gate MUST run when the project opens, at every Wave and at every change of mandate. If an exclusion criterion is triggered, or the case is in doubt, the project MUST be treated as out of scope and the Human Manager informed; when the only doubt is a question for the organisation not yet answered, the work on test data that Questions for the organisation allows MAY go on.
>
> New: **Applicability gate.** The Security Officer, an AI compliance role under its own qualified Role Profile, MUST assign the class or, in the informative mode, record that the case fits none, using a versioned checklist qualified by the maintainers. The AI Coordinator MUST invoke the Security Officer and MUST NOT assign the class itself. The gate MUST run when the project opens, at every Wave and at every change of mandate. In the blocking mode, if an exclusion criterion is triggered, or the case is in doubt, the project MUST be treated as out of scope and the Human Manager informed; when the only doubt is a question for the organisation not yet answered, the work on test data that Questions for the organisation allows MAY go on. In the informative mode the gate MUST NOT stop the project: the Security Officer MUST record in the Security Report the class, the exclusion criteria triggered and what it could not determine; when the scope has not changed since the last run, the Security Officer MAY record the repeated gate in the Log Tracker and in the Security Report by reference to the last run.

**6. §14, new paragraphs Security Officer in the informative mode and Local engines in the informative mode**, after **Independence of the Security Officer**, before **Legal advice**. Community-maintained section.

> New: **Security Officer in the informative mode.** In the informative mode the Security Officer is silent: it MUST NOT start an exchange with the Human Manager or question them, and it MUST NOT write to the Human Manager except in the Security Report and to answer the questions they put under Dialogue with the Human Manager. The scope of the project MUST NOT be reduced on grounds of the classification. What the Security Officer cannot determine MUST be recorded in the Security Report as not determined. The AI Coordinator MAY apply, by delegation, protections proposed by the Security Officer that are reversible and take nothing away from the request; they MUST be recorded in the Security Report. Risk profile, Treatments and Questions for the organisation MUST apply in the blocking mode only. The findings of the security, privacy and legal and compliance reviewers on the class, on the presence of personal data and on the exclusion criteria MUST be recorded in the Security Report and MUST NOT keep a Work Package open, or stop or reopen a phase; their other findings MUST follow §9, defects in how the product handles personal data among them. In the Manager View the current Security Report MUST be attached in place of the risk profile (Dialogue with the Human Manager).

> New: **Local engines in the informative mode.** The limits that the providers of external engines place on their models do not apply to an engine that runs locally. In the informative mode the mandate MUST state which local engines, if any, run the agents of the project or are part of the product, so that the Human Manager approves that use with the mandate; adding a local engine later is a change of mandate and MUST go to the Human Manager as a Do; a local engine MUST NOT be used before the Human Manager has approved its use, with the mandate or, before the mandate is approved, as a Do. The Security Report MUST name the engines used and, when one of them runs locally, MUST say so and that the limits of the providers of external engines do not apply to it.

**7. §3, Some uses are excluded.** A context principle of the Guide.

> Old: - **Some uses are excluded.** The method MUST NOT be applied to AI systems that applicable law prohibits or classes as high-risk, nor to the other out-of-scope cases of §14.
>
> New: - **Some uses are excluded.** In the blocking mode of §14 the method MUST NOT be applied to AI systems that applicable law prohibits or classes as high-risk, nor to the other out-of-scope cases of §14. In the informative mode those cases MUST NOT stop the project and MUST be recorded in the Security Report (§12).

**8. §2, Management applied to AI**, the item on scope and risk management.

> Old: - *Scope and risk management* become versioned Principles and Decisions, a Risk Log and adoption levels that limit risk up front.
>
> New: - *Scope and risk management* become versioned Principles and Decisions, a Risk Log and adoption levels that limit risk up front or, in the informative mode, make it known.

**9. §4, Internal accountability.**

> Old: **Internal accountability.** Everyone MUST answer for what they decide. The Human Manager answers for decisions within their remit and for using the method within the qualified scope. The AI Coordinator and the AI roles answer in an operational sense, not a legal one: every closure MUST have evidence and every error MUST become a retrospective case. Maintainers answer for the conformity of profiles to their sources at the time of qualification, not for individual projects.
>
> New: **Internal accountability.** Everyone MUST answer for what they decide. The Human Manager answers for decisions within their remit and for using the method within the qualified scope in the blocking mode or, in the informative mode (§14), for proceeding with what the Security Report records. The AI Coordinator and the AI roles answer in an operational sense, not a legal one: every closure MUST have evidence and every error MUST become a retrospective case. Maintainers answer for the conformity of profiles to their sources at the time of qualification, not for individual projects.

**10. §4, Liability towards third parties.** One sentence is added after "liability towards third parties lies with that organisation."; the rest of the paragraph is unchanged.

> New: In the informative mode (§14) the Human Manager answers for proceeding with what the Security Report records; liability towards third parties for the data of which an organisation is the controller lies with that organisation; the method does not move obligations that the law places on an organisation or on anyone else; in the informative mode the owner exercises this responsibility through mandate and acceptance.

**11. §5, Deny.**

> Old: **Deny.** The environment, not the agent, MUST block an action that the mandate forbids or that lies outside the adoption level, and MUST record why. For a project admitted under §14.2 (Running above the qualified level), class 1 takes the place of the adoption level, unless a requirement of level 1 that the paragraph makes due is due and not met; while work goes on only on test data under Questions for the organisation (§14), with or without the decision of §14.2, the environment MUST also block any data other than test data, masked data included, and every release. The AI Coordinator MUST look for an authorised alternative; if there is none, it MUST suspend the affected work.
>
> New: **Deny.** The environment, not the agent, MUST block an action that the mandate forbids or, in the blocking mode (§14), that lies outside the adoption level, and MUST record why. For a project admitted under §14.2 (Running above the qualified level), class 1 takes the place of the adoption level, unless a requirement of level 1 that the paragraph makes due is due and not met; while work goes on only on test data under Questions for the organisation (§14), with or without the decision of §14.2, the environment MUST also block any data other than test data, masked data included, and every release. The AI Coordinator MUST look for an authorised alternative; if there is none, it MUST suspend the affected work.

**12. §5, Do**, two items of the list.

> Old: - the mandate's reserved matters: impact on Vision, Principles or success criteria, personal data, third parties, new suppliers, spending above the threshold the mandate sets;
>
> New: - the mandate's reserved matters: impact on Vision, Principles or success criteria, personal data, third parties, new suppliers, spending above the threshold the mandate sets; in the informative mode (§14) personal data and third parties MUST be recorded in the Security Report and MUST NOT go to the Human Manager as a Do on that ground alone, even where the mandate reserves them; the other items of this list still apply;

> Old: - changes of project class, adoption-level upgrades and the decision to run a project above the qualified level. Downgrades are automatic (§14.2).
>
> New: - changes of project class, adoption-level upgrades and the decision to run a project above the qualified level. Downgrades are automatic (§14.2). In the informative mode a change of class MUST be recorded in the Security Report and MUST NOT go to the Human Manager as a Do on that ground alone; the other items of this list still apply.

**13. §9, Project record.**

> Old: **Project record.** The project record MUST identify: the application, its users, deliverables, repository and revision; the Eiraman version used, the class and the adoption level; the Eiraman components built into the product, and any adaptations; and the success criteria.
>
> New: **Project record.** The project record MUST identify: the application, its users, deliverables, repository and revision; the Eiraman version used, the class, the adoption level and the classification mode; the Eiraman components built into the product, and any adaptations; and the success criteria.

**14. §12, Three layers of documentation**, the managerial layer, and **Third-party evidence pack**.

> Old: - *Managerial.* For the Human Manager, who reads and decides by exception: project record, milestone plan, High Level Architectural View, decision records, business risks, dashboard, cycle review, acceptance outcome, cost report, security and performance summaries. Verified by an AI reviewer.
>
> New: - *Managerial.* For the Human Manager, who reads and decides by exception: project record, milestone plan, High Level Architectural View, decision records, business risks, dashboard, cycle review, acceptance outcome, cost report, security and performance summaries and, in the informative mode, the Security Report. Verified by an AI reviewer.

> Old: - **Third-party evidence pack.** On request, for a single release, the AI Coordinator MUST produce a pack containing the mandate, class and adoption level, profiles and versions, checks and outcomes, independent verifications, accepted risks and acceptance. At level 2 the pack MUST be ready at every release.
>
> New: - **Third-party evidence pack.** On request, for a single release, the AI Coordinator MUST produce a pack containing the mandate, class, adoption level and classification mode, profiles and versions, checks and outcomes, independent verifications, accepted risks and acceptance. At level 2 the pack MUST be ready at every release. In the informative mode the pack MUST include the Security Report.

**15. §12, new paragraph Security Report**, after **Cost report**.

> New: **Security Report.** In the informative mode (§14) every release MUST ship a Security Report. The writing rules MUST apply to it, except that it MUST open, in place of the four questions, with a fixed line stating that the Human Manager answers for proceeding, followed by what changed since the last reading, and MUST NOT ask anything. It MUST contain: the class, or that the case is out of scope; the findings on data, each with where it was found; the exclusion criteria triggered; the engines used; the protections applied; the protections recommended and not applied, the requirements not met among them; the declared limits recorded under §13; the actions the models refused, with the reason; and what could not be determined, the questions on security of the question round (§8) among it. It MUST say where a finding was found without reproducing the data. It MUST be updated at every Wave and at every release.

**16. §13, Minimum content**, the item on declared limits.

> Old: - declared limits: if a Work Package falls within them, the project leaves the scope of the method;
>
> New: - declared limits: if a Work Package falls within them, the project leaves the scope of the method; in the informative mode of §14 a limit of the Security Officer or of a security, privacy or legal and compliance profile MUST instead be recorded in the Security Report;

**17. §14.2, Class change.** Community-maintained section.

> Old: **Class change.** A change of class MUST always go to the Human Manager as a Do and counts towards the drift budget (E5). If the new class exceeds the level, the Human Manager MUST choose one of four options: reduce the scope, hand the critical component to a certified provider, take that project out of the method or, where Running above the qualified level allows it, let the project run by decision.
>
> New: **Class change.** In the blocking mode (§14) a change of class MUST always go to the Human Manager as a Do and counts towards the drift budget (E5). If the new class exceeds the level, the Human Manager MUST choose one of four options: reduce the scope, hand the critical component to a certified provider, take that project out of the method or, where Running above the qualified level allows it, let the project run by decision. In the informative mode a change of class MUST be recorded in the Security Report and MUST NOT count towards the drift budget (E5) as a change of class; the spending and time of the work it causes MUST count as any other deviation from plan.

**18. §4, Human Manager**, the item on what the Human Manager approves.

> Old: - MUST approve the Vision, Principles, success criteria, mandate, spending, project class and adoption-level upgrades;
>
> New: - MUST approve the Vision, Principles, success criteria, mandate, spending, adoption-level upgrades and, in the blocking mode (§14), the project class;

**19. §8, Phases and decisions**, the item on Discovery.

> Old: - *Discovery* yields the problem, benefit, discarded alternatives, a draft Vision, the first draft of Scope Management and the class set by the applicability gate (§14). The Human Manager approves Vision, mandate and class, or relaunches exploration.
>
> New: - *Discovery* yields the problem, benefit, discarded alternatives, a draft Vision, the first draft of Scope Management and the class set by the applicability gate (§14). The Human Manager approves Vision, mandate and, in the blocking mode (§14), class, or relaunches exploration.

**20. §14, Project classes.** The opening sentence changes; the table is unchanged. Community-maintained section.

> Old: **Project classes.** Every project MUST be assigned one of the following classes.
>
> New: **Project classes.** Every project MUST be assigned one of the following classes, except that in the informative mode a case that fits none MUST be recorded as out of scope (Out of scope in the informative mode).

**21. §5, E5 · Drift budget.** One sentence is added to the rule.

> Old: - **E5 · Drift budget.** Deviations from plan, class changes included, MUST add up in a drift budget cumulated over the project, expressed in spending and in time, and reported every governance cycle. Class changes MUST also be reported as an item of their own. Beyond the threshold the mandate sets, a mandate review MUST be triggered.
>
> New: - **E5 · Drift budget.** Deviations from plan, class changes included, MUST add up in a drift budget cumulated over the project, expressed in spending and in time, and reported every governance cycle. Class changes MUST also be reported as an item of their own. Beyond the threshold the mandate sets, a mandate review MUST be triggered. In the informative mode (§14) a change of class MUST NOT count towards the drift budget or be reported as an item of its own: it MUST be recorded in the Security Report; the spending and time of the work it causes MUST count as any other deviation from plan.

**22. §8, new paragraph Question round**, before **Divergence**. CR-023.

> New: **Question round.** Before divergence, the Design Thinking Facilitator MUST submit the same prompt to every executor of the group, asking what is not known and who should be asked. It MUST merge the questions into a question register, keeping their words, topic, author and addressee and whether a choice that is not reversible depends on them, and removing only duplicates. It MUST then submit the register, without the authors, to the User Personas, which MUST give for each question an answer, its source and a confidence level. The level MUST follow the source: high only when the answer is written in the request or in the materials of the Human Manager and the quotation answers that question, medium when it is deduced from what is written, low when it is supposed. When several User Personas give different answers or confidence levels to a question, the lowest confidence level MUST count; when that question reaches the Human Manager, the different answers MUST reach them with it, and otherwise they MUST all be recorded among the assumptions. Among the questions addressed to the Human Manager or to a person outside the Discovery group that are not at high confidence, the Facilitator MUST send to the Human Manager, through the AI Coordinator, those at the lowest confidence, up to the number that the mandate sets, each with the answer supposed; until the mandate is approved, the number that the AI Coordinator communicates with the gates at the start of Discovery MUST apply; at equal confidence, first those on which a choice that is not reversible depends, then those whose topic changes what the end user sees or does, then in the order of the question register. Technical questions and questions for a member of the group MUST NOT take one of these places. The answers not asked MUST be taken as correct and recorded as assumptions visible to the Human Manager. Without an answer by the gate, Discovery MUST continue and the suppositions MUST remain unconfirmed assumptions. In the informative mode (§14), questions on security MUST NOT take one of these places or be recorded among those assumptions: the Security Officer MUST record them in the Security Report as not determined. The question round MUST NOT count toward the maximum number of rounds.

**23. §8, Gates.** One sentence is added. CR-023.

> Old: **Gates.** At the gates that the AI Coordinator sets and communicates at the start of Discovery, the Human Manager MAY give new inputs, which start a new round of divergence.
>
> New: **Gates.** At the gates that the AI Coordinator sets and communicates at the start of Discovery, the Human Manager MAY give new inputs, which start a new round of divergence. One gate MUST follow the question round and precede divergence; it MUST carry the questions of that round.

**24. §8.1, Roles in the Discovery group**, the User Personas. CR-023.

> Old: - *User Personas:* stand for the users of the application; later they run the simulated-user functional tests (§9.1).
>
> New: - *User Personas:* stand for the users of the application; give a first, supposed answer to the questions of the question round, which stays an assumption until the Human Manager answers; later they run the simulated-user functional tests (§9.1).

**25. §8.1, Discovery procedure.** A step is added before *Same prompt*. CR-023.

> New: - *Questions.* Once, before the first round, it runs the question round (§8, Question round).

**26. §9, Shape of control artifacts.** Decisions 23, 31 and 44.

> Old: **Shape of control artifacts.** Each project and each Human Manager decide the shape of the dashboards, views and documents they use for control, and MUST record the choice as a project decision. The minimum content required by this Guide and by the adoption level MUST NOT be reduced.
>
> New: **Shape of control artifacts.** Each project and each Human Manager decide the shape of the dashboards, views and documents they use for control, and MUST record the choice as a project decision. The minimum content required by this Guide and, in the blocking mode (§14), by the adoption level MUST NOT be reduced; in the informative mode the content that only §14.1 requires MAY be left out and MUST be listed in the Security Report, and the documents that §12 lists MUST be kept as in the blocking mode.

### Paragraphs that do not change, and why

- **§14.2, Running above the qualified level** (RFC 0004). Unchanged, by decision 6: it is the exception of the blocking mode. In the informative mode it is not needed, because the class does not stop the project.
- **§14.1 and §14.2**, apart from the above. The text is unchanged: item 1 says what it does in the informative mode. The rules of §14.2 that stop a project or limit its data or releases do not do so, except for the Deny on the work that depends on a lapsed requirement that another rule sets; the error budget applies in both modes; a requirement of §14.1 that no other rule sets may be left unmet and is listed in the report; what other rules require stays due; Moving up applies in both modes and takes no evidence from the informative mode; Class change is item 17.
- **§14, Risk profile, Treatments, Questions for the organisation.** Unchanged: by item 6 they apply in the blocking mode only.
- **§14, Dialogue with the Human Manager.** Unchanged: the Human Manager MAY question the Security Officer at any time, in both modes; in the informative mode the Security Officer does not start the exchange, and no risk profile exists: by item 6 the Security Report is attached in the Manager View in its place.
- **§14, Independence of the Security Officer; §7, Hard blinding.** Unchanged in both modes.
- **§9, Deterministic anchors, Definition of done, Dissent or missing proof; §11, Security Risk Posture, Agents section, Untrusted tasks, Hostile-input test, Run traceability, Data classes per provider.** Unchanged in both modes: the modes concern the classification of the project, not the security of how the agents work, nor the checks on the code. A refused mandatory check follows item 1 in place of Dissent or missing proof. Findings of the security and privacy reviewers other than those on the class, the personal data found and the exclusions follow §9 (item 6).
- **§5, Do**, apart from item 12. One-way doors, impact on Vision, Principles or success criteria, new suppliers, spending, changes of Decision and new access go to the Human Manager in both modes.
- **§5, Do, changes that add an external service or move data outside the organisation; §9, High Level Architectural View.** Unchanged in both modes.
- **§5, Silence never approves a Do; §11, Data classes per provider.** Unchanged in both modes: Silence never approves a Do applies to every Do that remains; with the mandate the Human Manager still decides which data go to which provider, and Deny enforces it.
- **§15, Conformance.** Unchanged: an adoption in the informative mode respects the rules of the Guide, of which the mode is one. The project record states the mode (item 13).
- **§8, Convergence.** Unchanged: the Facilitator still submits the same prompt to every executor; the question round is a step of its own, and its register goes to the User Personas, and only the selected questions reach the Human Manager.
- **§5, one-way doors and Silence never approves a Do.** Unchanged: an assumption of the question round never approves a Do.
- **§12, Three layers of documentation.** The documents it lists stay due in both modes (item 26); item 14 adds the Security Report.
- **§8, Discovery executors and reviewers.** Unchanged: the security and privacy reviewers are still present; item 6 says what the findings of the security, privacy and legal and compliance reviewers do in the informative mode.

## Reversibility

A change to the Guide text is a one-way door (GOVERNANCE §6.2). This one relaxes several rules and a context principle: for a version in force it would be a MAJOR change under VERSIONING §2.1. While the Guide is a release candidate, not in force, rolling back costs a new candidate that restores the rc.4 text of the changed lines and drops the new paragraphs. Projects that adopted the candidate keep the version they recorded; new projects would pass the gate as it stands in rc.4.

## Impact

- **Adopters.** For personal use the default becomes the informative mode: the classification asks nothing, reduces nothing and stops nothing, and the project is delivered with a Security Report. In every other case the default is the blocking mode, as in rc.4, and the Human Manager can choose the informative mode unless the organisation's rules impose the blocking one.
- **What the method promises.** Until now the levels limited risk before the project started. In the informative mode they inform. A project with health data, children's data or data of customers, a project open to the public from an adoption at level 0, a high-risk AI system and an AI system that the law prohibits can all be built and delivered with a written notice only. The notice does not replace what the law requires, and it does not make lawful what the law forbids: the Human Manager, and the organisation for its data, answer for it. "Conformant with Eiraman" no longer says that a project stayed within a qualified scope. The site and every text that presents the levels as a protection have to say so.
- **Requirements of the levels.** In the informative mode a requirement that only §14.1 sets is optional, at every level: among them, as the rule is drafted, the installation and user manual, the backup and restore test, the breach-notification procedure, the data protection officer, the contracts with suppliers that process data and the data protection impact screening. The report lists those not met. It includes the ownership of the project at level 0, corporate IT policies as a binding input of the mandate, authentication and payments through certified providers, dynamic scanning and the external penetration test, also under a formal mandate. What other rules require stays due, the deterministic anchors among them. A project in the informative mode gives no evidence for moving up.
- **Local engines.** With an external engine the limits of its provider remain. With a local engine, in the informative mode, neither the method nor the provider sets a limit; the approval of the Human Manager, with the mandate or by a Do before it, and the line in the report are the only safeguards.
- **What still reaches the Human Manager.** The informative mode removes the questions of the Security Officer, not every decision on security: the approval of the mandate with its table of data classes per provider and, where there is one, its local engine, the Do for a local engine needed before the mandate or added later, new suppliers, new access, external services and irreversible actions stay. A change of class no longer reaches them as a Do or through the drift budget, apart from the spending and time it causes; the AI Reviewer can still report it as a critical deviation (§4).
- **Where the reason holds.** The limits of external engines as the limit of law is the reason given for personal use. The informative mode can also be chosen under a formal mandate, for projects with data of colleagues or of customers; the Human Manager confirmed it (decision 14).
- **Kits with a local engine.** Where the kit gives tasks to a local engine by default, the mandate of every project in the informative mode states it, and a Discovery that uses it, the gate at the opening included, needs a Do first.
- **A fixed mode.** A personal project that later receives a formal mandate stays in the informative mode, or starts again as a new project. Rules of the organisation that impose the blocking mode do not reach the version in progress, releases included; they apply to the next version, whose gate can then stop it.
- **The report itself.** It says where each finding was found, so it can point at personal data; item 15 asks it not to reproduce them.
- **Refusals.** In both modes one refusal stops the action for every competing candidate, so an over-cautious model can block it.
- **Question round.** In both modes Discovery gains a step and a gate; the Human Manager receives, once, no more questions from it than the mandate sets, and the other answers become assumptions that can be wrong. The number is set by a mandate that is approved at the end of Discovery, so until its approval the number that the AI Coordinator communicates at the start of Discovery applies.
- **Role Profiles.** Security Officer: in the informative mode it classifies and documents in silence. AI Coordinator: it records the mode in the mandate, does not turn to another model after a refusal, delivers the Security Report with every release, states the use of a local engine in the mandate. Security, privacy and legal and compliance reviewers: their findings on the class, the personal data found and the exclusions go in the report; the declared limits of their profiles are recorded there too. Design Thinking Facilitator and User Persona template: the question round. Released separately.
- **Extended Framework and Tools.** A qualified template for the Security Report (§12, Qualified templates); the Manager View shows the mode and links the report.
- **Cost.** The question round adds a step and a gate to Discovery. The Security Officer still runs the gate at the opening of the project, at every Wave and at every change of mandate, and writes the report; the attention asked of the Human Manager for security falls to reading the report.
- **Translations.** None published yet.
- **Version.** Rules are relaxed and obligations are added. The Guide is a pre-release of 1.0.0, not in force, so the change is released as the next candidate, rc.5.

## Alternatives

- **Do nothing.** The gate keeps stopping and reducing projects as the test bench showed.
- **Make the blocking mode proportionate instead of adding a mode:** fewer questions, no reduction that changes what was asked. It would keep the exclusions for everyone. CR-022 records it as absorbed by the decision on the two modes.
- **Keep AI systems that the law prohibits excluded in both modes.** Recommended by the AI Coordinator; not chosen by the Human Manager (decision 5).
- **Keep personal data and third parties as a Do in the informative mode.** Not chosen (decision 8).
- **Informative mode by default whenever there is no formal mandate.** Not chosen (decision 9).
- **Let the AI Coordinator try another model after a refusal.** Not chosen (decision 10).
- **Let the mode change during the project.** Recommended; not chosen (decision 11).
- **A separate notification and approval for local engines.** First decided (decision 7), then replaced by the statement in the mandate (decision 13).
- **Keep the approval of the class in the informative mode.** Not chosen (decision 12).
- **Informative mode for personal use only.** Not chosen (decision 14).
- **Replace the exception of RFC 0004 with the choice of the mode.** Not chosen (decision 6).
- **Stop a project that rules of the organisation reach.** Recommended; not chosen (decision 16).
- **No local engine before the mandate.** Recommended; not chosen (decision 17).
- **Let a refusal bind only the candidate that refused.** Not chosen (decision 19).
- **Let a mandate reserve personal data in the informative mode.** Recommended; not chosen (decision 20).
- **Count a change of class in the drift budget in the informative mode.** Recommended; not chosen (decision 22).
- **Keep the requirements of level 0 due in the informative mode.** Recommended; not chosen (decision 23).
- **Count the evidence of the informative mode for moving up.** Recommended; not chosen (decision 24).
- **Make only the documents of the levels optional.** Recommended; not chosen (decision 31).
- **A separate RFC for the question round.** Recommended; not chosen (decision 40).
- **The first five proposals of the AI Coordinator on the weight of the business roles.** Replaced by the direction of the Human Manager (CR-023).

## Acceptance evidence

- `tools/release_diff.py` from `v1.0.0-rc.4` to the candidate: every removed line is an "Old" text above, or the rc.4 paragraph that item 10 extends; no heading removed.
- `TRACEABILITY.md`: all earlier rows kept; one row per new or changed paragraph, marked "RFC 0005".
- Independent scope review: every change maps to CR-022 or CR-023 and to one of their decisions.
- A run of the test bench in each mode with a kit that implements the change. Informative mode on external engines: no question or message from the Security Officer reaches the Human Manager; what reaches them is only what §4, §5, §8 and §11 keep in both modes (approval of the mandate with its data classes per provider and its local engines, one-way doors, impact on Vision, Principles or success criteria, new suppliers, spending, changes of Decision, new access, external services, irreversible actions, a local engine needed before the mandate or added later, and the other Do escalations and reviews that the Guide keeps, such as E6 calibration, K9, the critical deviations of the AI Reviewer and a refused mandatory check); a model's refusal is recorded and no other model is tried; an action the mandate forbids is still denied; the scope is not reduced, the project is delivered with a Security Report that lists what the blocking mode would have stopped. Informative mode with a local engine: no local engine runs before the Human Manager has approved it, the mandate states it and the report says that the limits of external engines do not apply. Blocking mode: the behaviour of rc.4, with a refusal recorded in the Log Tracker and in the cycle review and the output of every competing candidate for that action discarded. Question round, in a run of Discovery: no more questions from it reach the Human Manager than the mandate sets, each with the answer supposed, and the assumptions later disproved are counted; in the informative mode the questions on security reach the report and not the Human Manager.
- The Author's decision on this RFC, with written reasons, before the release Do.

## Open questions

The Human Manager decided the points of substance (decisions 1 to 44, and the question round of CR-023). What remains:

- **Wording.** The text of the items applies those decisions; its independent verification is recorded in the project plan.
- **Left to a later RFC.** At level 2 in the informative mode the error budget applies, but the service level objectives it rests on are optional. A new version of a project has no defined moment of approval, nor of approval of its class when it passes to the blocking mode. The Guide does not say where the assumptions of the question round are shown.
- **Question round not tried.** No run of the test bench has used it. With a single Persona a supposed answer can be confident and wrong; the cases of the profiles that apply it are not qualified.
- **Mandate without rules.** By decision 11, a formal mandate that reaches a project open in the informative mode leaves it in that mode.
- **Data of other people in a personal project.** By decisions 8 and 9, a professional who keeps a list of customers and uses the method for themselves works in the informative mode by default, with the data recorded in the report. It follows from the decisions; it is stated here so that it is seen.
- **Comment period.** Thirty days from opening. An earlier decision is a deviation to record, as for the earlier RFCs.
- **Community-maintained sections.** Items 1 to 6, 17 and 20 change §14 and §14.2. Accepting them now needs the same recorded deviation as the earlier RFCs.

## Decision

**Accepted**, on 2026-11-27, by the Author (Do-S29).

Written reasons: the method had become too concentrated on security and on the test bench asked many security questions, delivered reduced versions of what was requested and surfaced few needs of the work; whoever answers for a project can choose to be informed instead of stopped, and the blocking mode stays available and applies wherever the use is not personal, unless another mode is chosen and the organisation does not impose the blocking one; the question round brings to the Human Manager the questions that only they can answer. No community member is active yet; founding contributors may reopen any item with a new RFC. The written reasons were drafted by the AI Coordinator from the Author's recorded request and confirmed by the Author on 2026-11-27.

**Deviation from the comment period.** The decision was taken before the end of the comment period (2026-12-27), which `rfcs/README.md` sets at thirty days for the relaxation of level requirements. The deviation is recorded here and in the changelog; it does not change the process for later RFCs.

**Deviation for community-maintained sections.** Items 1 to 6, 17 and 20 change §14 and §14.2, which their working groups propose. The groups do not exist yet, so the Steward proposed the text and the Author accepted it, as for RFC 0001, RFC 0003 and RFC 0004. The working groups may revise it by RFC once they are formed.

**Evidence not available at acceptance.** No run of the test bench has used either mode or the question round (Acceptance evidence).

**Left open at acceptance** (Open questions): the service level objectives the error budget rests on, in the informative mode; the moment a new version and its class are approved; where the assumptions of the question round are shown.

**Implementation.** The items are applied in candidate 1.0.0-rc.5 of the Guide.
