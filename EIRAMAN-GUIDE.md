<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# The Eiraman Guide

**Version 1.0.0-rc.7 · November 2026 · Release candidate**

**Attribution.** The Eiraman Guide by Paolo Ungari and contributors.

**Status.** Release candidate, not yet in force, not measured (§15, Measuring the method). The Author ratified its editorial choices on 25 November 2026; they are listed in `AUTHOR-RATIFICATION.md`.

## 0. About this Guide

**Purpose.** This Guide defines Eiraman and states what makes an application conformant, including the practices the community keeps (§7.1, §9.1, §14). Values, templates and tools belong to the Extended Framework, the Tools and the Cases.

**Normative language.** The key words MUST, MUST NOT, SHOULD, SHOULD NOT and MAY are to be interpreted as described in RFC 2119 and RFC 8174 when, and only when, they appear in all capitals. Every normative rule of this Guide carries one of these key words. An application conforms to Eiraman only if it respects every MUST and MUST NOT. A project that departs from a SHOULD or SHOULD NOT MUST record the reason in its mandate. Text without these key words defines terms, describes how the method works or explains it.

**Values and Guidance.** This Guide describes each mechanism without its value: it states no thresholds, counts, deadlines or sizes. The project mandate MUST set the values its mechanisms need and record them. The Extended Framework publishes indicative starting values, called Guidance.

**Implementation.** Implementation choices belong to the tool that runs the method, not to this Guide. A tool MAY make them freely within the rules of this Guide.

**Community-maintained sections.** Sections so marked are kept by the working groups named in their note; the Author accepts changes to them by RFC, without rewriting them, and MAY return a proposal, with written reasons, only when it conflicts with another part of this Guide. They are as normative as the rest of the Guide.

**Licence.** This Guide is licensed under the Creative Commons Attribution-ShareAlike 4.0 International licence (CC BY-SA 4.0), <https://creativecommons.org/licenses/by-sa/4.0/>. Attribution: "The Eiraman Guide by Paolo Ungari and contributors".

## 1. Eiraman definition

**Definition.** Eiraman is a management method for governed vibe coding: AI-built software directed by a Human Manager. The human does not read the code. A business person governs the work as a manager, through a mandate, principles and delegation. A system of AI agents executes the work, checks itself through competition and independent verification, and handles operational exceptions. Every release can be reconstructed from evidence and costs.

**Planning and many models.** Eiraman replaces step-by-step human approval with planning done up front and with a multi-model mode: within the same project, several models work independently as AI Coordinator, executors and reviewers.

Eiraman has three components.

**Method.** The roles, delegation, work cycle, architectural conventions, proofs of completion and adoption levels defined in this Guide. Each project MUST record the version of the method it adopts.

**Development Environment.** The environment in which the method runs. It hosts the AI Coordinator, executions, logs and verification tools, and it enforces Deny (§5, §11). The AI Coordinator configures and runs it on behalf of the Human Manager. Calls to external services depend on the project's delegation.

**Local and external boundary.** State, logs, repository and secrets MUST stay inside the Development Environment. Only the prompts and data sent to the engines and connectors that the mandate authorises MAY leave it.

**Projects.** The applications built with the method. Their development tests the method and helps refine it (§15). An application can incorporate parts of the method.

## 2. Eiraman theory

**Why Eiraman exists.** *Human-in-the-loop* control, where a person approves each AI step, *human-on-the-loop* control, where a person monitors and steps in on exceptions, and human code review help little where there is no development team. They have two limits. Point checks multiply until approving them is like accepting a software licence: nobody reads them. And they confine AI to helping developers, instead of putting it at the service of business users. Vibe coding, building software by instructing AI in natural language, sharpens both limits. Governed vibe coding keeps its speed and adds the governance it lacks: a business person directs the work as a Human Manager, and the AI system answers with evidence. Vibe coding also sharply increases the data people handle, often without the competence needed to see the risks. In Eiraman the managerial role extends to security: a Human Manager who delegates a task knows what that choice implies for security, privacy and regulatory compliance, because the classification of the project and the Security Officer make it known (§14). When the adopter uses the method for themselves, this knowledge is, by default, information, recorded in the Security Report (§12); in work and organisational contexts it is blocking by default: the adoption levels and the Applicability gate stop what the qualified level does not allow, except what the Human Manager decides to run above it under the conditions of §14.2 (§14, Classification mode).

**Management applied to AI.** Eiraman applies traditional management to AI. Agents are governed the way a manager governs an organisation: mandate, delegation, roles and teams, planning, risk management, reviews and retrospectives. Hence the founding principle, **Human as a Manager**. Every rule transposes a known management practice, adapted to what changes when the one executing is an agent:
- *Management by objectives* becomes the mandate, the Vision and executable, measured success and stop criteria.
- *Delegation* becomes 3D escalation, decided on reversibility; silence is never consent.
- *Organisation and seniority* become AI Squads, Role Profiles, Digital Seniority and Unit Cost, staffed as a pyramid in which the base does most of the work, recomposed at every retrospective.
- *Acceptance sampling* becomes review by samples with switching rules, so that the cost of review stays small against the cost of execution.
- *Scrum and Scrum of Scrums* become one team per Work Package under an AI Scrum Master and the AI Coordinator, bounded by cost, context and quotas rather than human timeboxes.
- *Design Thinking* becomes Discovery across models, with guardrails in place of the judgement agents lack.
- *Composable architecture* becomes a fixed order of construction that prevents AI patchworks.
- *Scope and risk management* become versioned Principles and Decisions, a Risk Log and adoption levels that limit risk up front or, in the informative mode, make it known.
- *Quality control* becomes closure on evidence, independent verifiers and competition, affordable because agents do not tire.
- *Management reporting* becomes the cycle review, bad news first and a completeness check against the records, because an agent's summary can flatter.
- *Internal control and segregation of duties* become the escalation classifier on a different model (E4) and verifiers independent of executors.
- *Bills of materials and supply-chain traceability* become the software bill of materials and the run records.

**The method applies to itself.** Eiraman treats each of its rules as a hypothesis and measures its own effects against a baseline: the same tasks carried out without the method (§15, Measuring the method). It also feeds itself: it evolves by applying itself. The Human Manager gives the direction; the agents translate it, by the principles of the method, into change requests, specific choices and suggestions, and put it into practice; the Human Manager decides through Do escalations (§5). Projects feed it in the same way, through what their development teaches (§1, Projects; §15, Feedback into the method).

**Four differences between people and machines** drive every adaptation.
- *Machines lack the limits of human interaction.* Limits such as team size or Sprint length depend no longer on human capacity but on cost, context window and provider quotas.
- *Agents lack a person's contextual judgement.* They follow instructions literally and do not notice when they drift out of scope. Open activities such as brainstorming need tighter boundaries than with a human team: defined roles and behaviours, rounds, convergence criteria, permitted data.
- *Agents' time is not people's time.* An agent that repeats a task many times still finishes long before a person would. In the choices of Digital Seniority only quality and cost count (§7); time counts only for the commitments made to people, such as release dates (E5).
- *Communication between agents is not human communication.* Models trained to answer people write long messages, and every agent that receives them reads them in full. Agents MUST write to each other in the agent dialect of the profile registry; anything that a person reads MUST follow §12.

## 3. Context principles

Four principles bound every rule of the method.

- **Specialist competence lives in Role Profiles, not in every project.** Eiraman moves the competence of software professionals into qualified Role Profiles (§13), from where it guides agents across many projects. Production moves closer to those who have the need. The human operator of a project is a business user: they decide functional and economic matters and MUST NOT stand in for the AI roles on technology, applications or security.
- **Human as a Manager acts up front.** The human governs with management tools: mandate, objectives, principles, delegation, reserved matters, budget and success criteria. They work at the strategic level and, for business decisions only, at the tactical level. They MUST NOT supervise execution. Exceptions and operational autonomy belong to the AI system.
- **Context Consistency and Independence.** Agents that work on the same information and need to collaborate MUST work in a shared context, for example the developers and architects of a team. Agents whose role requires divergence or independence, such as the members of the Discovery group, testers with respect to executors, verifiers and reviewers, MUST work in independent contexts. The AI Coordinator MUST apply this principle when it forms AI Squads and Discovery groups, and throughout execution.
- **Some uses are excluded.** In the blocking mode of §14 the method MUST NOT be applied to AI systems that applicable law prohibits or classes as high-risk, nor to the other out-of-scope cases of §14. In the informative mode those cases MUST NOT stop the project and MUST be recorded in the Security Report (§12).

## 4. Accountabilities

**Human Manager.** The business person who governs the project and owns the product's direction. The Human Manager:
- MUST describe the users and the process;
- MUST approve the Vision, Principles, success criteria, mandate, spending, adoption-level upgrades and, in the blocking mode (§14), the project class;
- MUST decide Do escalations, approve the next governance cycle and accept or reject the result;
- MAY authorise linking an account or folder through the platform's native consent;
- MUST receive technical decisions translated into functions, costs, time and impact on users and data, never in technical form.

**Interpreter.** The only channel between the Human Manager and the agents, under its own qualified Role Profile. The Interpreter:
- MUST convert what the Human Manager says into the agent dialect, and what the agents send to the Human Manager into documents that follow §12;
- MUST quote verbatim the words of the Human Manager in every Decision, Do and request it converts;
- MUST NOT decide, and MUST NOT change the meaning of what it converts;
- MUST review, before they reach the Human Manager, the work of the roles one level below it and the Do records.
- MUST pass the reports of the AI Reviewer and of the Security Officer to the Human Manager unchanged, checking only their form under §12.

