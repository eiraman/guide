<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# RFC 0004: Running a class 1 project from level 0, by decision of the Human Manager; the Security Officer

- **Author(s):** the Steward, on behalf of the working groups not yet formed
- **Accountable human:** Paolo Ungari (Steward)
- **AI-Use:** substantial (CONTRIBUTING.md §3)
- **Assisted-by:** Claude Fable 5.2
- **Assisted-by:** Claude Opus 5.5 (independent review)
- **Conflicts of interest:** none
- **Owner of the decision:** Author (Guide)
- **Affected artifacts:** Guide §4, §5, §7, §14, §14.1, §14.2; `TRACEABILITY.md`. After acceptance, in separate releases: Role Profiles (Security Officer, new; AI Coordinator; gate checklist), Extended Framework, Tools, site and kit
- **State:** accepted
- **Dates:** opened 2026-11-26 · comment period ends 2026-12-26 · accepted 2026-11-26, before the end of the comment period (deviation, see Decision)
- **Change request:** CR-013 and CR-014 of the project "Eiraman Open Framework"; decided by Do-S26

## Summary

Guide 1.0.0-rc.3 forbids a project whose class exceeds the qualified adoption level of the adopter. An adopter at level 0 therefore cannot start a departmental project, which is class 1, even when the Human Manager knowingly accepts the risk. This RFC adds one exception: by an explicit and recorded decision, the Human Manager can let a class 1 project run in an adoption qualified at level 0. No other class and no other level are admitted this way.

The exception waives only the evidence of experience at level 0 that moving up requires. Every Method requirement of level 1 is due before the first release. Personal data of colleagues are processed only once every Method and Organisation requirement of level 1 is met, the formal mandate included; until then the project works on test or masked data. With the mandate, ownership of the project and liability towards third parties lie with the organisation. The cases that the applicability gate treats as out of scope stay excluded, except that, while the only doubt is a question for the organisation not yet answered, the decision can cover work on test data alone, not masked data. Each project needs its own decision, and the decision does not qualify the adopter for level 1.

The RFC also names the AI compliance role that runs the applicability gate: the **Security Officer**. It assigns the class in place of the AI Coordinator and, when the class exceeds the level or an exclusion is triggered, it does not only stop the project: it delivers a risk profile with the treatments that would let the work proceed with less risk, and with what stays impossible. The decision of the Human Manager to run above the qualified level is taken on that profile.

The change concerns adopters at level 0, their AI Coordinator and the Security Officer.

The RFC changes §14, §14.1 and §14.2, which are community-maintained and whose working groups do not exist yet; the Steward proposes the text here and the Author accepts it by RFC (Guide §0, §15). Because it relaxes a requirement of the adoption levels, its comment period is thirty days (`rfcs/README.md`, step 3).

## Motivation

The evidence comes from the project's test bench, on 26 November 2026. Three requests written as a departmental manager would write them were run in isolation with a kit built from the Role Profiles registry at version 0.7.0. The applicability gate classed them above the qualified level of 0, two as class 1 and one as class 2, and found special categories of data in one of the class 1 requests. No project started; one run ended with a page of requirements for the IT department instead of a program. With an earlier kit the same requests had started after a Do, which the Guide does not allow either.

The gate behaved as §14 prescribes. The question put to the Human Manager was therefore whether that behaviour is the one wanted: "Should the applicability check let a departmental project start by a decision of the Manager?". The answer was yes, by decision (CR-013), followed by nineteen decisions on its limits, all taken on 26 November 2026:

1. the decision reaches one level above the qualified level, and no higher: from level 0, a class 1 project and not a class 2 one. This RFC adopts the reading of decision 1 that the Human Manager confirmed: level 0 and class 1 only;
2. the cases out of scope at any level stay excluded and cannot be admitted by decision;
3. all the technical requirements of the higher level stay due; the decision waives only the evidence of experience at the lower level. In the words of §14.1, the Method requirements of level 1 stay due, including the ones that are not strictly technical, such as the record of processing and the breach-notification procedure. The Human Manager confirmed this reading (decision 10);
4. the decision is written down, with the risk, in a Do, in the project record and in a declaration that the project runs above the qualified level; when personal data of colleagues are processed, the formal mandate of the organisation remains necessary. Carrying the declaration into the third-party evidence pack is how this RFC implements the decision;
5. when personal data of colleagues are processed, all the Organisation requirements of level 1 stay due, not the mandate alone;
6. for a project that runs under the mandate of the organisation, liability towards third parties lies with the organisation;
7. each project needs its own decision; at every cycle review the AI Coordinator recalls that the project runs above the level and proposes moving up when the evidence exists; experience gathered on that project counts for moving up;
8. while no Role Profile is qualified, a project admitted this way uses the draft profiles and declares it in the decision as an accepted risk. This is a deviation of the project that maintains the method, which already holds for level 0; it is not a rule of the Guide and this RFC does not write it; the deviation ends when the security and privacy profiles are qualified;
9. the Method requirements of level 1 are due before the first release, so the project can start and work before they are all in place; the Organisation requirements are due before personal data of colleagues are processed (see decision 14);
10. the Method requirements of level 1 are all due, the record of processing and the breach-notification procedure included;
11. no independent check is required before the decision: the Do prepared by the AI Coordinator is enough;
12. the Do also states how each requirement will be met; the project and what it produces are owned by the organisation that gives the mandate;
13. when the class is in doubt between class 1 and a higher class, the higher class is assumed, so the project cannot start by decision;
14. real personal data of colleagues enter only when all the protections of level 1 are in place, Method and Organisation; before that the project is built and tested on test or masked data. This narrows decision 9;
15. a preview given to colleagues to try is not a first release: the Method requirements are due at the formal release;
16. while a question that belongs to the organisation is unanswered, work may go on, on test data only;
17. the Security Officer works under hard blinding; a model different from the AI Coordinator's is recommended where available, not required;
18. while the only doubt is a question for the organisation not yet answered, the decision to run above the level can be taken for the work on test data alone, with no real data and no release. This RFC adds, as a consequence of decision 7, that going beyond that work after the organisation answers needs a new decision;
19. during that wait only test data are used, not masked data, which come from real ones.

The management practice behind the change is the explicit acceptance of a risk by the person who answers for it, within limits that the organisation sets.

**The Security Officer.** The same runs showed a second problem: the gate stopped three requests out of three without proposing any way to carry them out, although the risks it found were real and useful to know. The Human Manager asked for a role whose aim "is not to block the execution but to find a way to carry it out while minimising the risks", with which the Manager can talk, the AI Coordinator being answerable for putting the exchange in terms a business manager understands (CR-014). Asked how to bring it into the Guide, the Human Manager chose to put the role in this RFC rather than in a separate one. The independent review of the draft Role Profile added a warning that this RFC takes up: with the Guide as it is, at level 0 no treatment makes it possible to start a product that processes personal data of other people in operation; masking serves to build and test. Without the decision of item 2, the risk profile only says "it cannot be done" in a better way. The management practice is that of the security officer who proposes how to treat a risk and leaves the decision to whoever answers for it.

## Proposal

The proposed text is below, item by item. The accepted items are applied in `EIRAMAN-GUIDE.md` at version 1.0.0-rc.4.

