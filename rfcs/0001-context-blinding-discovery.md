<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# RFC 0001: Context Consistency and Independence, agent blinding, AI Reviewer and Discovery as Design Thinking AI

- **Author(s):** the Steward, on behalf of the working groups not yet formed
- **Accountable human:** Paolo Ungari (Steward)
- **AI-Use:** substantial (CONTRIBUTING.md §3)
- **Assisted-by:** Claude Opus 5.5
- **Conflicts of interest:** none
- **Owner of the decision:** Author (Guide)
- **Affected artifacts:** Guide §3, §4, §7, §8, §8.1, §9, §9.1; Role Profiles (AI Reviewer, Design Thinking Facilitator, AI Coordinator, functional analyst, simulated user; Business Analyst and User Persona templates), in a separate release of `role-profiles`
- **State:** accepted
- **Dates:** opened 2026-11-26 · comment period ends 2026-12-10 · accepted 2026-11-26, before the end of the comment period (deviation, see Decision)

## Summary

This RFC adds to the Guide a fourth context principle, **Context Consistency and Independence**: agents that work on the same information share context, agents whose role needs divergence or independence work in independent contexts. It introduces **hard blinding** and **soft blinding** (with a **context RACI**) to keep roles from overlapping, an **AI Reviewer** that extends the process reviewer to continuous monitoring, and a detailed **Discovery as Design Thinking AI** led by a **Design Thinking Facilitator** with a **Discovery group** that is not an AI Squad. Design and planning becomes a dedicated Work Package, every Work Package gets a new agent with a new context, and each agent closes with a **Work Package handover abstract**. User Personas run the simulated-user functional tests. The change affects every project that applies the Guide, its AI Coordinator and the Role Profiles listed above.

The RFC touches one community-maintained section, the test practices (§9.1). Its working groups do not exist yet, so the Steward proposes that text in this RFC; the Author accepts it by RFC as for any community-maintained section (Guide §0, §15). The phase playbooks (§8.1) are maintained by the Author, as are the other sections touched (PA-1 × D-OPEN-4).

## Motivation

The change request CR-003 of the project "Eiraman Open Framework" (26 November 2026), with the Human Manager's decisions Do-S03 to Do-S06, records these problems:

- **Context is treated in one place only.** Guide 1.0.0-rc.1 says "A team shares one context" and keeps the unit tester out of it (§7), and requires independent verification (§6). It does not say, as a rule of the method, which agents must share context and which must not, so the AI Coordinator has no general criterion when it forms AI Squads and groups. The audit in the appendix shows several roles whose independence the text leaves implicit.
- **Roles overlap.** An agent that can read everything tends to act outside its role. The Guide has no mechanism that limits what an agent knows of the project.
- **The process reviewer only samples.** It checks closed Waves after the fact. Nobody watches the framework and project KPIs while the work runs.
- **Discovery is under-specified.** §8 names divergence and convergence, and gives convergence to a single model as functional analyst, which is also a participant. There is no facilitator, no group composition, no procedure, and no report of how positions changed.
- **Design and planning is listed with the AI Coordinator among its roles**, so the agent that validates the plan also writes it.
- **Context grows across Work Packages.** Reusing the same agent carries over a context that is large, unchecked and not designed for the next package.
- **"Human Supervised" functional tests** in the historical specification were read as tests watched by a person; Do-S03 decided that they are tests run by User Personas as simulated users, and that PA-8 stays.

