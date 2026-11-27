<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# RFC 0006: The managerial role in security, measuring the method against a baseline, and a method that feeds itself

- **Author(s):** the Author, by request; text drafted by the AI Coordinator
- **Accountable human:** Paolo Ungari (Author)
- **AI-Use:** substantial (CONTRIBUTING.md §3)
- **Assisted-by:** Claude Opus 5.5 (drafting)
- **Conflicts of interest:** none
- **Owner of the decision:** Author (Guide)
- **Affected artifacts:** Guide title block (Status), §2 (Why Eiraman exists; new paragraph The method applies to itself), §15 (new paragraph Measuring the method); `TRACEABILITY.md`. After acceptance, in separate releases: the Extended Framework (Guidance on measurement), the Italian translation, and the site and kit where they present why Eiraman exists
- **State:** accepted
- **Dates:** opened 2026-11-27 · comment period ends 2026-12-27 · accepted 2026-11-27, before the end of the comment period (deviation, see Decision)
- **Change request:** CR-031 of the project "Eiraman Open Framework"; decided by D-031 and, for its extension, by D-031-B

## Summary

The RFC covers three themes.

**A. The managerial role extends to security** (D-031). The paragraph "Why Eiraman exists" (§2) gives one reason for the method: the limits of human-in-the-loop and human-on-the-loop control where there is no development team. This RFC adds a second one. Vibe coding sharply increases the data people handle, often without the competence needed to see the risks. In Eiraman a Human Manager who delegates a task knows what that choice implies for security, privacy and regulatory compliance. For one's own use this knowledge is, by default, information; in work and organisational contexts it is blocking by default: the adoption levels and the Applicability gate stop what the qualified level does not allow, except what the Human Manager decides to run above it under the conditions of §14.2 (Running above the qualified level). The mechanism already exists in Guide 1.0.0-rc.5 (§12, §14); this part adds no rule.

**B. Measuring the method** (D-031-B). A new descriptive paragraph of §2 states that the method treats each of its rules as a hypothesis and measures its own effects against a baseline, the same tasks carried out without the method. A new normative paragraph of §15, **Measuring the method**, binds those who maintain the method, not adopters: every version of the Guide, with the Extended Framework, Role Profiles and Tools released with it, is measured on a test bench against a declared baseline, the simplest configuration without the method, under equal conditions and with isolated runs; a version released before its campaign is completed declares itself "not measured"; bench testing takes the delivery as it is and records faults, with testers independent of the developers; requests, briefs and expected results are written by others than the maintainers, frozen before the campaign and hidden from the measured agents, and judged indicators follow K1; hypotheses, margins and repetitions are fixed before a campaign and every result is kept and counted; a test that removes a rule without a benefit above the margin leads to a proposal to reduce or remove it, and when the baseline is shown to obtain the same result at a lower cost for a class of project, the Guide says so and indicates the baseline; "not demonstrated" is enough for neither. Bench testing is distinguished from the acceptance testing of §9.1. Indicators, applications, repetitions, limits and the concrete baseline go to the Extended Framework as Guidance. The title block declares this candidate "not measured".

**C. A method that feeds itself** (D-031-B). The same paragraph of §2 states that the method evolves by applying itself: the Human Manager gives the direction, the agents translate it by the principles of the method into change requests, specific choices and suggestions, and the Human Manager decides through Do escalations.

This candidate, 1.0.0-rc.6, is itself **not measured**: no measurement campaign has been completed.

## Motivation

### A. Security

The Human Manager, who is also the Author of the Guide, asked on 27 November 2026 (CR-031):

> Il ruolo manageriale di Eiraman si esplicita anche nella sicurezza. Un altro dei grandi problemi del Vibe Coding è che nello sviluppare applicazioni aumentiamo considerevolmente la quantità di dati che gestiamo, spesso senza avere le competenze necessarie per capire i rischi. In Eiraman un manager umano che demanda lo sviluppo di un task sa quali implicazioni ha questa sua scelta da un punto di vista di sicurezza, privacy e compliance normativa. Questo in usi privati è una sola informazione ma diventa bloccante in contesti di lavoro e di organizzazioni. Questa è una modifica da considerare già nel «Perché esiste Eiraman».

In English:

> The managerial role of Eiraman is made explicit in security too. Another of the great problems of vibe coding is that, in developing applications, we considerably increase the amount of data we handle, often without the competence needed to understand the risks. In Eiraman a human manager who delegates the development of a task knows what implications this choice has from the point of view of security, privacy and regulatory compliance. In private use this is only information, but it becomes blocking in work and organisational contexts. This is a change to be considered already in "Why Eiraman exists".