| Section | Change | Kind | Source |
|---|---|---|---|
| §14 Applicability | Principle refers to the exception; Applicability gate names the Security Officer; new paragraphs Risk profile, Treatments, Questions for the organisation, Dialogue with the Human Manager, Independence of the Security Officer | Modified lines; new paragraphs | CR-013 (decisions 16 to 19); CR-014 |
| §14.2 Moving between levels and classes | New paragraph Running above the qualified level; Class change gains an option | New paragraph; modified line | Decisions 1 to 5, 7, 9 to 15 and 18 |
| §14.1 Requirements per adoption level | Level 0 · Organisation: ownership of a project run under the organisation's mandate | Modified line | Decisions 5, 6 and 12 |
| §4 Accountabilities | Liability towards third parties for such a project | Modified line | Decision 6 |
| §7 AI Squads | Hard blinding covers the Security Officer | Modified line | CR-014, decision 17 |
| §5 3D escalation | Deny takes class 1 as the limit for an admitted project, unless a requirement of level 1 is due and not met; during the wait for the organisation only test data and no release; the decision is in the list of what goes to the Human Manager | Modified lines | CR-013, decisions 4, 9, 18 and 19 |

No section number changes. No paragraph label is removed.

### Rule relaxed

**1. §14, Principle.** Community-maintained section.

> Old: **Principle.** Specialist competence lives in qualified Role Profiles, not in specialists present in every project. The risk that the Human Manager cannot assess is therefore limited from the start. Every adoption of Eiraman MUST have a qualified adoption level and every project MUST have a class. A project MUST NOT run if its class exceeds the qualified level of the adopter. Whoever uses the method for themselves stays at level 0. To move up, an adopter MUST meet the requirements of the next level and demonstrate them with evidence.
>
> New: **Principle.** Specialist competence lives in qualified Role Profiles, not in specialists present in every project. The risk that the Human Manager cannot assess is therefore limited from the start. Every adoption of Eiraman MUST have a qualified adoption level and every project MUST have a class. A project MUST NOT run if its class exceeds the qualified level of the adopter, except by the decision of the Human Manager that §14.2 allows (Running above the qualified level). Whoever uses the method for themselves stays at level 0. To move up, an adopter MUST meet the requirements of the next level and demonstrate them with evidence.

What is relaxed: the prohibition gains one exception. What is kept: every adoption has a qualified level, every project has a class, and moving up needs the requirements and the evidence.

### Rules added or changed

**2. §14.2, new paragraph Running above the qualified level**, after **Class change**. Community-maintained section.

> New: **Running above the qualified level.** By an explicit decision, the Human Manager MAY let a project of class 1 run in an adoption qualified at level 0. No other class and no other level are admitted this way. Each project MUST have its own decision. The decision MUST be taken on the risk profile that the Security Officer delivers (§14, Risk profile) and MUST go to the Human Manager as a Do that states the risk accepted and how each requirement of this paragraph will be met. It MUST be recorded in the project record, with a declaration that the project runs above the qualified level; the third-party evidence pack (§12) MUST carry that declaration. The project MUST meet all the Method requirements of level 1 (§14.1) before its first release; a preview given to colleagues to try is not a release. The decision waives only the Evidence of experience at level 0 that §14.1 requires for moving up. All the Method requirements and all the Organisation requirements of level 1, the formal mandate from the organisation included (§4), are due before personal data of colleagues are first processed, and the project MUST NOT process them until then; until then it MAY be built, tested and previewed only on test or masked data. If the class is in doubt between class 1 and a higher class, the higher class MUST be assumed, also when the doubt depends on a question for the organisation not yet answered; the exception below for the work on test data does not apply to it. A case that the applicability gate treats as out of scope (§14), because an exclusion criterion is triggered or the case is in doubt, or that leaves the scope of the method under §13, MUST NOT be admitted by decision, except that, while the only doubt is a question for the organisation not yet answered (§14, Questions for the organisation), the decision MAY be taken for the work on test data that that paragraph allows, and for nothing else. Once the organisation answers, the gate MUST run again, and running beyond that work MUST have a new decision under this paragraph. If a requirement of level 1 that this paragraph makes due is not met when it is due, or lapses afterwards, the permitted class of the project is the one of the qualified level until the requirement is met, and Automatic downgrade applies. At every cycle review the AI Coordinator MUST report that the project runs above the qualified level, and MUST propose moving up once the evidence exists; experience gathered on such a project counts as experience at level 0 for moving up. The decision does not qualify the adopter for level 1: moving up follows Moving up.