Decisions applied: **Do-S03** (User Personas as simulated users; PA-8 stays), **Do-S04** (Business Analyst and User Personas are project instances of qualifiable templates; PA-7 stays), **Do-S05** (the functional analyst links business needs to the solutions of UX-UI and architects; MOC means mock-up), **Do-S06** (hard blinding by environment and prompt, local model as an option; blinding concerns project information, not the model's general knowledge). The Author's decisions on the open points of the draft: **Do-S07** (acceptance, see Decision), **Do-S08** (recipients of the AI Reviewer's reports), **Do-S09** (who the Discovery reviewers are), and the correction that §8.1 is Author-maintained. Editorial points that stay: PA-2 (no numbers), PA-3 (vendor neutrality), PA-6 B (different model as a recommendation), PA-7, PA-8, PA-12 (RFC 2119 capitals).

## Proposal

The proposed text is in `EIRAMAN-GUIDE.md` at version 1.0.0-rc.2. Changes by section:

| Section | Change | Kind |
|---|---|---|
| Title block | Version 1.0.0-rc.2 | Modified line |
| §3 Context principles | "Three principles" becomes "Four principles"; new principle **Context Consistency and Independence** | Modified line; new paragraph |
| §4 Accountabilities | New paragraphs **AI Reviewer** (with the reports to the AI Coordinator and, for critical or unaccepted deviations, to the Human Manager in the Manager View, Do-S08) and **Suggestions of the AI Reviewer**. **Process reviewer** is unchanged | New paragraphs |
| §7 AI Squads and Digital Seniority | New item **A new agent for every Work Package**, with the Work Package handover abstract; **Shared context, except for the unit tester** now scopes the shared context to one Work Package; new paragraphs **Agent blinding**, **Hard blinding**, **Soft blinding** (context RACI) | New paragraphs; modified line |
| §8 Lifecycle and events | New paragraphs **Discovery at every start**, **Discovery group**, **Business Analyst and User Personas**, **Discovery executors and reviewers** (the Discovery reviewers are the reviewer profiles of the governance domains the project touches, security and privacy always present, Do-S09), **Discovery report**, **Design and planning as a Work Package**; **Convergence** moves from the functional analyst to the Design Thinking Facilitator. **Divergence**, **Gates** and **Phases and decisions** are unchanged | New paragraphs; replaced rule |
| §8.1 Phase playbooks | **Who works in each phase**: Discovery and Design and planning items updated; new paragraphs **Roles in the Discovery group** and **Discovery procedure** (step by step, descriptive; the obligations are in §8) | Modified lines; new paragraphs |
| §9 Commitments and artifacts | **Work Package record** adds the context RACI and the Work Package handover abstract | Modified line |
| §9.1 Test practices | **Test types**: simulated-user functional tests are run by the User Personas. **Who supervises tests** (PA-8) is unchanged | Modified line |

No section number changes. No paragraph label is removed.

### Rules replaced

Every line removed from `EIRAMAN-GUIDE.md` between `v1.0.0-rc.1` and the candidate is listed here, old text first, then new text. No heading is removed.

**1. Title block.**

> Old: **Version 1.0.0-rc.1 · November 2026 · Release candidate**
>
> New: **Version 1.0.0-rc.2 · November 2026 · Release candidate**

Version string only.

**2. §3, opening sentence.**

> Old: Three principles bound every rule of the method.
>
> New: Four principles bound every rule of the method.

Follows from the new principle.

**3. §7, Shared context, except for the unit tester.**

> Old: - **Shared context, except for the unit tester.** A team shares one context. The unit tester MUST NOT receive the team's discussion, so as not to bias the tests; it receives requirements, contracts, data and expected results. It MAY run on a different engine, or on the same engine without that context; for security and personal data, §6 applies.
>
> New: - **Shared context, except for the unit tester.** Within a Work Package, a team shares one context. The unit tester MUST NOT receive the team's discussion, so as not to bias the tests; it receives requirements, contracts, data and expected results. It MAY run on a different engine, or on the same engine without that context; for security and personal data, §6 applies.

Reconciles the shared team context with a new agent for every Work Package. The unit tester rule is unchanged.

**4. §8, Convergence.** Replaced rule.

> Old: **Convergence.** A single model, in the role of functional analyst, MUST gather the contributions, relate them to user evidence and produce the draft Vision and a first version of Scope Management: Vision, Principles, success criteria and open points. The Human Manager MUST then approve the Vision or relaunch the exploration.
>
> New: **Convergence.** The Design Thinking Facilitator MUST lead convergence; the functional analyst takes part as a member of the group. The Facilitator MUST submit the same prompt to every executor of the group, record the answers, restate them as Principles, Decisions and open points, and iterate until consensus within the maximum number of rounds that the mandate sets; it MUST then submit the result to the Discovery reviewers. Convergence MUST gather the contributions, relate them to user evidence and produce the draft Vision, the success criteria and the first draft of Scope Management. The Human Manager MUST then approve the Vision and the Principles, or relaunch the exploration.

What is replaced: convergence by "a single model, in the role of functional analyst". What is kept: gathering the contributions, relating them to user evidence, the draft Vision, the success criteria, the open points and the Human Manager's approval of the Vision. What is broadened: Decisions enter the first draft of Scope Management, and the Human Manager approves the Principles together with the Vision (as §4 already requires). The maximum number of rounds stays a value of the mandate (PA-2).

**5. §8.1, Who works in each phase, Discovery item.**

> Old: - *Discovery:* the AI Coordinator, the analyst and explorer agents on different models; divergence, then convergence by the analyst.
>
> New: - *Discovery:* the Discovery group that the AI Coordinator forms, its members on different models; divergence, then convergence led by the Design Thinking Facilitator.

The explorer agents become the members of the Discovery group; convergence follows the new §8 rule.

**6. §8.1, Who works in each phase, Design and planning item.**

> Old: - *Design and planning:* the analyst, application and infrastructure architects, AI Scrum Master and AI Coordinator, who produce business, application, data and technology views; alternative architectures assessed against a rubric fixed in advance.
>
> New: - *Design and planning:* the team of a dedicated Work Package, with the analyst, application and infrastructure architects and AI Scrum Master, who produce business, application, data and technology views; alternative architectures assessed against a rubric fixed in advance.

The AI Coordinator leaves the roles that perform Design and planning; it assigns the Work Package (§8).

**7. §9, Work Package record.**

> Old: **Work Package record.** A Work Package record MUST hold at least: project and Wave, identifier and starting revision; success criteria and exclusions; Principles, Decisions and dependencies; profiles and their versions; budget and attempts allowed; expected result and verifier; resumption procedure.
>
> New: **Work Package record.** A Work Package record MUST hold at least: project and Wave, identifier and starting revision; success criteria and exclusions; Principles, Decisions and dependencies; profiles and their versions; budget and attempts allowed; expected result and verifier; resumption procedure; the context RACI handed to its agents; and, at closing, the Work Package handover abstract of each agent.

Broadened: two items added, none removed.

**8. §9.1, Test types, simulated-user functional tests.**

> Old: - *Simulated-user functional tests:* an agent simulates a typical user and uses the application as a person would. They cost more, so they run in stable environments.
>
> New: - *Simulated-user functional tests:* the User Personas of the project, as simulated end users, use the application as a person would. They cost more, so they run in stable environments.

Do-S03: the agent that simulates the user is a User Persona. **Who supervises tests** keeps the PA-8 wording: the person MAY watch functional tests, but their progress MUST NOT depend on the person.

### Removed lines in the other files of the release

These lines carry no rule; they are listed so that the scope review can map every removed line.

| File | Old line | New line |
|---|---|---|
| `README.md` | Status: version 1.0.0-rc.1, a release candidate. … | Status: version 1.0.0-rc.2, a release candidate, with RFC 0001. … |
| `TRACEABILITY.md` | Row R002, "Version 1.0.0-rc.1" | Row R002, "Version 1.0.0-rc.2" (version string only; the row is kept) |
| `TRACEABILITY.md` | "Count check": the line "Paragraphs with a key word that carry no normative row: 0" and the "Result: PASS" line | The same lines, naming the known exemptions, the RFC 0001 rows and their mapping |
| `CHANGELOG.md` | `[Unreleased]: …/compare/v1.0.0-rc.1...main` | `[Unreleased]: …/compare/v1.0.0-rc.2...main` |
| `rfcs/README.md` | Empty index row "— · — · —" | Index row for RFC 0001, state accepted |
| `CHANGELOG.md` | In the 1.0.0-rc.1 entry, the three lines of "Community-maintained sections (PA-1 C)", which listed the phase playbooks (§8.1) as community-maintained | "Broad Guide (PA-1 C)": the same four parts, with the phase playbooks maintained by the Author; the correction is recorded under Fixed in 1.0.0-rc.2 |

## Reversibility

A change to the Guide text is a one-way door (GOVERNANCE §6.2). The new obligations are additions: removing them later would be MAJOR under VERSIONING §2.1. While the Guide is a release candidate, not in force, rolling back costs a new candidate that restores the rc.1 text of the eight lines above and drops the new paragraphs; projects that already applied the new roles would keep them as project practice. The Role Profiles released with this RFC (AI Reviewer, Business Analyst and User Persona templates) would be suspended, not deleted.

## Impact

- **Adopters.** Every project adds a Discovery group and a Design Thinking Facilitator at start, a dedicated Design and planning Work Package, a new agent for every Work Package, a context RACI for every AI Squad, an AI Reviewer, and hard blinding for the AI Coordinator, the AI Reviewer, the Facilitator and the Discovery reviewers. Cost rises with the number of agents and rounds; the mandate sets the maximum number of rounds. No change to applicability levels or classes.
- **Role Profiles.** New: AI Reviewer; Business Analyst and User Persona templates. Updated: Design Thinking Facilitator, AI Coordinator (blinding, context RACI, handover abstracts, Design and planning as a Work Package), functional analyst, simulated user. Released separately, in `role-profiles` 0.2.0 (package DT-PROFILES).
- **Tools.** A tool that enforces hard blinding has to restrict files, tools, data and retrieval per role. The traceability check gains the RFC rows.
- **Translations.** None published yet.
- **Version.** Obligations are added or broadened and none is removed or reversed: MINOR under VERSIONING §2.1. The Guide is a pre-release of 1.0.0, so the candidate number goes from rc.1 to rc.2.

## Alternatives

- **Do nothing.** Leaves the independence of reviewers, the Facilitator and the AI Coordinator implicit, and keeps a participant as the convergence judge.
- **Put Discovery entirely in §8.1.** §8.1 describes how the AI system usually works; the rules are those of §8. Obligations in §8.1 would contradict that sentence, so the obligations stay in §8 and the step-by-step procedure in §8.1.
- **Replace the process reviewer with the AI Reviewer.** The process reviewer MUST run on a model different from the AI Coordinator's; the AI Reviewer SHOULD (PA-6 B, a different model may not be available). Merging them would turn a MUST into a SHOULD, which removes an obligation. The AI Reviewer extends the process reviewer, whose checks keep their different model.
- **Make a local model mandatory for hard blinding.** Rejected by Do-S06: it depends on hardware; environment and prompt suffice, the local model is an option.

## Acceptance evidence

- `tools/release_diff.py` from `v1.0.0-rc.1` to the candidate: every removed line is listed above; no heading removed; the RFC 2119 counts rise only.
- `TRACEABILITY.md`: all rc.1 rows kept; one row per new or changed paragraph, marked "RFC 0001"; the traceability check passes.
- Independent scope review REV-DT: every change maps to CR-003, terms are consistent between the Guide and the Role Profiles, no conflict with PA-7 and PA-8.
- The Author's decision on this RFC, with written reasons, before the release Do (recorded below, Do-S07).

## Open questions

All open questions of the draft were decided by the Author on 2026-11-26:

- **§8.1 marker.** Under PA-1 × D-OPEN-4 only the adoption levels, the Digital Seniority catalogue and the test practices are community-maintained; the phase playbooks (§8.1) are maintained by the Author. No boxed note is added; the 1.0.0-rc.1 changelog entry that said otherwise is corrected.
- **AI Reviewer reports (Do-S08).** The AI Reviewer reports deviations to the AI Coordinator, which evaluates them critically and answers. Critical deviations, and deviations the AI Coordinator does not accept, also go to the Human Manager in the Manager View. Added to §4 AI Reviewer.
- **Discovery reviewers (Do-S09).** The reviewer profiles of the governance domains that the project touches, chosen by the AI Coordinator; the security and privacy domains are always present. Added to §8 Discovery executors and reviewers.
- **Comment period (Do-S07).** Decided below.

## Decision

**Accepted**, on 2026-11-26, by the Author (Do-S07).

Written reasons: no community member is active yet; founding contributors may reopen it with a new RFC.

**Deviation from the comment period.** The decision was taken before the end of the comment period (2026-12-10), which `rfcs/README.md` sets at no less than fourteen days. The deviation is recorded here and in the changelog; it does not change the process for later RFCs.

## Appendix: audit of the Context Consistency and Independence principle

Every place in the Guide (1.0.0-rc.2) where agents share, or must not share, context. *Shared* means a shared context; *independent* means an independent context. "Said before" states whether rc.1 already said so; "Said now" states where rc.2 says it.

| # | Where | Agents | Context | Why | Said before (rc.1) | Said now (rc.2) |
|---|---|---|---|---|---|---|
| A1 | §7 Agentic Scrum, Shared context | Executors (developers), architects and AI Scrum Master of one team | Shared, within one Work Package | They work on the same information and must collaborate | Yes: "A team shares one context" | Yes, scoped to one Work Package; principle in §3 |
| A2 | §7 Agentic Scrum, One AI Scrum Master per team | AI Scrum Master and the team's agents | Shared | It coordinates the team and keeps its Log Tracker | Implicit | Covered by §3 and A1 |
| A3 | §7 Shared context; §9.1 Unit tests | Unit tester vs the team | Independent | Not to bias the tests; it receives requirements, contracts, data and expected results only | Yes | Yes, unchanged; principle in §3 |
| A4 | §4 Specialist AI roles | Testers vs executors | Independent first assessment | The tester must not inherit the executor's reasoning | Yes: first assessment independent of the executor's discussion | Yes, unchanged; principle in §3 |
| A5 | §9.1 Test types, simulated-user functional tests | User Personas vs executors | Independent | They act as end users, who do not know the implementation | No: "an agent simulates a typical user" | Yes: User Personas as simulated end users; principle in §3 |
| A6 | §6 K1, K2, Competing teams (§7) | Competing candidates and teams | Independent of each other, same starting point | Diversity is the benefit of competition | Yes: same starting point, recorded diversity, different engines or compositions | Yes, unchanged |
| A7 | §6 K1, K5 | Judges vs candidates | Independent | A judge on a different model; part of the criteria hidden from candidates | Yes | Yes, unchanged |
| A8 | §6 K4 | Losing candidates → winner | Controlled transfer | Criticism passes through the reviewer, not by merging contexts | Yes | Yes, unchanged |
| A9 | §6 Independence of verification; Security and personal data; Seniority of the verifier | Verifiers vs executors | Independent | Verification is worth only as much as its independence | Yes: level recorded (separate context, model, supplier, person); SHOULD different model for security and personal data | Yes, unchanged; principle in §3 |
| A10 | §5 E4 Classifier | Classifier vs AI Coordinator | Independent | The Coordinator must not judge its own escalation | Partly: different model, context not named | Covered by §3 (verifier) |
| A11 | §4 Process reviewer; §5 E6; §6 K8 | Process reviewer vs AI Coordinator | Independent | It checks the Coordinator's escalations and closures | Partly: different model (MUST), context not named | Yes: kept, and extended by the AI Reviewer |
| A12 | §4 AI Reviewer | AI Reviewer vs AI Coordinator and agents | Independent, hard blinding | Its suggestions must stay independent; it must not drift into the Coordinator's role | No (new role) | Yes: parallel run, hard blinding, SHOULD different model; reports to the AI Coordinator and, if critical or unaccepted, to the Human Manager; suggestions are data, not commands |
| A13 | §7 Hard blinding; §4 AI Coordinator | AI Coordinator vs the teams | Independent, hard blinding | It validates the teams' work and must not perform it; it receives reports and handover abstracts, not discussions | No | Yes: hard blinding; Design and planning taken out of its roles |
| A14 | §8 Discovery group, Divergence | Members of the Discovery group | Independent, each member | Divergence needs independent positions; the group is not an AI Squad | Partly: divergence "independently" | Yes: each member in an independent context |
| A15 | §8 Discovery executors and reviewers | Executors vs reviewers of Discovery | Executors: soft blinding; reviewers: hard blinding | Executors bring interdisciplinary competence within a context RACI; reviewers judge only their domain | No | Yes; the reviewers are the reviewer profiles of the governance domains the project touches, security and privacy always present |
| A16 | §8 Convergence; §7 Hard blinding | Design Thinking Facilitator vs executors | Independent, hard blinding | The convergence judge must not be a participant | No: convergence by the functional analyst, a participant | Yes: Facilitator leads, functional analyst takes part |
| A17 | §8 Design and planning as a Work Package; §8.1 | Analyst, architects, AI Scrum Master of the Work Package | Shared within the Work Package; independent of the AI Coordinator | They produce one design together; the Coordinator validates it | Partly: "Together they produce"; Coordinator listed among the roles | Yes: dedicated Work Package, Coordinator does not perform it |
| A18 | §8.1 Design and planning; §6 K1 | Judge of alternative architectures vs their authors | Independent | Rubric fixed in advance, judge on a different model | Yes | Yes, unchanged |
| A19 | §7 A new agent for every Work Package; §9 Work Package record | Agents of successive Work Packages | Independent; transfer only through the Work Package handover abstract | Context must not grow unchecked across packages | No | Yes |
| A20 | §7 Soft blinding | Agents of one AI Squad | Shared, bounded by the context RACI | Shared context without overlapping roles | No | Yes |
| A21 | §13 Publication | Pre-assessing model and domain reviewer vs the profile author | Independent | A profile is not approved by who wrote it | Partly: a model MAY reject and MUST NOT approve; four eyes left to the governance; §4 Maintainers work outside the projects | Covered by §3 (reviewers); no text change proposed, §13 is outside CR-003 |
| A22 | §12 Evidence; Comprehension test | AI reviewer of documents; agent with the Human Manager profile vs the authors of the document | Independent | A check by the author is not a check | No | Covered by §3 (reviewers); no text change proposed |
| A23 | §9 Dissent or missing proof | Another verifier vs the first | Independent | A repeated test must not inherit the dissent | Implicit | Covered by §3 |
| A24 | §14.2 Moving up | Independent reviewer vs the AI Coordinator | Independent | It checks the dossier before the Do | Yes: "an independent reviewer" | Yes, unchanged |
| A25 | §14 Applicability gate | AI compliance role vs the executors | Independent | The class must not be set by who benefits from a lower one | No | Covered by §3 (verifier); no text change proposed, §14 is outside CR-003 |

**Summary.** Twenty-five places. Shared context: A1, A2, A17 (within the Work Package), A20 (bounded by the RACI). Independent context: the other twenty-one, with A8 and A19 as controlled transfers. rc.1 stated nine fully (A1, A3, A4, A6, A7, A8, A9, A18, A24) and five partly (A10, A11, A14, A17, A21). rc.2 states ten explicitly (A5, A11 to A17, A19, A20) and covers the rest (A2, A10, A21, A22, A23, A25) through the principle in §3. A21, A22 and A25 lie in sections outside CR-003; making them explicit needs a further RFC if the community wants it.