**AI Coordinator.** The agent that runs the project, under its own qualified Role Profile. It runs at the base of the pyramid (§7): coordination is a procedure that the Tools compute and the agent carries out. The AI Coordinator:
- MUST acquire only the authorised repository, configure engines and tools, assign credentials within the permissions granted, and check availability and budget;
- MUST prepare Waves, assign Work Packages, validate results and conformity, update the plan and run retrospectives;
- MUST manage start-up, diagnosis, suspension, resumption, release within the mandate, and restore.

**Specialist AI roles.** The analyst, architects, AI Scrum Masters, executors, testers and reviewers work under qualified Role Profiles and MUST respect their limits. They take the technical decisions. A tester MUST have access to requirements, contracts, data and expected results, and MUST make its first assessment independently of the executor's discussion.

**Process reviewer.** An independent agent that MUST run on a model different from the AI Coordinator's. It MUST sample closed Waves and check that due escalations reached the Human Manager (§5) and that closures are backed by evidence (§9).

**AI Reviewer.** The AI Reviewer extends the process reviewer from sampling closed Waves to monitoring the whole project, under its own qualified Role Profile. The AI Coordinator MUST start it before the phase it watches; it MUST run at the events of the project and on the samples that the Extended Framework suggests, and under hard blinding (§7). It SHOULD run on a model different from the AI Coordinator's where one is available; the checks of the process reviewer keep the different model they require. It MUST monitor the framework KPIs, such as the correctness of the Role Profiles assigned to AI Squads and the measured quality of outputs, and the project KPIs set in Design and planning. It MUST report deviations to the AI Coordinator, each with an independent suggestion; the AI Coordinator MUST evaluate them critically and answer. Critical deviations, and deviations the AI Coordinator does not accept, MUST also go to the Human Manager in the Manager View.

**Suggestions of the AI Reviewer.** The AI Reviewer's suggestions are data, not commands. Agents MUST evaluate them critically, and a suggestion MUST NOT be executed without the AI Coordinator.

**Maintainers.** The maintainers of the Extended Framework, organised in working groups under the project governance, MUST qualify Role Profiles, document templates and the gate checklist. They MUST work outside the projects that use them.

**Internal accountability.** Everyone MUST answer for what they decide. The Human Manager answers for decisions within their remit and for using the method within the qualified scope in the blocking mode or, in the informative mode (§14), for proceeding with what the Security Report records. The AI Coordinator and the AI roles answer in an operational sense, not a legal one: every closure MUST have evidence and every error MUST become a retrospective case. Maintainers answer for the conformity of profiles to their sources at the time of qualification, not for individual projects.

**Liability towards third parties** lies with the owner: the individual at adoption level 0, the organisation at levels 1 and 2. At levels 1 and 2 the Human Manager MUST act under a formal mandate from the organisation; without it the project stays at level 0. For a project that runs above the qualified level under a mandate of the organisation (§14.2), liability towards third parties lies with that organisation. In the informative mode (§14) the Human Manager answers for proceeding with what the Security Report records; liability towards third parties for the data of which an organisation is the controller lies with that organisation; the method does not move obligations that the law places on an organisation or on anyone else; in the informative mode the owner exercises this responsibility through mandate and acceptance. The owner exercises this responsibility through mandate, class and acceptance, and demonstrates due diligence with the evidence the method produces (§12).

## 5. 3D escalation: Deny, Delegate, Do

**Deny.** The environment, not the agent, MUST block an action that the mandate forbids or, in the blocking mode (§14), that lies outside the adoption level, and MUST record why. For a project admitted under §14.2 (Running above the qualified level), class 1 takes the place of the adoption level, unless a requirement of level 1 that the paragraph makes due is due and not met; while work goes on only on test data under Questions for the organisation (§14), with or without the decision of §14.2, the environment MUST also block any data other than test data, masked data included, and every release. The AI Coordinator MUST look for an authorised alternative; if there is none, it MUST suspend the affected work.

**Delegate.** AI roles MAY decide two-way doors on their own: reversible decisions with a known cost, within budget, such as engine, retry, fix or restore. Every such choice MUST stay linked to its Work Package.

**Do.** The following MUST go to the Human Manager:
- one-way doors;
- the mandate's reserved matters: impact on Vision, Principles or success criteria, personal data, third parties, new suppliers, spending above the threshold the mandate sets; in the informative mode (§14) personal data and third parties MUST be recorded in the Security Report and MUST NOT go to the Human Manager as a Do on that ground alone, even where the mandate reserves them; the other items of this list still apply;
- changes to a Decision;
- new access;
- changes that add an external service or move data outside the organisation (§9);
- changes of project class, adoption-level upgrades and the decision to run a project above the qualified level. Downgrades are automatic (§14.2). In the informative mode a change of class MUST be recorded in the Security Report and MUST NOT go to the Human Manager as a Do on that ground alone; the other items of this list still apply.

**In doubt, one-way.** When reversibility is in doubt, the decision MUST be treated as a one-way door.

**Content of a Do.** A Do MUST present, in functional and economic terms, the impact, the options, a recommendation, the evidence, a deadline and what happens if there is no answer.

**Changing a Decision.** A Do that changes a Decision MUST include a SWOT analysis. After the choice, execution returns to the AI Coordinator.

**Rules against under-escalation.**
- **E1 · Reserved matters.** The mandate MUST list reserved matters alongside delegation. What reaches the Human Manager MUST be the business impact of the reserved matter, translated into functions, costs, time and impact on users and data; the technical choice stays with the AI roles. Reserved matters prevail over K7 (§6).
- **E2 · Reversibility.** Reversibility MUST be the criterion that separates Delegate from Do.
- **E3 · Micro-decisions.** Every non-trivial choice MUST be recorded as a micro-decision, with the alternative, the estimated reversibility, the cost of rollback and the reserved matters considered.
- **E4 · Classifier.** Whether a decision goes to the Human Manager MUST be decided by a classifier running on a model different from the AI Coordinator's. If the two disagree, the decision MUST go up.
- **E5 · Drift budget.** Deviations from plan, class changes included, MUST add up in a drift budget cumulated over the project, expressed in spending and in time, and reported every governance cycle. Class changes MUST also be reported as an item of their own. Beyond the threshold the mandate sets, a mandate review MUST be triggered. In the informative mode (§14) a change of class MUST NOT count towards the drift budget or be reported as an item of its own: it MUST be recorded in the Security Report; the spending and time of the work it causes MUST count as any other deviation from plan.
- **E6 · Measurement.** The process reviewer MUST measure under-escalation (reserved decisions not brought to the Human Manager, over all reserved decisions) and over-escalation (Do escalations that fell within delegation, over all Do escalations). Both measures are estimates over a sample of micro-decisions (E3) and Do escalations. They MUST be reported with the number of decisions examined and with their confidence interval. A threshold is met only if the unfavourable bound of the interval stays within it.
- **E6 · Calibration.** In the first project of every new adoption, the Human Manager MUST review once a sample of autonomous decisions, to calibrate the process reviewer. The mandate sets the sample size.

**Silence never approves a Do.** Silence MUST NOT be taken as approval. Until there is an answer, the affected Work Package MUST stay suspended, while independent work continues. At the deadline the Human Manager MUST receive a reminder. When the reminder's deadline also passes, the package MUST leave the Wave and the cycle review MUST report it as a missing decision. The irreversible option MUST NOT be executed without an answer.

**Urgent containment.** The mandate MUST list pre-authorised, reversible containment actions, such as restore, credential revocation or suspending a function. The AI Coordinator MUST execute them at once and open an urgent Do. Any action not on the list MUST follow the ordinary Do rule. The mandate sets the deadlines for ordinary and urgent Do escalations.

## 6. Competition and independent verification

**Rationale.** Agents have no group harmony to preserve, so competition between candidates is sustainable when the cost justifies it. This is why the roles of controller and project manager can be given to AI.

**Generate and select.** The benefit of competition comes from generating several candidates and selecting the best, not from agents trying harder. It depends on the diversity of the candidates and on the reliability of the selector.

**Rules for competitive mechanisms.**
- **K1 · Reliable selector.** A competitive mechanism MUST be opened only with a reliable selector: tests, measurable criteria, or a rubric fixed in advance and assessed by a judge running on a model different from the competitors', with the order of candidates alternated. All candidates MUST start from the same point.
- **K2 · Diversity.** The diversity of the candidates (model, supplier or strategy) MUST be recorded.
- **K3 · Number of candidates.** The mandate MUST set the default number of candidates. Several candidates SHOULD be reserved for highly variable generative packages or for packages where errors are costly, and they MUST stay within the spending cap.
- **K4 · Learn from the losers.** After selection, the criticism raised by the losing candidates MUST be applied to the winner, through the reviewer.
- **K5 · Hidden criteria.** Part of the evaluation criteria MUST NOT be shown to the candidates, and judges MUST rotate.
- **K6 · Measure the mechanism.** The winning margin, judge–human agreement (calibrated on a sample of human judgements of candidates) and cost per accepted increment against a single executor MUST be measured. If the mechanism does not beat a single executor on a type of package, that type MUST return to a single executor. The mandate MUST set what counts as a type of package, the minimum number of packages and the minimum margin over a single executor.
- **K7 · Lowest rollback cost.** With strongly diverging proposals on a two-way door, the option with the lowest rollback cost MUST be adopted. If the budget allows, a short test that discriminates between the options MUST be run first.
- **K8 · High divergence.** Such cases MUST be flagged as high divergence. The process reviewer MUST examine all of them and give them priority in the calibration sample (E6).
- **K9 · Recurring divergence.** If divergence recurs on the same theme, the AI Coordinator MUST propose a mandate review as a Do, translated into functions, costs, time and impact on users and data. If the theme cannot be put in those terms, it stays with the AI roles under K7 and K8.