**3. §14.2, Class change.** Community-maintained section.

> Old: **Class change.** A change of class MUST always go to the Human Manager as a Do and counts towards the drift budget (E5). If the new class exceeds the level, the Human Manager MUST choose one of three options: reduce the scope, hand the critical component to a certified provider, or take that project out of the method.
>
> New: **Class change.** A change of class MUST always go to the Human Manager as a Do and counts towards the drift budget (E5). If the new class exceeds the level, the Human Manager MUST choose one of four options: reduce the scope, hand the critical component to a certified provider, take that project out of the method or, where Running above the qualified level allows it, let the project run by decision.

**4. §14.1, Level 0 · Organisation.** Community-maintained section. It follows from decisions 5 and 6: level 1 requires the owning organisation to be identified, and a project whose liability lies with the organisation cannot be owned and answered for by the adopter. The Human Manager confirmed it (decision 12).

> Old: **Level 0 · Organisation.** The adopter MUST be the owner of the project and of what it produces, and answers for both (§4).
>
> New: **Level 0 · Organisation.** The adopter MUST be the owner of the project and of what it produces, and answers for both (§4), except that a project that runs above the qualified level under a mandate of the organisation (§14.2) is owned, with what it produces, by that organisation, which answers for both.

**5. §4, Liability towards third parties.** One sentence is added after "without it the project stays at level 0."; the rest of the paragraph is unchanged.

> New: For a project that runs above the qualified level under a mandate of the organisation (§14.2), liability towards third parties lies with that organisation.

**6. §5, Deny.**

> Old: **Deny.** The environment, not the agent, MUST block an action that the mandate forbids or that lies outside the adoption level, and MUST record why. The AI Coordinator MUST look for an authorised alternative; if there is none, it MUST suspend the affected work.
>
> New: **Deny.** The environment, not the agent, MUST block an action that the mandate forbids or that lies outside the adoption level, and MUST record why. For a project admitted under §14.2 (Running above the qualified level), class 1 takes the place of the adoption level, unless a requirement of level 1 that the paragraph makes due is due and not met; while work goes on only on test data under Questions for the organisation (§14), with or without the decision of §14.2, the environment MUST also block any data other than test data, masked data included, and every release. The AI Coordinator MUST look for an authorised alternative; if there is none, it MUST suspend the affected work.

**7. §5, Do.** The last item of the list changes.

> Old: - changes of project class and adoption-level upgrades. Downgrades are automatic (§14.2).
>
> New: - changes of project class, adoption-level upgrades and the decision to run a project above the qualified level. Downgrades are automatic (§14.2).

### The Security Officer

Items 8 to 14 come from CR-014. Items 8 to 13 are in §14, a community-maintained section; item 14 is in §7.

**8. §14, Applicability gate.**

> Old: **Applicability gate.** An AI compliance role MUST assign the class, using a versioned checklist qualified by the maintainers. The gate MUST run when the project opens, at every Wave and at every change of mandate. If an exclusion criterion is triggered, or the case is in doubt, the project MUST be treated as out of scope and the Human Manager informed.
>
> New: **Applicability gate.** The Security Officer, an AI compliance role under its own qualified Role Profile, MUST assign the class, using a versioned checklist qualified by the maintainers. The AI Coordinator MUST invoke the Security Officer and MUST NOT assign the class itself. The gate MUST run when the project opens, at every Wave and at every change of mandate. If an exclusion criterion is triggered, or the case is in doubt, the project MUST be treated as out of scope and the Human Manager informed; when the only doubt is a question for the organisation not yet answered, the work on test data that Questions for the organisation allows MAY go on.

What changes: the role is named and the AI Coordinator may no longer classify. What is kept: the checklist, when the gate runs, and the rule for exclusions and doubtful cases, with the one exception of item 11.