The request continues an earlier statement of the Human Manager (CR-015, 26 November 2026): in organisations many people build small personal applications with AI without being aware of the data they handle and of the risk they are exposed to, the theft of the device being an example; the adoption levels and the check at the opening let them work consciously and limit the risk.

Since 1.0.0-rc.1 "Why Eiraman exists" speaks only of the limits of point control. RFC 0005 made the classification work in two modes and changed the item *Scope and risk management* of "Management applied to AI", but the reason the method gives for existing still says nothing of data and security. A reader who stops at §2 does not learn that the Human Manager's role covers them.

### B and C. Measurement and self-feeding

On 27 November 2026 the Human Manager extended the RFC (D-031-B):

> (a) Nella RFC 0006 includiamo anche la Test Board ed il processo di Collaudo con il principio che Eiraman deve misurare i propri effetti comparandosi con una baseline che oggi è fissata sul duo Opus+Sonnet.
>
> (b) Un altro principio che vorrei inserire è che Eiraman è un Framework che si "autoalimenta". Sostanzialmente quello che stiamo facendo. Io ti propongo un'idea e tu applicando i principi del framework la traduci in scelte puntuali e suggerimenti. In un rapporto "manager" che da la linea guida e team che la mette in atto.

In English:

> (a) In RFC 0006 let us also include the Test Board and the testing process (*collaudo*), with the principle that Eiraman must measure its own effects by comparing itself with a baseline that is today set on the Opus+Sonnet pair.
>
> (b) Another principle I would like to include is that Eiraman is a framework that "feeds itself". Essentially, what we are doing. I propose an idea to you and you, applying the principles of the framework, translate it into specific choices and suggestions. In a "manager" relationship, that gives the guideline, and a team that puts it into practice.

The Human Manager also decided that the decision of 26 November 2026, which kept the rules on measuring the method (B1 to B11 of the working copy of specification 0.3, never published) out of the Guide until the test bench had completed a campaign (RFC 0003, "Not included"), is **replaced**: the principle enters the Guide, without names of providers (PA-3); the concrete baseline and the pilots go to the Extended Framework. Rule B12, the governance share, is already in the Guide (§8, Governance cycle, RFC 0003 item 15).

The sources of part B are the section "Misura del metodo" of the working copy of specification 0.3 (rules B1 to B12), the design of the test bench (the measure of the cost of realignment, the "two doors" rule, the indicators, the hypotheses) and the bench in use: its Test Board, protocol, the fixed instructions of the baseline and the instructions of the testers. State of the bench at this RFC: only the first cycle of the pilots has been run, with no repetitions; the round prepared for candidate rc.5 has not been launched; no campaign has been completed.

The Guide so far says that projects test the method (§1, Projects; §15, Feedback into the method) but not that the method is measured, against what, or what follows when a simpler configuration does as well. And it does not say how the method itself evolves, although the method is developed as an Eiraman project (PA-4): the Human Manager gives a direction and the agents translate it into change requests and choices, as this RFC shows.

## Proposal

### A. §2, Why Eiraman exists

In §2, at the end of the paragraph **Why Eiraman exists**, after "and the AI system answers with evidence.", add:

> Vibe coding also sharply increases the data people handle, often without the competence needed to see the risks. In Eiraman the managerial role extends to security: a Human Manager who delegates a task knows what that choice implies for security, privacy and regulatory compliance, because the classification of the project and the Security Officer make it known (§14). When the adopter uses the method for themselves, this knowledge is, by default, information, recorded in the Security Report (§12); in work and organisational contexts it is blocking by default: the adoption levels and the Applicability gate stop what the qualified level does not allow, except what the Human Manager decides to run above it under the conditions of §14.2 (§14, Classification mode).

Notes on the text:

- "blocking by default" follows §14, Classification mode: without a choice the informative mode applies when the adopter uses the method for themselves and the blocking mode in every other case, doubt included; the Human Manager may choose the informative mode, unless the rules of the organisation impose the blocking one. "Binding" without qualification would have contradicted that rule.
- "by default" in the first half follows the same rule: for one's own use the informative mode applies only when no mode is chosen, and the Human Manager may choose the blocking one.
- "except what the Human Manager decides to run above it" follows §14.2, Running above the qualified level: in the blocking mode a class 1 project may run in an adoption qualified at level 0 by an explicit, recorded decision of the Human Manager, and no other class or level. Without the exception the sentence would have contradicted that rule.
- The text carries no RFC 2119 key word: §2 is theory, and the rules it points to are in §12 and §14.
- It names no provider, product or jurisdiction (PA-3, PA-11).
- The item *Scope and risk management* of "Management applied to AI" already says that the adoption levels "limit risk up front or, in the informative mode, make it known" (RFC 0005). It is consistent with the new text and is not changed.