**Independence of verification.** For each verification the level of independence achieved MUST be recorded: separate context, different model, different supplier, or a person. Each verification MUST reach at least the minimum level that the risk class of the Work Package sets. Verification SHOULD use models of different origin where possible, so that comparisons are effective.

**Security and personal data.** At every adoption level, verification of Work Packages that touch security or personal data SHOULD use at least a model different from the executor's. The level of independence achieved MUST be recorded in every case.

**Seniority of the verifier.** An independent reviewer or tester MUST work one Digital Seniority level above the executor it verifies (§7). The work of the highest level in use MUST be verified by the Human Manager or by a model of a different provider.

**Review by samples.** An oracle (tests, deterministic checks or a rubric fixed in advance) MUST run before any review by a model. Review on a model different from the executor's MUST cover every Work Package of the risk class (architecture, security, personal data, effects hard to undo); for the others it MAY cover a sample. The share sampled MUST follow switching rules set in the Extended Framework: tightened after rejected samples, reduced after a run of accepted ones. The cost of review MUST be recorded apart from the cost of execution.

## 7. AI Squads and Digital Seniority

**Role tiers.** AI roles are organised in a pyramid. The base does most of the work; going up, the number of agents, the volume of work and the cost per run fall. Each role MUST start from a qualified Role Profile; the project mandate MAY give it the project and domain context but MUST NOT alter the profile's rules and limits.
- *Top:* the Interpreter, the only role in contact with people (§4).
- *Upper:* the roles of Discovery that interpret people's needs, such as the business analyst and the User Personas.
- *Middle:* the roles of planning and design, such as the functional analyst, the experience designers and the architects.
- *Base:* every other role, the AI Coordinator, AI Scrum Masters, executors and testers included.
- *Reviewers* work one level above the roles they verify (§6).

**Unit Cost.** AI is not free. Every Role Profile MUST declare a Unit Cost, used to estimate and report the project's cost, review included.

**Digital Seniority.** In an organisation every person works at the level of experience the task requires; Eiraman applies the same rule to agents. An agent's Digital Seniority is the combination of engine and reasoning level with which the AI Coordinator activates it, for example a small engine with low reasoning for repetitive work.

| SD level | Name | When it is used |
|---|---|---|
| SD1 | Junior | The base: execution, testing and coordination on a bounded input received from an agent |
| SD2 | Professional | Planning and design; review of SD1 work |
| SD3 | Senior | Discovery roles that interpret people's needs; review of SD2 work |
| SD4 | Lead | The Interpreter; review of SD3 work and of Do records |
| SD5 | Principal | New problems that SD4 has not solved, only after a Do with a stated budget |

The mapping from SD levels to the engines and tool settings of each provider is not part of this Guide. It is kept, versioned, in the Tools.

**Agentic Scrum.** Agents work by Scrum principles, adapted to collaboration between AIs.
- **No Sprints or human timeboxes.** The unit of delivery MUST be the Wave, bounded by tokens, cost and duration (§8). Team size has no fixed limit; it depends on the AI environments used.
- **One team per Work Package.** The AI Coordinator MUST form one team for each Work Package, with the roles and competences the package needs.
- **A new agent for every Work Package.** The AI Coordinator MUST instantiate a new agent of the required role, with a new context, for each Work Package. At closing, each agent MUST provide a Work Package handover abstract: the significant information of its context that the next agents need. The AI Coordinator uses it to instantiate the agents of the following Work Packages.
- **One AI Scrum Master per team.** It MUST coordinate the team's agents, keep the Log Tracker of the package and deliver to the AI Coordinator an activity report on the template the AI Coordinator specifies.
- **Shared context, except for the unit tester.** Within a Work Package, a team shares one context. The unit tester MUST NOT receive the team's discussion, so as not to bias the tests; it receives requirements, contracts, data and expected results. It MAY run on a different engine, or on the same engine without that context; for security and personal data, §6 applies.
- **Competing teams.** The same Work Package MAY be assigned to several competing teams, with different engines or compositions, under rules K1–K9 and with the default number of candidates of K3.

**Agent blinding.** Blinding keeps each agent within the information of its role, so that roles do not overlap. Blinding concerns project information, not the general knowledge of the model.

**Hard blinding.** Under hard blinding, the environment MUST give the agent only the files, tools and data of its role, with no retrieval outside that perimeter (§11), and a binding prompt MUST constrain its behaviour. A local model without retrieval MAY be used. Hard blinding MUST apply to the AI Coordinator, the AI Reviewer, the Design Thinking Facilitator, the Discovery reviewers, the Discovery judge (§8) and the Security Officer (§14).

**Soft blinding.** When it forms an AI Squad, the AI Coordinator MUST hand each agent a context RACI, which states the agent's position on each part of the context:
- *R:* the only agent entitled to act on that part of the context;
- *C:* the agent MAY use its own competence on the subject but MUST NOT contradict the project instructions or other agents;
- *I:* the agent is blind on the subject.

**The AI Coordinator as Scrum of Scrums.** Beyond what a Scrum Master does, the AI Coordinator MUST perform technical and compliance validation of the teams' work: it sets the quality and functional criteria a package has to meet, verifies execution at the end of each package (§9), resolves dependencies between teams, and closes a Wave only after the integrated increment has been verified.

**Retrospective.** At the end of each cycle the AI Coordinator MUST analyse the Scrum Masters' reports. It optimises the composition of the teams, for example by raising a role's seniority or changing its model among those that its Role Profile enables and the mandate admits, and reviews operational decisions, that is the micro-decisions (E3) that touch neither approved Decisions nor reserved matters.

**Tolerance.** Improvements that save cost without reducing quality, or that reduce it within the mandate's tolerance, MAY be applied without the Human Manager. Any change to an approved Decision MUST go to the Human Manager as a Do with a SWOT analysis (§5).

**Flexible Decisions.** Re-forming AI Squads costs little, so approved Decisions can change more readily than with human teams. The cost of change and rework MUST be estimated and shown in the Do.

### 7.1 Digital Seniority catalogue

> **Community-maintained section.** Changes are proposed by the responsible working groups (DevSecOps & Tooling, for the Digital Seniority map; FinOps, for Unit Cost; Test & Quality, for requalification after model changes) and accepted by the Author via RFC without rewriting; the Author MAY return a proposal, with written reasons, only for a conflict with another part of this Guide.

**Catalogue.** Every Role Profile MUST declare the SD level of its role and list the tasks and deliverables the AI Coordinator can assign to it. For each task it MUST state the type of task (procedure, experience or novel problem), whether an oracle verifies it (a deterministic check, tests or a rubric fixed in advance), and whether it belongs to the risk class (architecture, security, personal data, effects hard to undo). The correspondence between SD levels and the configurations of each admitted tool, engine and reasoning level, local engines included, MUST be kept in a single map of the profile registry and re-verified at every model change. The map MUST also define the ladder of promotion: steps of higher reasoning on the same engine and steps to a more capable engine. The correspondence is an assessment by the maintainers of the map; configurations not yet tested are marked as such.

**Fallback.** A task outside the catalogue MUST run at the level of the role that performs it. The AI Coordinator MUST record the task, propose adding it to the catalogue (§15) and report in the cycle review the share of tasks run outside the catalogue.

**Team participation.** The Role Profile is the role; the SD level is the grade of a single run. Each run MUST be activated at the level of its role, or at the step that promotion gives, and recorded. An agent MUST NOT run at a higher level for the sole reason that another task of the Work Package needs it.

**Promotion and reduction.** Promotion MUST be a rare exception, because review must stay cheap against execution. A failure for lack of capability is an oracle that fails, a review that rejects for lack of capability, or, where there is no oracle, disagreement between two independent runs. The reviewer MUST record the cause of each failure: *input* (an incomplete or ambiguous work order), *environment*, *refusal* by the model, *depth* (steps skipped, edge cases missed) or *capability or knowledge*. The AI Coordinator MUST then act in this order:
- for input or environment, fix them and repeat the run at the same step; for a refusal, apply §14; none of these is a failure for lack of capability;
- for depth, take the next step of higher reasoning on the same engine;
- where an oracle exists, repeat the run at the same step while the cost of the repeats stays below the cost of one run at the next engine;
- only then, and only for a failure of capability or knowledge confirmed by two failures of different kinds, move to a more capable engine; a failure in the risk class moves to a more capable engine at once.

Model promotions MUST NOT exceed the share of runs per cycle that the mandate sets. Promotion uses the attempts allowed by the Work Package record (§9); when they are exhausted, the AI Coordinator MUST open a decision point. In the retrospective the AI Coordinator MAY lower the level of a task when evidence shows unchanged quality at lower cost, that is no increase in defects found after closure or in rework. That reduction is a two-way door within the mandate's tolerance; beyond it, it is a Do.

**Cost per level.** Unit Cost MUST be calibrated per SD level, and every run MUST record the effective level, engine and reasoning (§11). The cost of a local engine MUST also be recorded in machine hours.