The five paragraphs below are added after **Applicability gate**, before **Legal advice**.

**9. §14, new paragraph Risk profile.**

> New: **Risk profile.** When the class exceeds the qualified level, or an exclusion criterion is triggered, the Security Officer MUST deliver a risk profile of the project: the class with the answers to the checklist, the exclusions touched, the treatments it proposes in order of preference, the class after each treatment, its conditions, the residual risk and what remains impossible. A proposal whose class after treatment still exceeds the qualified level MUST say that it does not let the project start at that level; for a project of class 1 in an adoption at level 0 with no exclusion criterion triggered and the class not in doubt, it MUST also say that the decision of §14.2 (Running above the qualified level) is available and what it requires or, when the only doubt is a question for the organisation not yet answered, that the decision is available only for the work on test data that Questions for the organisation allows.

**10. §14, new paragraph Treatments.**

> New: **Treatments.** A treatment is a concrete form of the options of Class change (§14.2) other than running by decision: taking data or functions out of scope; building and testing only on test or masked data; keeping real data within the local execution of those already entitled to process them, never sent to agents or external services. A treatment MUST NOT be presented as a way past a case that is out of scope at any level; the only treatment of such a case MUST be to take the excluded data or function out of scope, and the reduced scope is a new scope that MUST pass the gate again.

**11. §14, new paragraph Questions for the organisation.**

> New: **Questions for the organisation.** For the questions of the checklist whose answer belongs to the organisation and not to the Human Manager, such as obligations under network and information security law, a data protection impact assessment, sector-specific regulation or the data protection officer, the Security Officer MUST say who can answer and MUST prepare the question to forward. An answer given by the Human Manager alone MUST be recorded as not verified and MUST NOT be taken as resolving the question. Until the organisation answers, the case MUST be treated as in doubt (Applicability gate). In the meantime, if no exclusion criterion is triggered, work MAY go on only on test data, with no real data and no release, within the class that the qualified level permits or under the decision of §14.2 (Running above the qualified level).

**12. §14, new paragraph Dialogue with the Human Manager.**

> New: **Dialogue with the Human Manager.** The Human Manager MAY question the Security Officer at any time, through the AI Coordinator. The AI Coordinator answers for the form, in business language, and MUST NOT alter the content. The original risk profile MUST be attached unchanged in the Manager View.

**13. §14, new paragraph Independence of the Security Officer.**

> New: **Independence of the Security Officer.** The Security Officer proposes and MUST NOT act as a reviewer. The roles of security reviewer and privacy reviewer MUST stay independent of it and MUST NOT be held, on the same project, by the Security Officer or by an agent instantiated from its Role Profile. The Security Officer SHOULD run on a model different from the AI Coordinator's where one is available.

**14. §7, Hard blinding.** The last sentence changes; the rest of the paragraph is unchanged. §7 is not a community-maintained section.

> Old: **Hard blinding.** Under hard blinding, the environment MUST give the agent only the files, tools and data of its role, with no retrieval outside that perimeter (§11), and a binding prompt MUST constrain its behaviour. A local model without retrieval MAY be used. Hard blinding MUST apply to the AI Coordinator, the AI Reviewer, the Design Thinking Facilitator, the Discovery reviewers and the Discovery judge (§8).
>
> New: **Hard blinding.** Under hard blinding, the environment MUST give the agent only the files, tools and data of its role, with no retrieval outside that perimeter (§11), and a binding prompt MUST constrain its behaviour. A local model without retrieval MAY be used. Hard blinding MUST apply to the AI Coordinator, the AI Reviewer, the Design Thinking Facilitator, the Discovery reviewers, the Discovery judge (§8) and the Security Officer (§14).

### Paragraphs that do not change, and why

