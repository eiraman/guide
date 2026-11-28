<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# RFC 0008: The AI Manager, bound only by its laws, and a proportionate Discovery and Design

- **Author(s):** the Author, by request; text drafted by the AI Coordinator of change request CR-041
- **Accountable human:** Paolo Ungari (Author)
- **AI-Use:** substantial (CONTRIBUTING.md §3)
- **Assisted-by:** Claude Opus 5.5 (Claude Code)
- **Conflicts of interest:** none
- **Owner of the decision:** Author (Guide); for §7.1, a community-maintained section, the DevSecOps & Tooling and FinOps working groups, which are not yet formed (see Decision)
- **Affected artifacts:** Guide §1, §2, §3, §4, §5, §7, §7.1, §8, §8.1, §9, §12, §13, §14; `TRACEABILITY.md`. In separate releases: the Role Profiles (`governo/manager-ai`, which replaces `governo/interprete`; the AI Coordinator and its cards; the dialect), the Tools, the Extended Framework, the site and kit, and the Italian translation
- **State:** accepted
- **Dates:** opened 2026-11-28 · comment period ends 2026-12-28 · accepted 2026-11-28, before the end of the comment period (deviation, see Decision)
- **Change requests:** CR-035 to CR-040 and CR-041 of the project "Eiraman Open Framework"; decided by D24–D43 and, in CR-041, D-041-A, D-041-B and D-041-D to D-041-I
- **Replaces in part:** [RFC 0007](0007-digital-seniority-pyramid.md), for the Interpreter and for the AI Coordinator's choices on promotion and level
- **Source of the text:** the behaviour tried in the pilots with the registry candidate `role-profiles` `5818b13` (`controllore/`, `governo/manager-ai` 0.5.1, the cards, the step tool and Wire). Under D-041-I the Guide describes that behaviour and adds no rule the kit does not have; what was decided but is not yet in the kit is an open question below.

## Summary