**Cost of errors.** For each type of task and SD level, the AI Coordinator MUST measure every governance cycle the cost of errors in tokens: the tokens spent on runs that did not lead to an accepted increment (rejected or repeated runs, reviews of rejected work, promotions and rework after closure), as a share of all the tokens of that type of task. Rework after closure MUST also be reported on its own. The indicator MUST be reported in the cycle review.

**Raising the level of a role.** When the cost of errors in tokens of a role exceeds the threshold that the mandate sets, and the cause recorded is not the input, the AI Coordinator MAY raise the level of that role by one step on its own, as a two-way door (§5, Delegate). It MUST then inform the Human Manager in the Manager View with the indicator, the old and new level and the expected cost. A raised level MAY be lowered again under «Promotion and reduction».

## 8. Lifecycle and events

**Five phases, one set of rules.** All five phases MUST be executed by the AI system in Waves, under the same rules: 3D escalation, competition, closure on evidence and cost recording. The Human Manager steps in only at each phase's decision points.

**Phases and decisions.** Each phase MUST end with the decisions of the Human Manager listed below; work that needs them MUST NOT proceed without them.
- *Discovery* yields the problem, benefit, discarded alternatives, a draft Vision, the first draft of Scope Management and the class set by the applicability gate (§14). The Human Manager approves Vision, mandate and, in the blocking mode (§14), class, or relaunches exploration.
- *Proof of concept* runs a repeatable feasibility test and identifies the resources and access needed. It becomes a Do only if the outcome is negative or needs new access or spending.
- *Design and planning* yields the architectural views, contracts, backlog, Work Packages, profiles, cost estimate, test criteria and proposed Principles and Decisions, refined from the first draft of Scope Management. The Human Manager approves the proposed Principles, the proposed Decisions with business impact and the budget. The Principles are then frozen for that version.
- *Scale* delivers increments closed on evidence. The Human Manager acts through the governance cycle and Do escalations.
- *Acceptance and operation* covers acceptance testing, release, manuals and service management. The Human Manager accepts or rejects the result and decides Do escalations on operations.

**Parallelism.** In every phase the degree of parallelism MUST stay within capacity and budget.

**Discovery as Design Thinking between models.** Left free, AI engines gather information well but tend to diverge, so Discovery follows Design Thinking with precise roles and boundaries.

**Discovery at every start.** Discovery MUST run at the start of every project and MUST be tracked in the activity tree of the plan. Its deliverable is the first draft of Scope Management: Vision, Principles, Decisions, success criteria and open points.

**Discovery group.** For Discovery the AI Coordinator MUST form a Discovery group, which is not an AI Squad: each of its members MUST work in an independent context. The group MUST include at least the Design Thinking Facilitator, the functional analyst, the Business Analyst, the UX-UI designer, the User Personas and, where the project has them, the platform and technology architects (§8.1).

**Business Analyst and User Personas.** The Business Analyst and the User Personas are project instances of qualifiable templates. Each MUST start from a qualified template, as a high-tier role starts from a qualified Role Profile (§7); the project gives the instance its project and domain context, which MUST NOT alter the template's rules and limits.

**Discovery executors and reviewers.** The Discovery group has executors and reviewers. Executors MUST work under soft blinding and bring interdisciplinary competence. Reviewers MUST work under hard blinding and MUST judge only the Principles and Decisions within their own domain. The Discovery reviewers are the reviewer profiles of the governance domains that the project touches, chosen by the AI Coordinator; the security and privacy domains MUST always be present.

**Question round.** Before divergence, the Design Thinking Facilitator MUST submit the same prompt to every executor of the group, asking what is not known and who should be asked. It MUST merge the questions into a question register, keeping their words, topic, author and addressee and whether a choice that is not reversible depends on them, and removing only duplicates. It MUST then submit the register, without the authors, to the User Personas, which MUST give for each question an answer, its source and a confidence level. The level MUST follow the source: high only when the answer is written in the request or in the materials of the Human Manager and the quotation answers that question, medium when it is deduced from what is written, low when it is supposed. When several User Personas give different answers or confidence levels to a question, the lowest confidence level MUST count; when that question reaches the Human Manager, the different answers MUST reach them with it, and otherwise they MUST all be recorded among the assumptions. Among the questions addressed to the Human Manager or to a person outside the Discovery group that are not at high confidence, the Facilitator MUST send to the Human Manager, through the AI Coordinator, those at the lowest confidence, up to the number that the mandate sets, each with the answer supposed; until the mandate is approved, the number that the AI Coordinator communicates with the gates at the start of Discovery MUST apply; at equal confidence, first those on which a choice that is not reversible depends, then those whose topic changes what the end user sees or does, then in the order of the question register. Technical questions and questions for a member of the group MUST NOT take one of these places. The answers not asked MUST be taken as correct and recorded as assumptions visible to the Human Manager. Without an answer by the gate, Discovery MUST continue and the suppositions MUST remain unconfirmed assumptions. In the informative mode (§14), questions on security MUST NOT take one of these places or be recorded among those assumptions: the Security Officer MUST record them in the Security Report as not determined. The question round MUST NOT count toward the maximum number of rounds.

**Divergence.** Several models, with defined roles and behaviours, independently generate hypotheses, problems, benefits and principles for the Vision. Divergence MUST run within guardrails: a maximum number of rounds set by the mandate, permitted sources and data, and criteria for discarding a hypothesis.

**Gates.** At the gates that the AI Coordinator sets and communicates at the start of Discovery, the Human Manager MAY give new inputs, which start a new round of divergence. One gate MUST follow the question round and precede divergence; it MUST carry the questions of that round.

**Convergence.** The Design Thinking Facilitator MUST lead convergence; the functional analyst takes part as a member of the group. The Facilitator MUST submit the same prompt to every executor of the group, record the answers, restate them as Principles, Decisions and open points, and iterate until consensus within the maximum number of rounds that the mandate sets; it MUST then submit the result to the Discovery reviewers. Convergence MUST gather the contributions, relate them to user evidence and produce the draft Vision and the first draft of Scope Management. The Human Manager MUST then approve the Vision or relaunch the exploration. Convergence follows K1 (§6): the convergence criteria MUST be fixed before divergence, and, after the Discovery reviewers, the result MUST be assessed against them by a judge that runs on a model different from those of the members of the group, before the result reaches the Human Manager. The judge MUST be an agent distinct from the Discovery reviewers and MUST work under hard blinding (§7). When no model different from those of all the members of the group is available, the AI Coordinator MUST bring the choice of the judge's model to the Human Manager as a Do, presented in functional and economic terms (§5, Content of a Do); the judge then runs on the model the Human Manager chooses, and the level of independence achieved is recorded (§6).

**Discovery report.** At the end of Discovery the Design Thinking Facilitator MUST produce a report for the Human Manager with the initial and the final position of each AI of the group.

**Design and planning as a Work Package.** Design and planning MUST run as a dedicated Work Package, which the AI Coordinator assigns and MUST NOT perform. It refines the Principles and Decisions of the first draft of Scope Management and produces the first Product Backlog and the architectural documents.

**Wave.** The unit of technical delivery in every phase, at the pace of the AI. A Wave MUST have a spending cap and a maximum duration; whichever is reached first applies. At the early-warning threshold that the mandate sets, the AI Coordinator MUST flag the Wave. At the Deny threshold that the mandate sets, the environment MUST Deny new work, and the Wave closes with a checkpoint. Waves follow one another automatically within mandate and budget. A Wave MUST close only after the integrated increment is verified.

**Governance cycle.** The Human Manager's unit of decision, on a calendar cadence. It MUST close with a single management review that contains: deliveries and acceptances; spending and cost per accepted increment; the governance share, that is the cost of the AI Coordinator, the AI Scrum Masters, the reviewers, the escalation classifier (E4), the judges (K1), the applicability gate (§14) and the drafting of managerial documents (§12), over the total cost of the cycle; the share of tasks run outside the catalogue (§7.1); the state of the drift budget (E5); the number of high-divergence cases (K8) and the recurring themes (K9); open Do escalations; and a proposal for the next cycle.

**Expired cycle.** If a cycle expires before the next one is approved, running Waves finish the active Work Package and MUST NOT open new ones.

**Escalation load.** An indicator of the governance cycle, read together with under-escalation. It MUST NOT block a due Do. Ordinary Do escalations and K9 escalations count toward it; urgent Do escalations, counted separately, and decisions planned by the phases do not. Non-urgent Do escalations MUST be grouped in the cycle review, except those that block the critical path.

**Declared and observed values.** The cycle review MUST show the declared value of the cycle's indicators next to the observed one. A declared value MUST NOT change except at a cycle review. The mandate sets cadence and reference values.

### 8.1 Phase playbooks

The playbooks describe how the AI system usually works; the rules are those of §8.

**Who works in each phase.**
- *Discovery:* the Discovery group that the AI Coordinator forms, its members on different models; divergence, then convergence led by the Design Thinking Facilitator.
- *Proof of concept:* the AI Coordinator, analyst, architect, executors and testers, who make the uncertainty explicit; alternative tests of the same technical question when the selector is measurable (K1).
- *Design and planning:* the team of a dedicated Work Package, with the analyst, application and infrastructure architects and AI Scrum Master, who produce business, application, data and technology views; alternative architectures assessed against a rubric fixed in advance.
- *Scale:* the AI Coordinator and AI teams with their AI Scrum Masters, testers and reviewers; K1–K9 on generative packages.
- *Acceptance and operation:* the AI Coordinator, testers and operations roles; alternative diagnoses of an incident.