### B and C. §2, new paragraph after "Management applied to AI"

> **The method applies to itself.** Eiraman treats each of its rules as a hypothesis and measures its own effects against a baseline: the same tasks carried out without the method (§15, Measuring the method). It also feeds itself: it evolves by applying itself. The Human Manager gives the direction; the agents translate it, by the principles of the method, into change requests, specific choices and suggestions, and put it into practice; the Human Manager decides through Do escalations (§5). Projects feed it in the same way, through what their development teaches (§1, Projects; §15, Feedback into the method).

Notes on the text:

- **Own label.** The two principles are about the method itself, not about the problem it answers ("Why Eiraman exists") nor about one practice it transposes (the list of "Management applied to AI"). A paragraph of their own keeps both readable and gives them one traceability row; it stays in §2 because it is theory.
- No RFC 2119 key word: the rules are in §15. "Change requests" is used in its ordinary sense; the Guide defines no term for it.

### B. §15, new paragraph before "Changing the method"

> **Measuring the method.** Every rule of the method is a hypothesis until a measurement supports it. This paragraph binds those who maintain the method, the Author for this Guide and the Maintainers (§4) for the Extended Framework and, with them, the Role Profiles and Tools; it sets no obligation on adopters. Each version of this Guide, with the Extended Framework, the Role Profiles and the Tools released with it, MUST be measured on a test bench against a declared baseline; a release of one of them that does not change the Guide is covered by the campaign of the version of the method that includes it. A version MAY be released before its measurement campaign is completed, and it MUST then declare itself "not measured" in its status. The baseline is the simplest configuration without the method: two agents, one at a Digital Seniority (§7) suited to design and one at a lower Digital Seniority suited to implementation, with no AI Coordinator, no reviewer and a single candidate; the Extended Framework names the levels and the models. The baseline and the configurations compared with it MUST receive the same request, the same files and tools, the same simulated Human Manager, an agent that plays the Human Manager, and the same limits of time and cost; each run MUST be isolated from the others, and a run beyond the limits counts as failed. The baseline MUST be run again at every change of model, and a comparison MUST be made only between runs with the same models. Bench testing MUST take the delivery as it is: the testers follow the delivered instructions literally and do not make up with their own ability for what is missing, and they MUST record as a fault, that is, any failure of the delivery to do what its instructions say or what was asked, everything that does not work. The testers MUST be independent of those who developed the delivery and SHOULD NOT use models more capable than those under measurement. Seniority of the verifier (§6) does not apply to them. The requests, the briefs of the simulated Human Manager and the expected results of the tests MUST be written by someone other than those who maintain the method, and MUST be frozen before the campaign; the measured agents MUST NOT see the briefs or the expected results. An indicator that a model judges MUST follow K1 (§6). Bench testing measures the method; it is distinct from the acceptance testing of §9.1, in which a person performs the business task of a project and the Human Manager decides on acceptance, and neither replaces the other. The hypotheses of a campaign, each with its primary indicator, its margin and its number of repetitions, MUST be recorded before the campaign and MUST NOT change after it; every result MUST be kept and counted, unfavourable, failed and interrupted runs included. When a test that removes a single rule excludes, with the repetitions declared before the campaign, a benefit above the declared margin, whoever coordinates the work on the method MUST propose to the Human Manager to reduce that rule to Guidance or to remove it. When a completed campaign demonstrates, within the declared margin, that for a class of project the baseline obtains the same result at a lower cost, the Author MUST state it in this Guide and indicate the baseline for that class; the conclusion holds only for the classes the bench represents. An outcome of "not demonstrated" is enough for neither. The Extended Framework gives as Guidance the indicators, what counts as the same result, the measure of the cost of realignment, the test applications, the number of repetitions, the limits and the models of the baseline.

Notes on the text:

- **Who it binds.** The Author and the Maintainers (§4), as §4 Maintainers and §15 Changing the method already bind actors other than an application. It sets no obligation on adopters, so the conformance of an application (§15, Conformance) does not depend on it.
- **Scope.** A campaign measures a version of the Guide together with the Extended Framework, Role Profiles and Tools released with it, since together they are what an adopter runs; a release of one of them that does not change the Guide is covered by the campaign of the version that includes it, so that every profile release does not need a campaign of its own.
- **MUST and SHOULD.** The rules that make a comparison valid are MUST: a declared baseline under equal conditions (request, files and tools, simulated Human Manager, limits) and isolated runs (B6); a new baseline run at every change of model and comparisons only between the same models (B2); delivery taken as it is, faults recorded, testers independent of the developers (B4); requests, briefs and expected results written by others than the maintainers, frozen and hidden from the measured agents, and judged indicators under K1 (B9, B4); hypotheses with indicator, margin and repetitions fixed before, every result kept and counted (B8); the proposal to reduce or remove a rule and the statement on the baseline, both under the standard of proof of B11. Without any of these a result cannot be trusted, is biased or is lost. "A run beyond the limits counts as failed" and "Seniority of the verifier does not apply" carry no key word: they define how a rule applies. The capability of the testers is a SHOULD NOT: a ranking of capability between models is not always determinable, and a project that departs from it records the reason (§0). Seniority of the verifier (§6) would require testers at least at the seniority of the executor, which is what the bench must avoid: a tester more able than an office user makes an unusable delivery pass.
- **Digital Seniority of the baseline.** The Human Manager did not fix the levels; the paragraph says only that the designer works at a seniority suited to design and the implementer at a lower one, and leaves levels and models to the Extended Framework. The release before a completed campaign is a MAY, so that the obligation to measure does not block every release; the MUST on "not measured" makes it visible.
- **Values in the Extended Framework.** Indicators, what counts as the same result, the measure of the cost of realignment, the test applications, the number of repetitions, the limits and the models of the baseline are values or tools (§0, Values and Guidance; PA-2, PA-3).
- **Bench testing and acceptance testing.** On the bench a tester follows the delivered instructions literally and records faults; in a project, under §9.1, a person performs the business task, the AI records, and the Human Manager decides on acceptance. The paragraph states the difference so that neither is taken for the other.
- **Not included** in the Guide, and left to the Extended Framework: confidence intervals and the test of a threshold (B7; the Guide keeps the standard of proof of B11 in words: "excludes", "demonstrates within the declared margin", "not demonstrated"); the calibration of the judges on human judgements beyond K1 and the tuning of difficulty on another variant (B9, B4); the content of the run record (B10, already partly in §11, Run traceability); the declaration "not measured" in the record of each project (B1), which would bind adopters; the campaign as a Wave of the method project with its launch as a Do.

### Title block

> **Status.** Release candidate, not yet in force, not measured (§15, Measuring the method). The Author ratified its editorial choices on 25 November 2026; they are listed in `AUTHOR-RATIFICATION.md`.

## Reversibility

A change to the Guide text is a one-way door (GOVERNANCE §6.2). Part A and the paragraph of §2 are descriptive. The paragraph of §15 adds obligations for those who maintain the method: for a version in force it would be a MINOR change under VERSIONING. While the Guide is a release candidate, rolling back costs a new candidate that removes the added sentences and paragraphs and the words "not measured" from the status.

## Impact

- **Normative.** The new paragraph of §15 is normative for the Author and the Maintainers. RFC 2119 key words in `EIRAMAN-GUIDE.md`, from 1.0.0-rc.5 to 1.0.0-rc.6: MUST 350 → 366, MUST NOT 66 → 68, SHOULD 7 → 7, SHOULD NOT 2 → 3, MAY 37 → 38; all the changes are in §15 (MUST 12 → 28, MUST NOT 2 → 4, SHOULD NOT 0 → 1, MAY 2 → 3). Part A, the new paragraph of §2 and the status carry no key word.
- **Adopters.** No new obligation. The Guide states up front that the role of the Human Manager covers security, privacy and compliance implications, that the method is measured and that it evolves by applying itself.
- **Maintainers and the Author.** Each version needs a campaign on the test bench or the declaration "not measured". This candidate declares it.
- **Role Profiles.** None to requalify.
- **Extended Framework.** A new Guidance on measuring the method: the concrete baseline, the Test Board and the pilots, the indicators, the "two doors" rule and the measure of the cost of realignment, repetitions and confidence intervals, the values of the limits, run records, the tester instructions and the brief of the simulated Human Manager. It is being prepared as `guidance/BENCH.md` in the framework candidate 0.3.0.
- **Tools.** None in this release; the bench tools stay in the bench repository.
- **Translations.** The Italian translation (`translations/it/`, 1.0.0-rc.5+it.1) must translate the changes and move to 1.0.0-rc.6+it.1.
- **Site and kit.** Where they present why Eiraman exists or claim results, they say that the version is not measured.
- **Version.** Obligations are added. The Guide is a pre-release of 1.0.0, not in force, so the change is released as the next candidate, rc.6.

## Alternatives

### A