- **§14, Deliverables.** Unchanged. The class of a deliverable counts in the class of the project, and the exception applies to that class within its limits: documents for colleagues are class 1 and can be produced by a project admitted under item 2; the example of the paragraph (a level 0 adoption producing documents for customers, which are class 2) stays forbidden.
- **§14, Out of scope at any level** and **Legal advice.** Unchanged. No treatment and no decision passes an exclusion; the risk profile is not legal advice.
- **§14, Applicability gate**, rule on exclusions and doubtful cases. Kept by item 8: the gate still treats a doubtful case, or a case with an exclusion criterion, as out of scope, except for the work on test data of item 11. The exception of item 2 starts from the class the gate assigns and excludes every case the gate treats as out of scope, except that, while the only doubt is a question for the organisation not yet answered, the decision can cover the work on test data of item 11 alone.
- **§4, Specialist AI roles.** Unchanged: like the AI Coordinator and the AI Reviewer, the Security Officer is defined with its own qualified Role Profile in its own paragraph (item 8).
- **§8, Discovery executors and reviewers.** Unchanged: the security and privacy reviewers of the Discovery group are the reviewers of item 13, not the Security Officer.
- **§14.1, requirements of level 1 and level 2.** Unchanged. Item 2 refers to the Method and Organisation requirements of level 1 as they are.
- **§14.2, Moving up** and **Automatic downgrade.** Unchanged. Item 2 refers to both. The permitted class of the project is class 1; while a requirement of level 1 that item 2 makes due is due and not met, it is the class of the qualified level, and only corrective releases may run; once the requirement is met, the permitted class is class 1 again.
- **§9, Project record** and **§12, Third-party evidence pack.** Unchanged: they already list the class and the adoption level; item 2 adds the declaration to both.
- **§4, Internal accountability.** Unchanged: "qualified scope" is read as the scope that §14 allows, the decision of §14.2 included; the Human Manager answers for that decision (decision 4).
- **§12, Writing rules.** Unchanged: the document for the Human Manager is the AI Coordinator's rendering in business language; the original risk profile attached in the Manager View is its evidence (§12, Evidence).
- **§3, context principles.** Unchanged. The class is still assigned by an AI compliance role, now named; the Human Manager accepts a business risk and does not stand in for the AI roles.

## Reversibility

A change to the Guide text is a one-way door (GOVERNANCE §6.2). This one relaxes a prohibition: for a version in force it would be a MAJOR change under VERSIONING §2.1. While the Guide is a release candidate, not in force, rolling back costs a new candidate that restores the rc.3 text of items 1, 3 to 8 and 14 and drops items 2 and 9 to 13. Projects started under the exception would then have to move up, reduce their scope or leave the method.

## Impact

- **Adopters.** An adopter at level 0 can start a class 1 project by a recorded decision. All the Method requirements of level 1 are due, and with personal data of colleagues the Organisation requirements too, so the work is that of level 1; what is saved is the waiting time needed to gather evidence at level 0 first. A class 2 project cannot start from level 0, and an adopter at level 1 gains nothing from this RFC. Projects with special categories of data, children's data, automated decisions on people and the other cases out of scope stay out, whatever the decision.
- **What the method promises.** Until now the levels limited risk before the project started, with no exception. After this RFC the limit can be passed by one class, from level 0, by a person who may not be able to assess the risk they accept; the safeguards are the requirements of level 1, the organisation's mandate and liability for colleagues' data, and the written declaration.
- **Role Profiles.** AI Coordinator: it invokes the Security Officer instead of classifying, and carries the dialogue with the Human Manager without altering its content; when the gate assigns class 1 in an adoption at level 0, it presents the Do of item 2 instead of stopping; it sees that the Method requirements of level 1 are met before the first release, and that no personal data of colleagues are processed before all the Method and Organisation requirements are met; it records the decision and the declaration; it reports the state at every cycle review and proposes moving up. Security Officer: a new Role Profile, today a local draft; it assigns the class, assumes the higher class when the class is in doubt, delivers the risk profile and prepares the decision of item 2. Security and privacy reviewers: unchanged, and distinct from the Security Officer. Released separately.
- **Qualified profiles.** Level 1 requires security and privacy profiles qualified for class 1, and today every Role Profile is a draft. By decision 8 the project that maintains the method extends its recorded deviation: a project admitted under item 2 uses the draft profiles and declares it in the Do. The Guide text does not change on this point. By a further decision of the Human Manager (Do-S25 of the scope register), the same deviation covers the Security Officer in every project, class 0 included, until its Role Profile is qualified; it applies from the candidate that includes this RFC and is declared in each project: without it, no project could be given a class once item 8 is in force.
- **Tools.** The Manager View and the project record show that the project runs above the qualified level; the Manager View carries the original risk profile.
- **Cost.** One more agent at every run of the gate, that is at the opening of the project, at every Wave and at every change of mandate; a risk profile whenever the class exceeds the level or an exclusion is triggered.
- **Test bench.** Of the three requests of the bench, the class 1 request without special categories of data starts after the recorded decision, with the draft profiles declared in the Do (decision 8); it works on test or masked data until all the Method and Organisation requirements of level 1 are met, the organisation's mandate included; its release waits for the Method requirements of level 1; the class 2 request cannot start from level 0; the request with special categories of data stays excluded.
- **Translations.** None published yet.
- **Version.** A prohibition is relaxed and obligations are added. The Guide is a pre-release of 1.0.0, not in force, so the change is released as the next candidate, rc.4.