**Roles in the Discovery group.**
- *Design Thinking Facilitator:* runs the Discovery procedure and leads convergence.
- *Functional analyst:* links the needs of the Business Analyst and the User Personas to the solutions of the UX-UI designer and the architects.
- *Business Analyst:* holds the Vision and, where applicable, brings the expertise of the industry.
- *UX-UI designer:* proposes the solutions for the experience and the interface of the users.
- *User Personas:* stand for the users of the application; give a first, supposed answer to the questions of the question round, which stays an assumption until the Human Manager answers; later they run the simulated-user functional tests (§9.1).
- *Platform and technology architects,* where present: propose the technical solutions.

**Discovery procedure.** The Design Thinking Facilitator works in rounds:
- *Questions.* Once, before the first round, it runs the question round (§8, Question round).
- *Same prompt.* It submits the same prompt to all the executors of the group, each in its own context.
- *Record.* It records the answers.
- *Reconcile.* It checks whether the answers reconcile fully or partially.
- *Restate.* It issues a new prompt that states the Principles, cornerstones everyone agrees on, which Design and planning refines and which freeze at the end of planning; the Decisions, which can change on new specifications or evidence; and the open points, deferred to design, to a mock-up (MOC) or to a proof of concept (POC), or needing a Do of the Human Manager.
- *Iterate.* It repeats the rounds until consensus, within the maximum number of rounds that the mandate sets.
- *Review.* It submits the result to the Discovery reviewers, each of whom judges only its own domain.
- *Judge.* The K1 judge assesses the result against the convergence criteria fixed before divergence.
- *Report.* It writes the report for the Human Manager, with the initial and the final position of each AI.

**Proof of concept and MVP.** The functional analyst validates feasibility, in theory or by asking the AI Coordinator for small trial Work Packages. It also validates the compute and access the project needs, for example whether a local engine can process a document of the expected size within the expected time and cost.

**Design and planning.** The functional analyst works first with the application architect, then with the infrastructure architects and the AI Scrum Master. Together they produce the architectural design, the Product Backlog and its workstreams, the cost estimate of the AI component, and an initial performance estimate that tests later update in the Performance Analysis. The design follows the architectural guidelines of the vendors or open-source communities of the chosen technologies, and the architects carry these competences in their profiles.

## 9. Commitments and artifacts

**Two results, accepted separately.** Acceptance of the software and acceptance of the deliverable the software produces MUST remain separate. For example, when an increment adds a quality check to a document generator, a document the check rejects can be the successful proof of the increment, while generated documents go through their own review.

**Vision.** The Vision becomes binding when the mandate is approved. A change to the Vision MUST open a new project.

**Principles.** Principles MUST be frozen per version at the end of planning. If a Principle changes during installation, the AI Coordinator MUST mark the version as failed, record the installed state and manage the restore or the transition to a new version.

**Success criteria.** The success criteria of a version and of the project MUST be based on KPIs measurable in the test procedures.

**Decisions.** A Decision MUST NOT violate a Principle. Decisions are linked: changing one can require re-examining the linked ones.

**Decision record.** Each Decision MUST have an identifier, owner, status, rationale, linked Principles and dependencies. A new Decision MUST refer to the one it replaces and to the packages to re-examine. A saving that changes a Decision MUST go to the Human Manager, even when it is within the quality tolerance.

**Open points.** Each open point MUST state which Wave it blocks and the criterion for closing it.

**Stop criteria.** The mandate MUST contain the project's stop criteria, such as spending, a run of Waves without an accepted increment, or a negative proof of concept.

**Product Backlog.** The Product Backlog holds the workstreams the teams can carry out. Each workstream MUST be labelled with its component and priority (§10) and linked to the Decisions and open points it depends on.

**Work Package record.** A Work Package record MUST hold at least: project and Wave, identifier and starting revision; success criteria and exclusions; Principles, Decisions and dependencies; profiles and their versions; budget and attempts allowed; expected result and verifier; resumption procedure; the context RACI handed to its agents; and, at closing, the Work Package handover abstract of each agent.

**Final account.** The final account of a Work Package MUST include all candidates, the discarded ones too.

**Definition of ready.** Functional criteria MUST be written in Given/When/Then form. Non-functional criteria MUST refer to the characteristics of ISO/IEC 25010. A Work Package MUST NOT be declared ready until its criteria are executable.

**Definition of done.** The AI Coordinator MUST close a Work Package only when the mandatory checks on the identified candidate have passed and the evidence is identifiable. A change to the candidate MUST reopen the affected checks.

**Dissent or missing proof.** The package MUST stay open. With a clear requirement, the test MUST be repeated or another verifier assigned. With an ambiguous requirement, a decision point MUST be opened. Outcome, dissent and the rationale for closure MUST be recorded.

**Deterministic anchors.** At every release, static analysis, dependency and licence analysis, and secret scanning MUST be run. AI roles interpret their results and MUST NOT replace them.

**Log Tracker.** The general log of all activities, used by the AI Coordinator to follow progress and as the basis of the completeness check (§12). It is not designed for people.

**Risk Log.** The risks of failure of the project and how they are managed. Business risks go to the Human Manager; the detail stays operational.

**High Level Architectural View.** A concise view with a drawing, within the length limit the mandate sets, in non-specialist terms and derived from the architecture document: points of contact with people; where data lives and its data classes; external services and AI engines, local ones distinguished from external; the main flows and boundaries, that is what leaves the organisation and who can access it. The AI Coordinator MUST update it whenever a part is created, changes or disappears. A change that adds an external service or moves data outside the organisation MUST go to the Human Manager as a Do (§5).

**Shape of control artifacts.** Each project and each Human Manager decide the shape of the dashboards, views and documents they use for control, and MUST record the choice as a project decision. The minimum content required by this Guide and, in the blocking mode (§14), by the adoption level MUST NOT be reduced; in the informative mode the content that only §14.1 requires MAY be left out and MUST be listed in the Security Report, and the documents that §12 lists MUST be kept as in the blocking mode.

**Manager View.** The tool through which the Human Manager reads the progress dashboard, the Do records and the findings addressed to them.

**Project record.** The project record MUST identify: the application, its users, deliverables, repository and revision; the Eiraman version used, the class, the adoption level and the classification mode; the Eiraman components built into the product, and any adaptations; and the success criteria.

**Two links.** The AI Coordinator MUST keep two separate links: between a Work Package and the software release, and between a run of the product and the deliverable it generated. For each adopted Eiraman component, where it runs and which version is in use MUST be recorded.

### 9.1 Test practices

> **Community-maintained section.** Changes are proposed by the responsible working groups (Test & Quality; DevSecOps & Tooling; Security, for security testing) and accepted by the Author via RFC without rewriting; the Author MAY return a proposal, with written reasons, only for a conflict with another part of this Guide.

**Test levels.** Component, integration, system and acceptance. Unit tests are component tests; scripted and simulated-user functional tests are integration and system tests; acceptance testing is the acceptance level. Security and performance testing is proportionate to the risk.

**DevSecOps practices.** Work follows DevSecOps practices where they apply: a Git history of the application and its versions, with messages written to be read by people too; Security by Design, with static analysis and, at level 2, penetration testing (§14.1); and heavily automated tests run by dedicated agents.

**Test types.**
- *Unit tests* run at the end of each Work Package and are performed by the independent AI tester. They also check the security and performance components, and they update the Security Risk Posture and the Performance Analysis.
- *Scripted functional tests:* an agent runs the test script, records the logs and checks completion or failure. The test agent MUST NOT fix on its own either the candidate or its own test script: it MUST report every error to the AI Coordinator, which assigns the fix; for the test agent this limits the autonomy of Delegate (§5). Fixing the test script is a task of its own, assigned and recorded by the AI Coordinator; the same test agent MAY receive it. Every fix reopens the affected checks (§9).
- *Simulated-user functional tests:* the User Personas of the project, as simulated end users, use the application as a person would. They cost more, so they run in stable environments.
- *Acceptance testing:* a person performs the business task while the AI assists, recording observations and missing information. The Human Manager decides on acceptance.

**Who supervises tests.** The person MAY watch functional tests, but their progress MUST NOT depend on the person. Acceptance testing is supervised by the AI: the person executes and the AI records.

## 10. Composable architecture

**Order of construction.** An application is broken down into components tied to functions, developed independently in Work Packages. With AI the key point is the order of construction: adding pieces is easy, and without a catalogue and an order the result is a patchwork. Components MUST be built in the priority below.

**Backbone.** The core components needed for the core deliverable. The Backbone has the highest priority. The first usable path MUST run through it in minimal form, together with the Brain and the essential interfaces. The Backbone MUST then be completed over all the main paths of the core deliverable before the other components are extended.

**Brain.** The application's logic, more and more often made of internal or external AI engines. Brain tasks MUST be catalogued as trusted or untrusted. The catalogue decides which tasks are delegated to engines and which stay under deterministic control or require a Do (§11). The mandate MUST set the criteria by which a Brain task is trusted or untrusted, and the role that applies them.

**Limbs and Senses.** The interfaces through which the application communicates with users and other systems. They rest on Backbone and Brain. They MUST be developed early in essential form, within the first usable path, and in advanced form only once the previous components are stable.

**Hairs.** The most peripheral functions, which can be added or cut at any time, even for small specific tasks. They come last in priority. Before a Hair is removed, the core MUST pass regression.

**Component contract.** Each component MUST declare its contract, data, dependencies and integration test and, if it is peripheral, a check of behaviour when it is removed. The first usable path runs through Backbone and Brain and includes the essential interfaces (see Backbone).