- **Do nothing.** The theory keeps giving one reason only, and the reader meets security first as a set of rules in §14.
- **A paragraph of its own in §2.** Not chosen: the Human Manager asked for the change in "Why Eiraman exists".
- **A rule in §2 with a key word**, for example that the Human Manager MUST know the implications of delegating. Not chosen: §2 has been theory since rc.1, and the rules that make the implications known are already in §12 and §14.
- **A new context principle in §3.** Not chosen: the mechanism exists; what was missing is the reason.
- **"Binding" in organisations without qualification**, as the request reads. Not chosen: in the Guide the Human Manager may choose the informative mode unless the organisation imposes the blocking one, and may run a class 1 project above the qualified level under §14.2.
- **Change the item *Scope and risk management* too.** Not needed: it already matches.

### B and C

- **Keep measurement out of the Guide until a campaign is completed** (the decision of 26 November 2026). Replaced by D-031-B.
- **Name the concrete baseline in the Guide.** Not chosen: PA-3 excludes provider names, and the baseline changes with the models; it goes to the Extended Framework.
- **Carry rules B1 to B11 whole into the Guide.** Not chosen: the Guide carries their principles, B2, B4, B6, B8, B9 and B11 included, while values, procedures and tools of the bench go to the Extended Framework (§0, Values and Guidance).
- **Keep the first half of B11 and the parity of B6 in the Extended Framework**, as in the first draft. Not chosen after the independent review: without them a rule could survive a campaign that shows it useless, and a comparison could rest on unequal conditions.
- **Apply Seniority of the verifier to bench testers.** Not chosen: a tester as able as the executors would make up for what the delivery lacks.
- **Make measurement binding on adopters**, for example the declaration "not measured" in every project record (B1). Not chosen: the Human Manager asked for a principle of the method; adopters already report the governance share (§8).
- **Put the two principles in "Why Eiraman exists" or in the list of "Management applied to AI".** Not chosen: see the notes on the text.
- **Use "acceptance testing" for the bench.** Not chosen: in the Guide acceptance testing is done by a person (§9.1); the bench takes the delivery literally with agents.

## Acceptance evidence

- `tools/release_diff.py` from `v1.0.0-rc.5` to the candidate: in `EIRAMAN-GUIDE.md` the changed lines are the version label, the status, the paragraph Why Eiraman exists (old text kept whole) and the two new paragraphs; no heading removed or renamed; RFC 2119 counts change only in §15, as listed under Impact.
- `TRACEABILITY.md`: all earlier rows kept; one row per new or changed paragraph, marked "RFC 0006", normative or descriptive.
- No provider, product or jurisdiction named in the Guide.
- Independent review of the diff against the changelog, CR-031, D-031 and D-031-B.
- The Author's approval of the final text at the publication Do.
- Not available: a completed campaign. This candidate is "not measured".

## Open questions

- **Wording.** The direction is decided (D-031, D-031-B); the Author approves the final text at the publication Do.
- **Comment period.** The paragraph of §15 concerns the maintenance of the method, close to governance; in doubt the thirty-day period applies, ending 2026-12-27. An earlier decision is a deviation to record, as for the earlier RFCs.
- **First campaign.** When it is completed, the status of the Guide changes by a new release, and the statement on the baseline, if any, needs an RFC.
- **One-door choices.** The bench design reports apart the choices that cannot be undone by correcting the program; whether they must be asked first is a decision of the Human Manager not yet taken.
- **Guidance pending.** The Guidance of the Extended Framework on measurement (guidance/BENCH.md) is being prepared in the framework candidate 0.3.0 and is released together with this version; until then the Guide's references to it are pending.

## Decision

**Accepted**, on 2026-11-27, by the Author (D-031; extended by D-031-B): approved direction; final text approval at the publication Do.

Written reasons: vibe coding increases the data people handle, often beyond what they can judge, and the method already makes the implications of delegating known; the reason the Guide gives for existing should say so. A method that treats its rules as hypotheses must show its effects against what the same tasks cost without it, and must say when it is not measured; it evolves the way it asks projects to work, with the Human Manager giving the direction and the agents translating it. The written reasons were drafted by the AI Coordinator from the Author's recorded requests and are confirmed by the Author with the final text, at the publication Do.

**Replaced decision.** The decision of 26 November 2026 that kept rules B1 to B11 out of the Guide until a campaign was completed (RFC 0003, "Not included") is replaced by D-031-B. RFC 0003 is not changed.

**Deviation from the comment period.** The decision was taken before the end of the comment period (2026-12-27). The deviation is recorded here and in the changelog; it does not change the process for later RFCs.

**Implementation.** Applied in candidate 1.0.0-rc.6 of the Guide, which is not measured.