## Alternatives

- **Do nothing.** A departmental project cannot start from level 0. The adopter has to gather evidence at level 0 first, or leave the method for that project. This keeps the strongest protection and the least usefulness for the people the method is meant for.
- **Write the exception for any level, one level above.** Not chosen (decision 1, as confirmed): level 0 and class 1 only. From level 1 to class 2 the project is exposed to the Internet and holds data of third parties, and the evidence that level 2 requires includes a penetration test of the release itself, which is not experience at the lower level.
- **Let the decision pass the exclusions too.** Not chosen (decision 2): they are limits of law or safety that do not depend on the level.
- **Waive the requirements of level 1 and only declare what is missing.** Not chosen (decisions 3 and 5): the data of colleagues would have no protection guaranteed by the method.
- **Keep liability with the individual.** Not chosen (decision 6): the data belong to the organisation.
- **Accept a yes in the conversation, without a record.** Not chosen (decision 4): the decision could not be shown to third parties.
- **Do not count the experience gathered above the level.** Not chosen (decision 7): moving up would stay out of reach for those who work only on departmental projects.
- **Count a preview given to colleagues as the first release.** Not chosen (decision 15).
- **Require an independent check before the decision,** as Moving up does for the evidence. Not chosen (decision 11).
- **Require every protection before the project starts.** Not chosen (decision 9): some can be tested only on a product that exists.
- **Put the Security Officer in a separate RFC.** Not chosen by the Human Manager: the role and the decision it prepares belong together, and §14 would be changed twice.
- **Leave the list of treatments to the Extended Framework.** Possible: item 10 states the three treatments in the Guide because CR-014 names them; the working groups may move the detail later.
- **Change only the AI Coordinator profile.** Not possible: a profile that lets the project start would contradict §14, and an implementation MUST respect the rules of the Guide (§15).
- **Declare the data of the test bench fictitious and its requests class 0.** It would let the bench run without changing the method, but it does not answer the question for real departmental projects. It remains available to the bench.

## Acceptance evidence