## 11. Environment, execution and agent security

**Project opening.** The AI Coordinator MUST resolve the versions of method and profiles, check the repository and available capabilities, configure runners and connectors, and test the authorisations needed. Access that requires the account holder MUST go through a narrowly scoped request to that holder. The environment MUST enforce tool constraints and keep secrets in the platform's credential store.

**Executions.** Each execution MUST have an identifier, persisted state, input version, checkpoint, budget and attempt limit.

**Resumption.** After an interruption, the AI Coordinator MUST reconcile the state with the effects already produced before restarting. If the AI Coordinator is unavailable, the runtime MUST preserve the work and prevent new uncontrolled operations. On restart, the AI Coordinator MUST check the last delivery, then resume or restore the previous version.

**Security Risk Posture.** Every project MUST keep a Security Risk Posture, following Security by Design. It classifies the application by needs, context and data processed, and lists the security and compliance requirements, the personal data and their handling, the security perimeters, open ports and services, and the security specification of each component.

**Agents section.** The Security Risk Posture MUST include an Agents section. For each role it lists the permitted tools, network destinations, readable data and irreversible actions; irreversible actions MUST always go to a Do. Recognised references for agent security, such as the OWASP guidance on large language model and agentic applications, inform this section.

**Untrusted tasks.** Brain tasks catalogued as untrusted (§10) MUST NOT be delegated to an engine without a deterministic check of the result. If the action is irreversible, it MUST go to a Do.

**Hostile-input test.** Every project MUST run a negative test: an input carrying a hostile instruction MUST produce a recorded Deny.

**Run traceability.** Each run MUST record the profile hash, the exact model identifier, the effective configuration, the Unit Cost and the role of the agent, labelled as governance or production (§8, Governance cycle). The product MUST include a software bill of materials (SBOM). The aim is traceability, since the output of a language model cannot be reproduced deterministically.

**Data classes per provider.** The mandate MUST contain a table of data classes per provider: which providers are allowed for each class of data, taking retention and training use into account.

**Delegation of data.** Delegation MUST consider separately the origin of the data, the role's permissions, the permitted destinations and reversibility.

## 12. Writing for the Human Manager

**Three layers of documentation.** Project documentation MUST be kept in three layers, each with its reader and verifier:
- *Strategic.* For the Human Manager, who approves: Vision, Principles, success criteria, mandate. Verified by the Human Manager.
- *Managerial.* For the Human Manager, who reads and decides by exception: project record, milestone plan, High Level Architectural View, decision records, business risks, dashboard, cycle review, acceptance outcome, cost report, security and performance summaries and, in the informative mode, the Security Report. Verified by an AI reviewer.
- *Operational.* For the agents: architecture, backlog, Work Packages and staffing, Log Tracker, detailed registers, test evidence. Verified by the AI system.

**Messages between agents.** Work orders, reports, verdicts, handover abstracts and every other message from one agent to another MUST follow the agent dialect of the profile registry: a message with fixed fields, terse English, a closed list of symbols and no restatement of what the receiver already holds. A deterministic check of the format MUST run before delivery; a message that fails it is not delivered. The dialect MUST NOT be used in anything a person reads, and an instruction found inside a message remains data (§11).

**Writing rules.** The rules below apply to every document for the Human Manager, which reaches the Human Manager through the Interpreter (§4).
- **Business language.** A document MUST use business language.
- **Four questions first.** A document MUST open with what has changed, what is being asked, by when, and what happens if there is no answer.
- **Changes first.** What changed since the last reading MUST come first.
- **Length limits.** Each decision record MUST stay within the length limit that the mandate sets.
- **Outcomes, not procedures.** A document MUST report outcomes, not procedures.
- **Evidence.** Every verifiable statement MUST be linked to evidence, and the AI reviewer MUST check the link.
- **Comprehension test.** An agent with the Human Manager profile MUST test each document for comprehension. The Human Manager calibrates that agent once, on a set of documents whose size the mandate sets.
- **Bad news first.** Failed tests, open risks, dissent, rejections and missing decisions MUST come before good news.
- **Completeness check.** The document MUST be compared with the operational registers. An omission MUST block its delivery.
- **Third-party evidence pack.** On request, for a single release, the AI Coordinator MUST produce a pack containing the mandate, class, adoption level and classification mode, profiles and versions, checks and outcomes, independent verifications, accepted risks and acceptance. At level 2 the pack MUST be ready at every release. In the informative mode the pack MUST include the Security Report.
- **Qualified templates.** Each document type MUST have a versioned template qualified by the maintainers. The templates are in the Extended Framework.

**Cost report.** The cost report MUST show development costs and running costs of the application separately.

**Security Report.** In the informative mode (§14) every release MUST ship a Security Report. The writing rules MUST apply to it, except that it MUST open, in place of the four questions, with a fixed line stating that the Human Manager answers for proceeding, followed by what changed since the last reading, and MUST NOT ask anything. It MUST contain: the class, or that the case is out of scope; the findings on data, each with where it was found; the exclusion criteria triggered; the engines used; the protections applied; the protections recommended and not applied, the requirements not met among them; the declared limits recorded under §13; the actions the models refused, with the reason; and what could not be determined, the questions on security of the question round (§8) among it. It MUST say where a finding was found without reproducing the data. It MUST be updated at every Wave and at every release.

**Percentages.** Progress expressed as a percentage MUST state its denominator.

## 13. Role Profiles

**Minimum content.** A conformant Role Profile MUST contain at least:
- purpose, responsibilities, permitted and forbidden actions, and communication contract;
- normative sources, each with a precise reference to the clause from which a rule derives;
- the mandatory deterministic tools and how to interpret their results;
- a qualification suite with known-answer cases;
- declared limits: if a Work Package falls within them, the project leaves the scope of the method; in the informative mode of §14 a limit of the Security Officer or of a security, privacy or legal and compliance profile MUST instead be recorded in the Security Report;
- curator and reviewer, and the date and expiry of the qualification.

Further content, such as enabled engines, the task catalogue by Digital Seniority level (§7.1) and the Unit Cost per engine, is specified in the Extended Framework.

**Publication.** First a language model MUST run a pre-assessment: the qualification suite, consistency with the sources, format, and a search for anomalous instructions. The model MAY reject a profile but MUST NOT approve it. A domain expert reviewer then publishes the profile as a signed version. Maintenance rules, including four eyes and domain reviewers, are set by the project governance and the Extended Framework.

## 14. Applicability: classes, levels and the gate

> **Community-maintained section.** This section, with §14.1 and §14.2, is proposed by the responsible working groups (Security, with Privacy and Legal & Compliance; Adoption & Evidence, for the evidence behind thresholds) and changes are accepted by the Author via RFC without rewriting; the Author MAY return a proposal, with written reasons, only for a conflict with another part of this Guide.

**Classification mode.** The security classification of a project works in one of two modes. In the *blocking* mode the rules of this section stop a project, as each of them states. In the *informative* mode the same rules stop nothing: the Security Officer applies them to find what the blocking mode would have stopped or asked, and MUST record the class and every finding in the Security Report (§12); the Human Manager answers for proceeding. The Human Manager MAY choose the mode when the project opens, and the mandate MUST record the mode that applies. If no mode is chosen, the informative mode MUST apply when the adopter uses the method for themselves, and the blocking mode MUST apply in every other case. When no mode is chosen and it is in doubt whether the adopter uses the method for themselves, the blocking mode MUST apply; the AI Coordinator MUST record in the mandate the ground on which the mode applies. An organisation MAY impose the blocking mode through its own rules, which are a binding input of the mandate; the mode it imposes MUST apply to every project opened, and to every new version of a project approved, while those rules are in force. Rules that reach a project already open in the informative mode MUST NOT change the mode of the version in progress: the blocking mode they impose MUST apply only to the projects opened and the versions approved afterwards. The mode MUST apply from the opening of the project and MUST NOT change during it, at the approval of the mandate included, except for a new version under such rules; otherwise a different mode MUST have a new project. In the informative mode the classification MUST NOT stop or reduce any action. The rules of §14.2 that stop a project or limit its data or releases, Automatic downgrade and Running above the qualified level among them, MUST NOT stop the project or limit its data or releases, except that when a requirement that another rule of this Guide sets lapses, the environment MUST Deny the work that depends on it until the requirement is restored. Error budget (§14.1) MUST apply in both modes. A requirement of §14.1, at any level, other than Error budget, that no other rule of this Guide sets MAY be left unmet; the Security Report MUST list the requirements not met, up to the qualified level or the level of the same number as the class of the project, whichever is higher, and up to the highest level when the case is among those out of scope at any level or fits no class. Moving up (§14.2) MUST apply in both modes, and the evidence of a project in the informative mode MUST NOT count towards a higher level. In both modes an action that a model refuses MUST NOT be performed: the AI Coordinator MUST NOT have it performed by the same model with another request, or by another model, candidate or Digital Seniority level, and when competing candidates run the same Work Package, the output of every candidate for that action MUST be discarded; in the informative mode the refusal MUST be recorded in the Security Report with the reason, and in the blocking mode in the Log Tracker and in the cycle review; a refusal is an action that a model declines on the grounds of its own rules, and it MUST NOT count as a failure for lack of capability; an action that a model cannot complete MUST follow §7.1; the AI Coordinator MUST record a refused action as not performed and close the Work Package without it, when its mandatory checks pass, or re-plan it. When it is in doubt whether a model declines on the grounds of its own rules or cannot complete an action, the case MUST count as a refusal. When a refused action is a mandatory check, the Work Package MUST stay open, the check MUST NOT be repeated or assigned to another verifier under Dissent or missing proof (§9), and the AI Coordinator MUST bring the decision to the Human Manager as a Do. The other rules of this Guide MUST apply in both modes.