The only channel between the Human Manager and the agents becomes the **AI Manager**: the representative of the Human Manager in the project, omniscient, and bound only by four laws in order of priority (the result within its context, the Human Manager's time, spending, the method). It is the counterweight of a method that otherwise runs on determined flows (D-041-H): the Guide states its laws as MUST and describes its behaviour as their consequence, with no fixed rule beside them. The rest of the method stays deterministic: the AI Coordinator no longer asks for approvals or reviews costs, sends open choices to the AI Manager and executes its derogations; reviewers, Security Officer, judge, phases and gates keep their rules. Discovery and Design and planning become **proportionate and iterative**: the AI Manager decides the roles of the Discovery group case by case, the K1 judge measures substance once per iteration with three outcomes, Design covers administration and data, and the proof of concept executes a real script and is never skipped. The closure against a negative review decided with D-041-A and D-041-F is not yet in the kit: under D-041-I it stays an open question and the Guide keeps its closure rules.

## Motivation

**What the Human Manager asked.** Quoted verbatim, in Italian, with an English translation.

- CR-035: «Correggi gli errori che hai trovato ed implementa la modifica PROPOSTA-MANAGER-AI-FABLE.md poi riesegui il pilota» (*"Fix the errors you found, implement the AI Manager proposal, then run the pilot again"*). On the limits of the role: «Non deve avere vincoli se non le 4 leggi, altrimenti andiamo ad aggiungere un altro elemento deterministico invece di contrastarlo» (*"It must have no constraints other than the four laws, otherwise we add one more deterministic element instead of countering it"*); and «lui è il mio rappresentante nel progetto e può decidere in mia vece» (*"it is my representative in the project and can decide in my stead"*).
- CR-036: «Togliamo approvazioni e revisioni di costo dal compito del Coordinatore in tutte le fasi. Lo traccia nelle informazioni che manda al Manager AI che decide come comportarsi» (*"Let us take approvals and cost reviews out of the Coordinator's task in every phase. It records them in the information it sends to the AI Manager, which decides how to behave"*). Then: «ogni volta che si attiva deve recuperare le tutte le informazioni che gli servono (è omniscente) per risolvere definitivamente il problema. E' il linea con la legge sul costo, risolvere un problema in modo subottimale la viola» (*"every time it acts it must retrieve all the information it needs (it is omniscient) to solve the problem for good. That is in line with the law on cost: solving a problem sub-optimally violates it"*); and «Aggiungi al suo profilo una domanda esplicita per ogni azione "Come devo comportarmi per rispettare le leggi?"» (*"Add to its profile an explicit question for every action: 'How must I behave to respect the laws?'"*).
- CR-037: «Analizziamo il processo della fase di Design Thinking mi sembra troppo burocratico» (*"Let us analyse the Design Thinking phase: it seems too bureaucratic to me"*); «Trasformiamolo in un processo iterativo sia questo che tutti gli altri step di design. E' il manager AI nel caso a giudicare che servono integrazioni» (*"Let us turn it, and all the other design steps, into an iterative process. It is the AI Manager who judges whether additions are needed"*).
- CR-038: «Il Manager AI non ha potere di modificare il KIT ma può chiedere al coordinatore di anticipare o posticipare l'avvio di azioni, richiedere di ripetere fasi o taskin base alle sue leggi» (*"The AI Manager has no power to change the kit, but it can ask the coordinator to bring forward or postpone the start of actions, or to repeat phases or tasks, according to its laws"*); «Processo snello per me significa anche rivedere i passaggi di review che abbiamo per lasciarli al minimo» (*"A lean process also means, to me, reviewing our review steps to keep them to the minimum"*); and «la fiducia fino a prova contraria» (*"trust until proven otherwise"*).
- CR-039: «Rivediamo il ruolo del giudice. non ha approvato una sola revisione fino ad ora» (*"Let us review the role of the judge. It has not approved a single review so far"*).
- CR-040: «Facciamo anche un'analisi della fase di design dopo 7 ed 8» (*"Let us also analyse the design phase after pilots 7 and 8"*).
- CR-041: «pubblichiamo una nuova RC che recepisce tutte le change fino al 40» (*"let us publish a new release candidate that takes in all the changes up to 40"*), «Dai spazio al manager AI e Wire nei metodi» (*"give room to the AI Manager and Wire among the methods"*); on the Principle: «Modifico PR-5» (*"I change PR-5"*); on the AI Manager (D-041-H): «Il manager AI non deve avere regole fisse o paletti, solo le leggi: è il contraltare del Framework che opera su flussi determinati» (*"The AI Manager must have no fixed rules or boundaries, only the laws: it is the counterweight of the Framework, which runs on determined flows"*); and on this candidate (D-041-I): «non modificare quello che ha funzionato nei piloti» (*"do not change what worked in the pilots"*).

**Evidence from the pilots of 27–28 November 2026** (pilots, not measurements):
- **The channel.** With an Interpreter that "converts and does not decide", pilots 1 to 5 did not close their first phase: the coordinator at the base took silence for consent, stalled on cases its procedure did not foresee, or waited for confirmations. Judgement was missing above the procedure; the AI Manager puts it there.
- **Discovery.** In pilot 7 Discovery took 33 runs and about 16.7 euro, 12% of it on exploration, with three negative judgements on form only. The K1 judge gave 6 judgements in pilots 4, 7 and 8, all negative, at about 0.6 dollars each; it read only the Facilitator's synthesis, not the Human Manager's answers or the AI Manager's decisions, and its criteria asked for group Decisions that, after CR-036 to CR-038, the group no longer takes. In pilots 4 and 8 its first-iteration findings were real gaps.
- **Design.** In pilot 7 Design cost about 1.4 dollars in about 5 minutes. The four blocking defects of acceptance were all functions missing from the backlog (replacement of real data, deletion by others, management of colleagues, unlocking); no role in Design dealt with security and data; the proof of concept was on paper; the backlog had no user-verifiable acceptance criteria.

## Proposal

The text is in `EIRAMAN-GUIDE.md` 1.0.0-rc.7. For each rule, the place in the kit `5818b13` is given in the Impact table.

1. **§2, The laws of the AI Manager** (new): the four laws as MUST, how they weigh, the question before every action (profile §3). *Delegation* names the AI Manager; *Design Thinking* becomes proportionate and iterative; the fourth difference says that people read only human language.
2. **§4, AI Manager** (new; replaces the Interpreter of RFC 0007): defined by its role and by the laws; its behaviour is descriptive (conversion and quotation, check of the AI Coordinator, Manager View, full information and estimates on an anomaly, trust without one, start of AI Coordinators, report of every initiative). The reports of the AI Reviewer and the Security Officer reach the Human Manager unchanged, attached by the Tools.
3. **§4, Approvals in the Human Manager's stead** (new): the AI Coordinator sends every approval, Do and question to the AI Manager; the AI Manager decides what it can assume (second law) and, under the first law, brings to the Human Manager what is critical, a higher spending cap, a change of what was asked or of the security chosen, and the Vision without convergence; other decisions, one-way doors included, it decides itself within the delegation (D-041-D, D-041-E).
4. **§4, Derogations of the AI Manager** (new, descriptive): under the fourth law it does not change the kit; it asks for derogations (bring forward, postpone, repeat, leave out), each with its law and reason; the AI Coordinator executes and records them.
5. **§4**, AI Coordinator: keeps the state for the agents, does not ask for approvals or review costs, sends open choices, executes derogations; Human Manager, Process reviewer and Internal accountability follow the channel.
6. **§5**, *Do through the AI Manager* (new) and *E4 · Classifier*: what E4 classifies as a Do reaches the AI Manager (D-041-E).
7. **§7**: *Omniscience* (new, descriptive); the AI Manager at the top and at SD4; Retrospective and Tolerance through the AI Manager.
8. **§7.1**: depth, capability and the risk class become open choices; the order of promotion is what the third law normally gives the AI Manager; the cap on promotions is a value of the mandate, context of the first law; lowering a task and raising a role are the AI Manager's decisions on open choices.
9. **§8**: *Iterations* (new); *Discovery group* with no minimum (D-041-B, D-041-G); questions through the AI Manager; *Convergence* with Decisions proposed by the group and confirmed, content criteria, the judge's inputs, its question and three outcomes, the Vision approved by the AI Manager on a convergent outcome (D-041-D); *Complete design* (new: the Tools check administration and data and the acceptance criteria and report to the AI Manager; backlog review by security and privacy); *A real proof of concept* (new).
10. **§9**: *Product Backlog* turns acceptance criteria into tests; *Manager View* is written by the AI Manager.
11. **§12**: the dialect's safety rule (a symbol only after a measurement, obligations and prohibitions in words; human language towards people); documents reach the Human Manager through the AI Manager.
12. **§13**: the Role Profile of the AI Manager MAY state the four laws in place of the lists of actions.
13. **§14**: the Human Manager questions the Security Officer through the AI Manager; the Tools attach the original risk profile unchanged.

**Left to the registry and Guidance:** the model and effort of the AI Manager and of every role (PR-6; levels map); the Wire specification; the commands, the derogation syntax and its perimeter in the step tool, the state file; the four criteria of the judge; the closed list of package phases (D43); the update of the base documents after Design (D42); the context threshold; the cases of the AI Manager's profile.

## Reversibility

A one-way door for adopters: a new mandatory role and changed approval and Discovery rules. While the Guide is a release candidate, rolling back costs a new candidate from 1.0.0-rc.6, or from the text of RFC 0007 alone (commit `59402b6`).

## Impact

- **Normative.** RFC 2119 key words in `EIRAMAN-GUIDE.md`, per section, as MUST NOT / MUST / SHOULD NOT / SHOULD / MAY:

  | Section | 1.0.0-rc.6 | RFC 0007 text (`59402b6`) | 1.0.0-rc.7 |
  |---|---|---|---|
  | §2 | 0 / 0 / 0 / 0 / 0 | 0 / 2 / 0 / 0 / 0 | 0 / 7 / 0 / 0 / 0 |
  | §4 | 1 / 24 / 0 / 1 / 1 | 3 / 29 / 0 / 1 / 1 | 2 / 32 / 0 / 1 / 1 |
  | §5 | 5 / 33 / 0 / 0 / 1 | 5 / 33 / 0 / 0 / 1 | 5 / 36 / 0 / 0 / 1 |
  | §6 | 1 / 19 / 0 / 3 / 0 | 1 / 24 / 0 / 3 / 1 | 1 / 24 / 0 / 3 / 1 |
  | §7 | 3 / 15 / 0 / 0 / 6 | 3 / 15 / 0 / 0 / 6 | 3 / 15 / 0 / 0 / 5 |
  | §7.1 | 0 / 10 / 0 / 0 / 3 | 2 / 18 / 0 / 0 / 4 | 1 / 21 / 0 / 0 / 1 |
  | §8 | 9 / 49 / 0 / 0 / 1 | 9 / 49 / 0 / 0 / 1 | 13 / 58 / 0 / 0 / 2 |
  | §9 | 4 / 30 / 0 / 0 / 1 | 4 / 30 / 0 / 0 / 1 | 5 / 31 / 0 / 0 / 1 |
  | §12 | 1 / 24 / 0 / 0 / 0 | 2 / 26 / 0 / 0 / 0 | 2 / 28 / 0 / 0 / 0 |
  | §13 | 1 / 3 / 0 / 0 / 1 | 1 / 3 / 0 / 0 / 1 | 1 / 3 / 0 / 0 / 2 |
  | §14 | 27 / 58 / 0 / 1 / 9 | 27 / 58 / 0 / 1 / 9 | 26 / 58 / 0 / 1 / 9 |
  | Total | 68 / 366 / 3 / 7 / 38 | 73 / 388 / 3 / 7 / 40 | 75 / 414 / 3 / 7 / 38 |

  The other sections are unchanged in count. Under D-041-H, some key words of 1.0.0-rc.6 that bound the actor who now is the AI Manager become descriptive: in §7, Tolerance (MAY); in §7.1, the cap on promotions (MUST NOT), the lowering of a task (MAY) and the lowering of a raised level (MAY); in §14, Dialogue with the Human Manager (MUST NOT alter the content, now a consequence of the first and second laws; the attachment of the risk profile binds the Tools). These are obligations removed from the text for one actor, recorded in the changelog under Removed.

- **Rules new in 1.0.0-rc.7 and where they are in the kit `5818b13`** (paths in `role-profiles`):

  | Rule (Guide) | Kit |
  |---|---|
  | §2 Agents write in the dialect; people read human language | `_dialetto/WIRE.md` (opening, rule 5) |
  | §2 The laws of the AI Manager, the question before every action | `governo/manager-ai/PROFILO.md` §3 «Le tue leggi», «Prima di ogni azione», «Come le leggi lavorano insieme» |
  | §4 AI Manager: conversion and quotation, Manager View, full information and estimates, trust, AI Coordinators, report | `governo/manager-ai/PROFILO.md` §1, §3 («Quando tutto funziona», «Quando rilevi un'anomalia», «La fiducia…», «Le sessioni dei Coordinatori», «Il tuo solo obbligo»), §6 |
  | §4 Reports of the AI Reviewer and the Security Officer unchanged, attached by the Tools | `governo/manager-ai/PROFILO.md` case 15 and «La Vista del Manager» (`documenti.html` from `vista_manager.py`) |
  | §4 Approvals in the Human Manager's stead; one-way doors decided by the AI Manager | `controllore/schede/do.md` «Chi decide»; `governo/manager-ai/PROFILO.md` cases 6, 8, 17 |
  | §4 Derogations; the AI Coordinator executes and records them | `controllore/schede/deroga.md`; `controllore/CONTROLLORE.md` point 13 |
  | §4 AI Coordinator at the base; state for the agents; no approvals or costs; open choices | `controllore/CONTROLLORE.md` (opening); `controllore/STATO.md`; `controllore/schede/do.md` |
  | §4 AI Reviewer at events and on samples | `controllore/schede/revisore-ai.md`; `controllore/RIFERIMENTO.md` §3 ter |
  | §5 Do through the AI Manager; E4 | `controllore/schede/do.md` («Elenco chiuso…», «Chi decide», «Dopo la decisione») |
  | §6 Verifier one level above; review by samples; cost of review apart | `controllore/schede/revisione.md` points 1–2, 7; `controllore/schede/costruzione.md` «Fine Wave» |
  | §7 Pyramid, SD table by role, Unit Cost with review | `_seniority/SENIORITY.md`, `_seniority/seniority.json` |
  | §7 Omniscience | `governo/manager-ai/PROFILO.md` §1 «Che cosa sai» |
  | §7 Retrospective and Tolerance through the AI Manager | `controllore/schede/promozione.md` («Retrospettiva», lowering a level) |
  | §7.1 Catalogue, Fallback, Team participation | `_seniority/ISTRUZIONI-CATALOGO.md`; `controllore/schede/promozione.md` |
  | §7.1 Promotion and reduction, cap, open choices | `controllore/schede/promozione.md` («La promozione è rara») |
  | §7.1 Cost per level (machine hours), Cost of errors, Raising the level of a role | `_seniority/seniority.json` (`ora_macchina_locale`); `controllore/schede/promozione.md` |
  | §8 Iterations; no automatic correction round; no stop for form | `controllore/schede/scoperta.md` «Iterazioni»; `controllore/schede/design.md` 3–4; `governo/manager-ai/PROFILO.md` case 19 |
  | §8 Discovery group decided by the AI Manager | `controllore/schede/scoperta.md` «Ruoli» (`limiti.ruoli_iterazione`, derogation `salta`); the first iteration keeps the roles of rc.6 until the Human Manager decides (`controllore/RIFERIMENTO.md` §3 bis), now decided by D-041-G |
  | §8 Question round through the AI Manager | `controllore/schede/scoperta.md` «Giro e sintesi»; `controllore/RIFERIMENTO.md` «Domande del gruppo» |
  | §8 Convergence: proposed Decisions, content criteria, inputs, three outcomes, Vision | `controllore/schede/scoperta.md` «Criteri», «Giudice K1» |
  | §8 Complete design: Tools check and report; backlog review | `controllore/schede/design.md` 5, 5 bis; `controllore/RIFERIMENTO.md` «Design e POC completi» |
  | §8 A real proof of concept, never skipped | `controllore/schede/poc.md` |
  | §9 Acceptance criteria become tests | `controllore/RIFERIMENTO.md` «Design e POC completi» (D41) |
  | §9 Manager View written by the AI Manager | `governo/manager-ai/PROFILO.md` «La Vista del Manager» |
  | §12 Messages between agents, measured symbols, obligations in words | `_dialetto/WIRE.md` «Regole» 1, 2 and «Forma del messaggio» |
  | §13 Laws in place of the lists of actions | `governo/manager-ai/PROFILO.md` «Nota sul formato» (`sezioni_assenti`) |
  | §14 Dialogue through the AI Manager; risk profile attached by the Tools | `governo/manager-ai/PROFILO.md` «La Vista del Manager» (`documenti.html`) |
  | **Not in the kit, taken out of the Guide:** closure by derogation against a negative review (D-041-A, D-041-F); the increment "verified with derogation"; §6 Outcome of review; the AI Manager in the governance share; an absent role of the group replaced or left out (D-041-G); real data, new suppliers, external release, classification mode and acceptance named as reserved items | open questions 1–4 |

- **Adopters.** A new mandatory role, the AI Manager, which writes the Manager View; the mandate records the delegation within which it decides; Discovery may have fewer roles; Design with data of people gains a checked administration section; the proof of concept runs a script.
- **Principles.** PR-5 of the project that maintains the method is changed by D-041-A, but the Guide keeps its closure rules until the kit implements the closure by derogation (open question 1).
- **Role Profiles, Tools, Translations.** As in the registry candidate `5818b13`; the Italian translation of this RFC's changes is pending (`translations/it`).

## Alternatives

- **Keep the Interpreter**, which converts and does not decide. Pilots 1 to 5 showed that a deterministic chain with no judgement above it stalls on unforeseen cases.
- **An AI Manager with explicit rules and limits in the Guide** (the first candidate `2603110`, and the recommendation of the AI Coordinator). Rejected by D-041-H: fixed rules would add one more deterministic element instead of countering it.
- **An AI Manager that changes the kit** (proposal of CR-035, 8.2). Replaced by D31: derogations only.
- **Write in the Guide what was decided but is not yet in the kit** (closure by derogation, the absent roles). Rejected by D-041-I: the Guide describes what worked in the pilots.
- **Keep a Discovery of at least five roles.** Rejected by D-041-B and D-041-G.
- **Remove the K1 judge.** Rejected (CR-039): in the first iterations it found real gaps.

## Acceptance evidence

- `tools/release_diff.py` from `v1.0.0-rc.6` to the candidate: every changed line maps to RFC 0007, to this RFC or to the changelog; no heading is removed or renamed.
- `TRACEABILITY.md`: all earlier rows kept; rows marked "RFC 0008" for each new or changed paragraph.
- No provider or model named in the Guide.
- Every rule new in 1.0.0-rc.7 has a place in the kit `5818b13` (Impact table); what has none is out of the Guide and listed below.
- **Pilots.** The AI Manager ran in pilots 6 to 8 of the kit candidate. These are pilots, not measurements. **CR-039 and CR-040 have not been tried in a real pilot**: the judge with three outcomes and content criteria, the complete Design, the backlog review, the real proof of concept and the tests from the criteria are in the kit and untested in a session.
- **Contrary evidence, stated honestly (CR-039, note on §15).** In a single informal comparison, pilot 7 with the method cost about 33 dollars and scored 5.7; a pair of agents without the method, the baseline of §15, cost about 1.6 dollars and scored 6.2: a similar result at about one twentieth of the cost. It is one run, not a campaign with hypotheses registered before it: it does not trigger the obligations of §15, Measuring the method, and the candidate stays "not measured". It is an indication to measure in a declared campaign.
- Independent review of the diff against this RFC, RFC 0007, the changelog and the decisions listed above.

## Open questions

1. **Closure by derogation (D-041-A, D-041-F).** Decided by the Human Manager: the AI Manager may close any Work Package against a negative outcome of review, the risk class and security and personal data in the blocking mode included, with the review run and its outcome kept, and an increment that contains it "verified with derogation". The kit `5818b13` has no such derogation: a package closes only on positive mandatory checks (`controllore/schede/costruzione.md` «Chiusura»; `deroga.md` has four types). Under D-041-I the Guide keeps §9 Definition of done and Dissent or missing proof as in 1.0.0-rc.6; the closure by derogation enters the Guide with the kit that implements and tries it.
2. **Absent roles in Discovery (D-041-G).** The AI Manager decides the group with no minimum. The kit has no rule for a step given to a role that is absent, such as the question round or the simulated-user tests without User Personas; the formulation proposed in the first candidate ("carried out by the role the AI Manager indicates, or not carried out, with the reason") waits for the kit. The kit still keeps the roles of rc.6 in the first iteration (`controllore/RIFERIMENTO.md` §3 bis) and needs updating to D-041-G (WP-41B).
3. **Reserved items.** The kit names, as context of the first law, what was asked, the information supplied, the security chosen and the budget. Real data, new suppliers, external release, classification mode and acceptance of the result, named in the first candidate, are not named in the kit and are out of the Guide's list.
4. **Governance share.** The kit does not count the AI Manager in the governance share (`controllore/RIFERIMENTO.md`, «quota di governo»): its cost stays in the project cost.
5. **Perimeter of derogations.** The step tool of the kit rejects derogations outside a fixed perimeter (security controls, judge, AI Reviewer, risk class, proof of concept). Under D-041-H the Guide describes these as consequences of the laws, not as limits; whether the tool keeps the perimeter is a choice for the registry.
6. **Rules that bind every agent.** The dialect (§2, §12) and the verification of the highest level by the Human Manager or another provider (§6) apply to all agents, the AI Manager included; the Guide keeps them as rules of the method.

**Note on risk (D-041-H).** Without fixed limits, the protection of the budget, of the security chosen and of real data rests on the first law, which makes the context given by the Human Manager the measure of the "best way", and on the transparency of the Manager View, where every decision and derogation of the AI Manager is reported. No control outside the laws checks the AI Manager before it acts.

**Note on these decisions.** For D-041-E, D-041-F, D-041-G and D-041-H the AI Coordinator recommended more prudent options: one-way doors always with the Human Manager, closure by derogation excluded for the risk class and for security and personal data in the blocking mode, a minimal Discovery group, and explicit rules for the AI Manager. The Human Manager chose otherwise. The accountability for these choices, and for every decision the AI Manager takes under them, remains with the Human Manager (§4, Internal accountability).

## Decision

**Accepted**, on 2026-11-28, by the Author: the decisions of CR-035 to CR-040 (D24–D43, with D27 and D28 as behaviour rules of the profile and D31 replacing decision 8.2 of CR-035), and in CR-041 D-041-A (PR-5 changed: «Modifico PR-5»), D-041-B (proportionate Discovery), D-041-D (the Vision approved by the AI Manager on a convergent outcome), D-041-E (one-way doors outside the reserved items decided by the AI Manager; §5 and E4 aligned), D-041-F (closure by derogation without exceptions), D-041-G (no minimum Discovery group), D-041-H (the AI Manager bound only by its laws) and D-041-I (the Guide describes what worked in the pilots), with the request for a release candidate that takes in all the changes up to CR-040.

Written reasons: a Human Manager who governs by exception needs a representative that holds judgement above the procedure, decides what it can assume and reports everything it does; the four laws give it the priorities a manager gives a deputy, and only those bind it, so that it counters the determinism of the method instead of adding to it. The rest of the method keeps its rules. A small project should not pay for a Discovery sized for a large one, and a judge must measure whether enough is known to build. Design must cover what people need to run the product with real data, and feasibility must be proved by running something. The Guide describes what the pilots tried; what was decided and not yet tried waits for the kit. The written reasons were drafted by the AI Coordinator from the Author's recorded requests and are confirmed by the Author with the final text, at the publication Do.

**Replaced decisions.** D20 (the Interpreter "converts and does not decide") is replaced by D24. RFC 0007 is replaced on the Interpreter and on the AI Coordinator's choices on promotion and level. D-041-H replaces in part D31, D32, D-041-A and D-041-F, for the part that bound the AI Manager: not changing the kit and keeping derogations within the context are consequences of the laws, not rules. PR-5 in its earlier form is replaced by D-041-A, which waits for the kit before it enters the Guide (open question 1). The text of the first candidate (`2603110`) is replaced by this one.

**Deviation from the comment period.** The decision was taken before the end of the thirty-day comment period (2026-12-28), as for RFC 0006 and RFC 0007. §7.1 is community-maintained and its working groups are not yet formed: the Author accepts the text without their proposal. Both deviations are recorded here and in the changelog; they do not change the process for later RFCs, and the founding contributors may reopen any point with a new RFC.

**Implementation.** Applied in candidate 1.0.0-rc.7 of the Guide, which is not measured.