- `tools/release_diff.py` from `v1.0.0-rc.3` to the candidate: every removed line is the "Old" text of items 1, 3, 4, 6, 7, 8 and 14, or the rc.3 paragraph that item 5 extends; no heading removed.
- `TRACEABILITY.md`: all earlier rows kept; one row per new or changed paragraph, marked "RFC 0004".
- Independent scope review: every change maps to CR-013 or CR-014 and to one of the decisions listed under Motivation or, for items 8 to 14, to decisions 16 to 19 and to D-SO-1 to D-SO-3, the extension of 26 November and the decision to put the role in this RFC, all recorded in CR-014; the exclusions of §14 are untouched; no conflict with §3, §7, §12, §13 and §15.
- A run of the test bench with a kit that implements the change: a class 1 request starts after the recorded decision, with the organisation's mandate and with the draft profiles declared in the Do (decision 8); a class 2 request and a request with a case out of scope do not start; a release without the Method requirements of level 1, and processing of colleagues' data before all the Method and Organisation requirements are met, are denied; a lapsed requirement applies Automatic downgrade; for a request above the level the Security Officer delivers a risk profile with treatments, and no treatment admits a case out of scope; the AI Coordinator does not assign the class; a question for the organisation left unanswered, or answered by the Human Manager alone, keeps the case out of scope, while work on test data goes on and real data and release are denied; a preview on test or masked data runs before the Method requirements are met; the Security Officer runs under hard blinding; during the wait masked data are denied, and a decision taken during the wait admits only work on test data; the Manager View carries the original risk profile unchanged; no security or privacy reviewer role is held by the Security Officer.
- The Author's decision on this RFC, with written reasons, before the release Do.

## Open questions

The questions of the earlier drafts were decided by the Human Manager on 2026-11-26 (decisions 9 to 19 under Motivation, and the deviation on the draft profile of the Security Officer). Still open, or stated as consequences so that they are seen:

- **Class 1 without personal data of colleagues.** In that case item 2 asks for no mandate, and the project starts on the decision of the Human Manager alone, who keeps ownership and liability. The same holds for every admitted project until the mandate is given: ownership and liability move to the organisation from that moment (items 4 and 5). It is a consequence of the decisions, stated here so that it is seen. Because authentication through the corporate identity is a Method requirement, the first release in practice processes personal data of colleagues and needs the mandate.
- **Previews.** By decision 15 a preview is not a release, and by decision 14 it runs on test or masked data until all the protections are in place. Signing in with the corporate identity processes personal data of colleagues, so a preview with real sign-in falls under decision 14.
- **Who masks the data.** Masking real data is itself a processing of those data. Item 2 does not say who may produce the masked data; item 10 suggests it is whoever is already entitled to process the real ones.
- **A lapse after release.** When a requirement lapses after release, the text does not say whether processing in operation stops or only non-corrective releases do.
- **After the organisation answers.** Item 2 asks for a new decision to go beyond the work on test data. If the Human Manager wants the first decision to be enough, the text has to say so.
- **Name of the role.** "Security Officer" is the name the Human Manager used; the Italian name and the working group that owns the profile are open in CR-014.

The comment period and the community-maintained sections were decided at acceptance as two recorded deviations (Decision).

## Decision

**Accepted**, on 2026-11-26, by the Author (Do-S26).

Written reasons: a method meant for business people has to let a departmental project start when the person who answers for it accepts the risk knowingly; the limits decided keep the protections of level 1, the organisation's mandate and the exclusions, and the Security Officer makes the decision an informed one. No community member is active yet; founding contributors may reopen any item with a new RFC.

**Deviation from the comment period.** The decision was taken before the end of the comment period (2026-12-26), which `rfcs/README.md` sets at thirty days for the relaxation of level requirements. The deviation is recorded here and in the changelog; it does not change the process for later RFCs.

**Deviation for community-maintained sections.** Items 1 to 4 and 8 to 13 change §14, §14.1 and §14.2, which their working groups propose. The groups do not exist yet, so the Steward proposed the text and the Author accepted it, as for RFC 0001 and RFC 0003. The working groups may revise it by RFC once they are formed.

**Left open at acceptance** (Open questions): the name of the role in Italian and the working group that owns its profile; who masks the data; what stops when a requirement lapses after release; whether a new decision is needed after the organisation answers, as item 2 now requires.

**Implementation.** The items are applied in candidate 1.0.0-rc.4 of the Guide.