**Principle.** Specialist competence lives in qualified Role Profiles, not in specialists present in every project. In the blocking mode the risk that the Human Manager cannot assess is therefore limited from the start; in the informative mode it is made known in the Security Report. Every adoption of Eiraman MUST have a qualified adoption level and every project MUST have a class or, in the informative mode, the record that it fits none (Out of scope in the informative mode). In the blocking mode, a project MUST NOT run if its class exceeds the qualified level of the adopter, except by the decision of the Human Manager that §14.2 allows (Running above the qualified level). In the informative mode the class MUST NOT stop the project, and the Security Officer MUST record it in the Security Report. Whoever uses the method for themselves stays at level 0. To move up, an adopter MUST meet the requirements of the next level and demonstrate them with evidence.

**Deliverables.** Classes also apply to the deliverables a product generates. For example, in the blocking mode a level 0 adoption MUST NOT use a document generator to produce documents for customers, which are class 2. In the informative mode the Security Officer MUST record the class of the deliverables in the Security Report.

**Project classes.** Every project MUST be assigned one of the following classes, except that in the informative mode a case that fits none MUST be recorded as out of scope (Out of scope in the informative mode).

| Class | Users | Data | Exposure | Examples |
|---|---|---|---|---|
| 0 | Only the adopter | No personal data of others | Local or none | Personal tools, document generators for own use |
| 1 | Colleagues in the same organisation | Ordinary personal data of colleagues | Internal network or cloud with corporate identity | Departmental applications |
| 2 | Customers, suppliers or an authenticated public | Ordinary personal data of third parties, limited volumes | Internet with authentication | Portals, self-service, documents for customers |

**Out of scope at any level.** In the blocking mode the method MUST NOT be applied to projects that involve:
- special categories of personal data or data on criminal offences;
- children's data;
- large-scale processing of personal data;
- processing for which a data protection impact assessment is mandatory;
- automated decisions with legal or similarly significant effects on people;
- payments handled in the product's own code;
- AI systems that applicable law prohibits or classes as high-risk;
- an owner subject to network and information security obligations as an essential or important entity;
- installable distributed software or connected devices subject to product cybersecurity regulation, until dedicated requirements exist;
- activities under sector-specific regulation;
- physical safety.

The Extended Framework maps these categories to the law of each jurisdiction, starting with the European Union.

**Out of scope in the informative mode.** In the informative mode the cases above MUST NOT stop the project: the Security Officer MUST record in the Security Report each case it finds. A case that fits no class MUST be recorded as out of scope, and the project record MUST state it in place of the class.

**Applicability gate.** The Security Officer, an AI compliance role under its own qualified Role Profile, MUST assign the class or, in the informative mode, record that the case fits none, using a versioned checklist qualified by the maintainers. The AI Coordinator MUST invoke the Security Officer and MUST NOT assign the class itself. The gate MUST run when the project opens, at every Wave and at every change of mandate. In the blocking mode, if an exclusion criterion is triggered, or the case is in doubt, the project MUST be treated as out of scope and the Human Manager informed; when the only doubt is a question for the organisation not yet answered, the work on test data that Questions for the organisation allows MAY go on. In the informative mode the gate MUST NOT stop the project: the Security Officer MUST record in the Security Report the class, the exclusion criteria triggered and what it could not determine; when the scope has not changed since the last run, the Security Officer MAY record the repeated gate in the Log Tracker and in the Security Report by reference to the last run.

**Risk profile.** When the class exceeds the qualified level, or an exclusion criterion is triggered, the Security Officer MUST deliver a risk profile of the project: the class with the answers to the checklist, the exclusions touched, the treatments it proposes in order of preference, the class after each treatment, its conditions, the residual risk and what remains impossible. A proposal whose class after treatment still exceeds the qualified level MUST say that it does not let the project start at that level; for a project of class 1 in an adoption at level 0 with no exclusion criterion triggered and the class not in doubt, it MUST also say that the decision of §14.2 (Running above the qualified level) is available and what it requires or, when the only doubt is a question for the organisation not yet answered, that the decision is available only for the work on test data that Questions for the organisation allows.

**Treatments.** A treatment is a concrete form of the options of Class change (§14.2) other than running by decision: taking data or functions out of scope; building and testing only on test or masked data; keeping real data within the local execution of those already entitled to process them, never sent to agents or external services. A treatment MUST NOT be presented as a way past a case that is out of scope at any level; the only treatment of such a case MUST be to take the excluded data or function out of scope, and the reduced scope is a new scope that MUST pass the gate again.

**Questions for the organisation.** For the questions of the checklist whose answer belongs to the organisation and not to the Human Manager, such as obligations under network and information security law, a data protection impact assessment, sector-specific regulation or the data protection officer, the Security Officer MUST say who can answer and MUST prepare the question to forward. An answer given by the Human Manager alone MUST be recorded as not verified and MUST NOT be taken as resolving the question. Until the organisation answers, the case MUST be treated as in doubt (Applicability gate). In the meantime, if no exclusion criterion is triggered, work MAY go on only on test data, with no real data and no release, within the class that the qualified level permits or under the decision of §14.2 (Running above the qualified level).

**Dialogue with the Human Manager.** The Human Manager MAY question the Security Officer at any time, through the AI Coordinator. The AI Coordinator answers for the form, in business language, and MUST NOT alter the content. The original risk profile MUST be attached unchanged in the Manager View.

**Independence of the Security Officer.** The Security Officer proposes and MUST NOT act as a reviewer. The roles of security reviewer and privacy reviewer MUST stay independent of it and MUST NOT be held, on the same project, by the Security Officer or by an agent instantiated from its Role Profile. The Security Officer SHOULD run on a model different from the AI Coordinator's where one is available.

**Security Officer in the informative mode.** In the informative mode the Security Officer is silent: it MUST NOT start an exchange with the Human Manager or question them, and it MUST NOT write to the Human Manager except in the Security Report and to answer the questions they put under Dialogue with the Human Manager. The scope of the project MUST NOT be reduced on grounds of the classification. What the Security Officer cannot determine MUST be recorded in the Security Report as not determined. The AI Coordinator MAY apply, by delegation, protections proposed by the Security Officer that are reversible and take nothing away from the request; they MUST be recorded in the Security Report. Risk profile, Treatments and Questions for the organisation MUST apply in the blocking mode only. The findings of the security, privacy and legal and compliance reviewers on the class, on the presence of personal data and on the exclusion criteria MUST be recorded in the Security Report and MUST NOT keep a Work Package open, or stop or reopen a phase; their other findings MUST follow §9, defects in how the product handles personal data among them. In the Manager View the current Security Report MUST be attached in place of the risk profile (Dialogue with the Human Manager).

**Local engines in the informative mode.** The limits that the providers of external engines place on their models do not apply to an engine that runs locally. In the informative mode the mandate MUST state which local engines, if any, run the agents of the project or are part of the product, so that the Human Manager approves that use with the mandate; adding a local engine later is a change of mandate and MUST go to the Human Manager as a Do; a local engine MUST NOT be used before the Human Manager has approved its use, with the mandate or, before the mandate is approved, as a Do. The Security Report MUST name the engines used and, when one of them runs locally, MUST say so and that the limits of the providers of external engines do not apply to it.

**Legal advice.** The checklist MUST NOT be used as a substitute for legal advice.

### 14.1 Requirements per adoption level

**Cumulative requirements.** Each level MUST meet its own requirements and those of every level below it. Requirements cover the method, the organisation and the evidence. The Extended Framework gives indicative values for their thresholds and periods and maps their legal references to each jurisdiction.

**Level 0 · Method.** A personal-use adoption MUST use qualified base Role Profiles and run the deterministic anchors at every release (§9). Its documents for the Human Manager MUST include the project record with the milestone plan, the decision records, the governance cycle review with the business risks, the High Level Architectural View, the progress dashboard and an installation and user manual.

**Level 0 · Organisation.** The adopter MUST be the owner of the project and of what it produces, and answers for both (§4), except that a project that runs above the qualified level under a mandate of the organisation (§14.2) is owned, with what it produces, by that organisation, which answers for both.

**Level 0 · Evidence.** An adoption MAY start at level 0 without prior evidence.

**Level 1 · Method.** To move up from level 0 to internal-team use, the adoption MUST add:
- security and privacy profiles qualified for class 1;
- authentication only through the corporate identity;
- a backup and restore test before release;
- rules on log content and retention;
- a data protection impact screening at every change of processing;
- a breach-notification procedure within the deadline of applicable law, written for the Human Manager;
- for the Human Manager, a management summary of the Security Risk Posture, a record of processing for the controller, an Executive Description, the milestone plan as a document of its own and the business risks of the Risk Log as a register of its own.

**Level 1 · Organisation.** The owning organisation MUST be identified. The Human Manager MUST act under a formal mandate from it (§4). Corporate IT policies MUST be a binding input of the mandate. A data protection officer MUST be designated where the organisation is required to have one.

**Level 1 · Evidence.** Experience at level 0 MUST show measured results: under-escalation within the threshold, after calibration (E6); detection of a deliberately vulnerable test suite at least at the threshold the maintainers set; no critical finding open at release.

**Level 2 · Method.** To move up from level 1 to use by external users, the adoption MUST add:
- selected and verified requirements of a recognised application security verification standard;
- dynamic scanning at every release;
- authentication and payments only through certified providers;
- operation with service level objectives, incident management and blameless postmortems, which feed the retrospective;
- a policy for updating dependencies and fixing vulnerabilities that blocks the release whenever the product is offered in a commercial activity;
- for the Human Manager, a penetration test summary and the Performance Analysis;
- the third-party evidence pack ready at every release (§12).

**Error budget.** In operation at level 2, when the error budget is exhausted the environment MUST Deny non-corrective releases.

**Level 2 · Organisation.** An external penetration test, bought as a service, MUST run at the first release and then periodically; the AI Coordinator prepares its scope and authorisation and the Human Manager decides its cost. Contracts with the suppliers that process data MUST meet data protection law.

**Level 2 · Evidence.** Operation at level 1 MUST have lasted a defined period without serious incidents, and the penetration test of the first class 2 release MUST have passed.

**Release documents.** At every level each release MUST ship an installation and user manual, plus an Executive Description and a Performance Analysis where the level requires them, all verified at that release. The documents each level requires are the minimum set for the writing rules of §12.

**Operational documents.** At every level the operational layer MUST include the Product Backlog, the Work Package records, the run records and, for each team, the staffing plan and the Log Tracker.

### 14.2 Moving between levels and classes

**Moving up.** Moving up a level is a one-way door and MUST therefore go to the Human Manager as a Do. The AI Coordinator MUST present a management dossier with the requirements met, the evidence, the recurring costs and the residual risks. An independent reviewer MUST check the evidence before the Do.

**Automatic downgrade.** If a requirement lapses, for example a suspended profile, an expired penetration test or an open serious incident, the environment MUST apply a Deny. Only corrective releases MAY run until the requirement is restored or the project returns to the permitted class.

**Class change.** In the blocking mode (§14) a change of class MUST always go to the Human Manager as a Do and counts towards the drift budget (E5). If the new class exceeds the level, the Human Manager MUST choose one of four options: reduce the scope, hand the critical component to a certified provider, take that project out of the method or, where Running above the qualified level allows it, let the project run by decision. In the informative mode a change of class MUST be recorded in the Security Report and MUST NOT count towards the drift budget (E5) as a change of class; the spending and time of the work it causes MUST count as any other deviation from plan.

**Running above the qualified level.** By an explicit decision, the Human Manager MAY let a project of class 1 run in an adoption qualified at level 0. No other class and no other level are admitted this way. Each project MUST have its own decision. The decision MUST be taken on the risk profile that the Security Officer delivers (§14, Risk profile) and MUST go to the Human Manager as a Do that states the risk accepted and how each requirement of this paragraph will be met. It MUST be recorded in the project record, with a declaration that the project runs above the qualified level; the third-party evidence pack (§12) MUST carry that declaration. The project MUST meet all the Method requirements of level 1 (§14.1) before its first release; a preview given to colleagues to try is not a release. The decision waives only the Evidence of experience at level 0 that §14.1 requires for moving up. All the Method requirements and all the Organisation requirements of level 1, the formal mandate from the organisation included (§4), are due before personal data of colleagues are first processed, and the project MUST NOT process them until then; until then it MAY be built, tested and previewed only on test or masked data. If the class is in doubt between class 1 and a higher class, the higher class MUST be assumed, also when the doubt depends on a question for the organisation not yet answered; the exception below for the work on test data does not apply to it. A case that the applicability gate treats as out of scope (§14), because an exclusion criterion is triggered or the case is in doubt, or that leaves the scope of the method under §13, MUST NOT be admitted by decision, except that, while the only doubt is a question for the organisation not yet answered (§14, Questions for the organisation), the decision MAY be taken for the work on test data that that paragraph allows, and for nothing else. Once the organisation answers, the gate MUST run again, and running beyond that work MUST have a new decision under this paragraph. If a requirement of level 1 that this paragraph makes due is not met when it is due, or lapses afterwards, the permitted class of the project is the one of the qualified level until the requirement is met, and Automatic downgrade applies. At every cycle review the AI Coordinator MUST report that the project runs above the qualified level, and MUST propose moving up once the evidence exists; experience gathered on such a project counts as experience at level 0 for moving up. The decision does not qualify the adopter for level 1: moving up follows Moving up.

## 15. Conformance, partial application and feedback

**Conformance.** The tool that puts the method into practice is one implementation of it. It MUST respect the normative rules and MUST NOT add rules of its own and present them as Eiraman. An application conforms only if it respects all the normative rules of this Guide.

**Partial application.** A product that incorporates only parts of the method MUST publish a declaration of partial conformity, listing the rules applied and those not applied. It MUST NOT present itself as Eiraman-conformant without this qualification.

**Incorporable components.** Every Eiraman component that can be incorporated into a product MUST declare its contract, regression tests, version and the rules it implements.

**Feedback into the method.** Projects make the method mature in three steps.
- **Observation.** The retrospective MUST link a reproducible case, the rule applied, the outcome and the cost. The AI Coordinator MUST identify whether the cause lies in data, application, environment or method.
- **Proposal.** A specific fix stays in the application backlog. A reusable rule or component MUST come with a contract, a test, its limits and its impact on existing projects, and MUST be proposed to the method as a Request for Comments (RFC). A change to a project's Principles or Decisions MUST follow the approvals of §5.
- **Adoption.** An approved change MUST be versioned, with compatibility notes, a regression test and the list of projects adopting it. The project that prompted it MUST keep a reference to the change. Another project MAY adopt only the relevant component.

**Measuring the method.** Every rule of the method is a hypothesis until a measurement supports it. This paragraph binds those who maintain the method, the Author for this Guide and the Maintainers (§4) for the Extended Framework and, with them, the Role Profiles and Tools; it sets no obligation on adopters. Each version of this Guide, with the Extended Framework, the Role Profiles and the Tools released with it, MUST be measured on a test bench against a declared baseline; a release of one of them that does not change the Guide is covered by the campaign of the version of the method that includes it. A version MAY be released before its measurement campaign is completed, and it MUST then declare itself "not measured" in its status. The baseline is the simplest configuration without the method: two agents, one at a Digital Seniority (§7) suited to design and one at a lower Digital Seniority suited to implementation, with no AI Coordinator, no reviewer and a single candidate; the Extended Framework names the levels and the models. The baseline and the configurations compared with it MUST receive the same request, the same files and tools, the same simulated Human Manager, an agent that plays the Human Manager, and the same limits of time and cost; each run MUST be isolated from the others, and a run beyond the limits counts as failed. The baseline MUST be run again at every change of model, and a comparison MUST be made only between runs with the same models. Bench testing MUST take the delivery as it is: the testers follow the delivered instructions literally and do not make up with their own ability for what is missing, and they MUST record as a fault, that is, any failure of the delivery to do what its instructions say or what was asked, everything that does not work. The testers MUST be independent of those who developed the delivery and SHOULD NOT use models more capable than those under measurement. Seniority of the verifier (§6) does not apply to them. The requests, the briefs of the simulated Human Manager and the expected results of the tests MUST be written by someone other than those who maintain the method, and MUST be frozen before the campaign; the measured agents MUST NOT see the briefs or the expected results. An indicator that a model judges MUST follow K1 (§6). Bench testing measures the method; it is distinct from the acceptance testing of §9.1, in which a person performs the business task of a project and the Human Manager decides on acceptance, and neither replaces the other. The hypotheses of a campaign, each with its primary indicator, its margin and its number of repetitions, MUST be recorded before the campaign and MUST NOT change after it; every result MUST be kept and counted, unfavourable, failed and interrupted runs included. When a test that removes a single rule excludes, with the repetitions declared before the campaign, a benefit above the declared margin, whoever coordinates the work on the method MUST propose to the Human Manager to reduce that rule to Guidance or to remove it. When a completed campaign demonstrates, within the declared margin, that for a class of project the baseline obtains the same result at a lower cost, the Author MUST state it in this Guide and indicate the baseline for that class; the conclusion holds only for the classes the bench represents. An outcome of "not demonstrated" is enough for neither. The Extended Framework gives as Guidance the indicators, what counts as the same result, the measure of the cost of realignment, the test applications, the number of repetitions, the limits and the models of the baseline.

**Changing the method.** This Guide MUST change only through an RFC, decided by the Author with written reasons. Community-maintained sections are proposed by their working groups and accepted by the Author via RFC without rewriting; the Author MAY return a proposal, with written reasons, only when it conflicts with another part of this Guide. The Extended Framework, Role Profiles and Tools are governed by the community under the project governance. A community decision that would change the text of this Guide MUST also have an accepted Guide RFC.

## 16. End note

**Version history.** Version 1.0 supersedes the Italian specification 0.3, which remains the historical source and is kept, non-normative, in `history/`. Version 1.0 is the first in canonical English under an open licence; it separates this Guide from the Extended Framework and opens part of it to community maintenance. Version 0.3 restored AI Squads, Design Thinking between models and composable architecture, and added Digital Seniority. Version 0.2 revised accountabilities, levels, escalation, competition and conformance. The full history is in `HISTORY.md`.

**Acknowledgements.** Eiraman draws on established management and engineering practice. The Scrum Guide is the work of Ken Schwaber and Jeff Sutherland. TOGAF® is a registered trademark of The Open Group. Sources for the rules of this Guide are listed in the body of knowledge of the Extended Framework.
