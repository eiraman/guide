<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# RFC 0008: The AI Manager, closure by derogation, and a proportionate Discovery and Design

- **Author(s):** the Author, by request; text drafted by the AI Coordinator of change request CR-041
- **Accountable human:** Paolo Ungari (Author)
- **AI-Use:** substantial (CONTRIBUTING.md §3)
- **Assisted-by:** Claude Opus 5.5 (Claude Code)
- **Conflicts of interest:** none
- **Owner of the decision:** Author (Guide); for §7.1, a community-maintained section, the DevSecOps & Tooling and FinOps working groups, which are not yet formed (see Decision)
- **Affected artifacts:** Guide §1, §2, §3, §4, §5, §6, §7, §7.1, §8, §8.1, §9, §12, §13, §14 (Dialogue with the Human Manager); `TRACEABILITY.md`. In separate releases: the Role Profiles (`governo/manager-ai`, which replaces `governo/interprete`; the AI Coordinator and its cards; the dialect), the Tools, the Extended Framework, the site and kit, and the Italian translation
- **State:** accepted
- **Dates:** opened 2026-11-28 · comment period ends 2026-12-28 · accepted 2026-11-28, before the end of the comment period (deviation, see Decision)
- **Change requests:** CR-035, CR-036, CR-037, CR-038, CR-039, CR-040 and CR-041 of the project "Eiraman Open Framework"; decided by D24–D43, D-041-A (Principle PR-5 changed) and D-041-B
- **Replaces in part:** [RFC 0007](0007-digital-seniority-pyramid.md), for the Interpreter and for the AI Coordinator's choices on promotion and level

## Summary

The only channel between the Human Manager and the agents becomes the **AI Manager**: the representative of the Human Manager in the project, omniscient, bound by four laws in order of priority (the result within its context, the Human Manager's time, spending, the method). It decides in the Human Manager's stead what it can assume, brings to them what is critical and cannot be assumed, never changes the context they gave, writes the Manager View and reports there every initiative. It does not change the kit: when the process errs it asks the AI Coordinator for a **derogation** within a fixed perimeter. The AI Coordinator no longer asks for approvals or reviews costs: it sends open choices. Principle PR-5 changes (D-041-A): every package closes on an identified candidate with independent review, and the AI Manager may close against a negative outcome only with a recorded derogation. Discovery and Design and planning become **proportionate and iterative** (D-041-B): fewer roles for a small project, one round per iteration, the K1 judge once per iteration on the substance, with three outcomes. Design covers administration and data, every backlog item has a user-verifiable acceptance criterion, and the proof of concept executes a real script and is never skipped.

## Motivation

**What the Human Manager asked.** Quoted verbatim, in Italian, with an English translation.

- CR-035: «Correggi gli errori che hai trovato ed implementa la modifica PROPOSTA-MANAGER-AI-FABLE.md poi riesegui il pilota» (*"Fix the errors you found, implement the AI Manager proposal, then run the pilot again"*). On the limits of the role: «Non deve avere vincoli se non le 4 leggi, altrimenti andiamo ad aggiungere un altro elemento deterministico invece di contrastarlo» (*"It must have no constraints other than the four laws, otherwise we add one more deterministic element instead of countering it"*); and «lui è il mio rappresentante nel progetto e può decidere in mia vece» (*"it is my representative in the project and can decide in my stead"*).
- CR-036: «Togliamo approvazioni e revisioni di costo dal compito del Coordinatore in tutte le fasi. Lo traccia nelle informazioni che manda al Manager AI che decide come comportarsi» (*"Let us take approvals and cost reviews out of the Coordinator's task in every phase. It records them in the information it sends to the AI Manager, which decides how to behave"*). Then: «ogni volta che si attiva deve recuperare le tutte le informazioni che gli servono (è omniscente) per risolvere definitivamente il problema. E' il linea con la legge sul costo, risolvere un problema in modo subottimale la viola» (*"every time it acts it must retrieve all the information it needs (it is omniscient) to solve the problem for good. That is in line with the law on cost: solving a problem sub-optimally violates it"*); and «Aggiungi al suo profilo una domanda esplicita per ogni azione "Come devo comportarmi per rispettare le leggi?"» (*"Add to its profile an explicit question for every action: 'How must I behave to respect the laws?'"*).
- CR-037: «Analizziamo il processo della fase di Design Thinking mi sembra troppo burocratico» (*"Let us analyse the Design Thinking phase: it seems too bureaucratic to me"*); «Trasformiamolo in un processo iterativo sia questo che tutti gli altri step di design. E' il manager AI nel caso a giudicare che servono integrazioni» (*"Let us turn it, and all the other design steps, into an iterative process. It is the AI Manager who judges whether additions are needed"*).
- CR-038: «Il Manager AI non ha potere di modificare il KIT ma può chiedere al coordinatore di anticipare o posticipare l'avvio di azioni, richiedere di ripetere fasi o taskin base alle sue leggi» (*"The AI Manager has no power to change the kit, but it can ask the coordinator to bring forward or postpone the start of actions, or to repeat phases or tasks, according to its laws"*); «Processo snello per me significa anche rivedere i passaggi di review che abbiamo per lasciarli al minimo» (*"A lean process also means, to me, reviewing our review steps to keep them to the minimum"*); and «la fiducia fino a prova contraria» (*"trust until proven otherwise"*).
- CR-039: «Rivediamo il ruolo del giudice. non ha approvato una sola revisione fino ad ora» (*"Let us review the role of the judge. It has not approved a single review so far"*).
- CR-040: «Facciamo anche un'analisi della fase di design dopo 7 ed 8» (*"Let us also analyse the design phase after pilots 7 and 8"*).
- CR-041: «pubblichiamo una nuova RC che recepisce tutte le change fino al 40» (*"let us publish a new release candidate that takes in all the changes up to 40"*), «Dai spazio al manager AI e Wire nei metodi» (*"give room to the AI Manager and Wire among the methods"*); and on the Principle: «Modifico PR-5» (*"I change PR-5"*).

**Evidence from the pilots of 27–28 November 2026** (pilots, not measurements):
- **The channel.** With an Interpreter that "converts and does not decide", pilots 1 to 5 did not close their first phase: the coordinator at the base took silence for consent, stalled on cases its procedure did not foresee, or waited for confirmations. Judgement was missing above the procedure; the AI Manager puts it there.
- **Discovery.** In pilot 7 Discovery took 33 runs and about 16.7 euro, 12% of it on exploration, with three negative judgements on form only. The K1 judge gave 6 judgements in pilots 4, 7 and 8, all negative, at about 0.6 dollars each; it read only the Facilitator's synthesis, not the Human Manager's answers or the AI Manager's decisions, and its criteria asked for group Decisions that, after CR-036 to CR-038, the group no longer takes. In pilots 4 and 8 its first-iteration findings were real gaps.
- **Design.** In pilot 7 Design cost about 1.4 dollars in about 5 minutes. The four blocking defects of acceptance were all functions missing from the backlog (replacement of real data, deletion by others, management of colleagues, unlocking); no role in Design dealt with security and data; the proof of concept was on paper; the backlog had no user-verifiable acceptance criteria.

## Proposal

The text is in `EIRAMAN-GUIDE.md` 1.0.0-rc.7. In short:

1. **§2, The laws of the AI Manager** (new). The four laws in order of priority, read by weight and then by order, a law set aside only as far as needed, and the question before every action. *Delegation* and *Quality control* in the list of practices name the AI Manager and the derogation; *Design Thinking* becomes proportionate and iterative. The fourth difference says that people read only human language.
2. **§4.** *AI Manager* (new, replaces the Interpreter of RFC 0007); *Approvals in the Human Manager's stead* (new): everything for the Human Manager passes through the AI Manager, which decides what it can assume within the delegation and never changes the context of the first law (spending cap, scope, real data or new suppliers, release outside the organisation, classification mode), the Vision without convergence or the acceptance of the result; *Derogations of the AI Manager* (new): no change to the kit; bring forward, postpone, repeat or leave out an action, with the law and the reason; never a phase, the spending cap, the security chosen, the security controls, the judge, the AI Reviewer or the risk class; no other MUST of the Guide set aside except closure by derogation. The *AI Coordinator* keeps the state for the agents, no longer asks for approvals or reviews costs, and executes derogations. The *Human Manager*, the *Process reviewer* and *Internal accountability* follow: the Human Manager remains accountable.
3. **§5.** *Do through the AI Manager* (new).
4. **§6.** *Outcome of review* (new): PR-5 as changed by D-041-A.
5. **§7.** *Omniscience* (new), the third position of blinding; the AI Manager at the top and at SD4; the retrospective and the tolerance through the AI Manager.
6. **§7.1.** Depth, capability and the risk class become open choices that the AI Manager decides, in the order of RFC 0007; lowering a task and raising the level of a role become decisions of the AI Manager on an open choice of the AI Coordinator.
7. **§8.** *Iterations* (new); *Discovery group* proportionate, possibly below five roles, with the Facilitator and at least one User Persona; questions pass through the AI Manager; in *Convergence*, Decisions proposed by the group and confirmed, criteria on content, the judge's inputs, its question and three outcomes, and the AI Manager may approve the Vision in the Human Manager's stead only on a convergent outcome; *Complete design* (new) and *A real proof of concept* (new); the governance share includes the AI Manager; the playbook follows.
8. **§9.** *Definition of done* and *Dissent or missing proof* admit closure by derogation; *Closure by derogation* (new) keeps the review and its outcome, and keeps technical state, acceptance and release distinct; *Product Backlog* turns acceptance criteria into tests; *Manager View* is written by the AI Manager.
9. **§12.** The dialect's safety rule: a symbol only after a measurement, obligations and prohibitions in words; human language towards people; documents reach the Human Manager through the AI Manager.
10. **§13.** The Role Profile of the AI Manager MAY state the four laws in place of the lists of permitted and forbidden actions.
11. **§14.** The Human Manager questions the Security Officer through the AI Manager.

**Left to the registry and Guidance, not to the Guide:** the model and effort of the AI Manager and of every role (PR-6; levels map); the Wire specification, its fields, glossary and length caps (`_dialetto/`); the tool commands, the derogation syntax, the state file and its keys; the four criteria of the judge's content (kit); the closed list of package phases (D43); the update of the base documents after Design (D42); the context threshold of the coordinator; the behaviour cases of the AI Manager's profile.

## Reversibility

A one-way door for adopters: a new mandatory role, a changed Principle, changed closure and Discovery rules. While the Guide is a release candidate, rolling back costs a new candidate from 1.0.0-rc.6, or from the text of RFC 0007 alone (commit `59402b6`).

## Impact

- **Normative.** RFC 2119 key words in `EIRAMAN-GUIDE.md`, from the text of RFC 0007 (commit `59402b6`) to 1.0.0-rc.7, per section, as MUST NOT / MUST / SHOULD NOT / SHOULD / MAY:

  | Section | RFC 0007 text | 1.0.0-rc.7 |
  |---|---|---|
  | §2 | 0 / 2 / 0 / 0 / 0 | 0 / 7 / 0 / 0 / 0 |
  | §4 | 3 / 29 / 0 / 1 / 1 | 8 / 45 / 0 / 1 / 4 |
  | §5 | 5 / 33 / 0 / 0 / 1 | 5 / 34 / 0 / 0 / 2 |
  | §6 | 1 / 24 / 0 / 3 / 1 | 2 / 26 / 0 / 3 / 1 |
  | §7 | 3 / 15 / 0 / 0 / 6 | 3 / 16 / 0 / 0 / 8 |
  | §7.1 | 2 / 18 / 0 / 0 / 4 | 2 / 23 / 0 / 0 / 4 |
  | §8 | 9 / 49 / 0 / 0 / 1 | 13 / 63 / 0 / 0 / 5 |
  | §9 | 4 / 30 / 0 / 0 / 1 | 6 / 36 / 0 / 0 / 2 |
  | §12 | 2 / 26 / 0 / 0 / 0 | 2 / 28 / 0 / 0 / 0 |
  | §13 | 1 / 3 / 0 / 0 / 1 | 1 / 3 / 0 / 0 / 2 |
  | Total | 73 / 388 / 3 / 7 / 40 | 85 / 440 / 3 / 7 / 52 |

  The other sections are unchanged in count (§14 changes words, not key words). From 1.0.0-rc.6, with RFC 0007: 68 / 366 / 3 / 7 / 38 → 85 / 440 / 3 / 7 / 52.
- **Adopters.** A new mandatory role in every project, the AI Manager, which writes the Manager View; the mandate records the delegation within which the AI Manager decides; Discovery may have fewer roles; every Design with data of people gains the administration functions; the proof of concept runs a script.
- **Principles.** PR-5 of the project that maintains the method changes (D-041-A); a closure against a negative review is no longer impossible, but it is always recorded, motivated and reported, and never counts as acceptance or release.
- **Role Profiles.** `governo/manager-ai` replaces `governo/interprete` (marked replaced); the AI Coordinator and its cards (Discovery, Design, proof of concept, derogation, promotion); the reviewers of security and privacy review the backlog; the Facilitator proposes content criteria.
- **Tools.** The step tool applies derogations, iterations, three outcomes of the judge and the backlog checks; the Manager View is written by the AI Manager.
- **Translations.** The Italian translation translates RFC 0007's text; this RFC's changes are pending (`translations/it`, note "Pending update to 1.0.0-rc.7+it.1").

## Alternatives

- **Keep the Interpreter**, which converts and does not decide. Pilots 1 to 5 showed that a deterministic chain with no judgement above it stalls on unforeseen cases.
- **An AI Manager free of the Guide's MUSTs**, as the first proposal put it ("it may set aside a rule of this Guide"). Rejected for the Guide: D31 and D33 keep the Guide's MUSTs and the risk class fixed, and D40 refused the skip of the proof of concept because §8 makes all five phases mandatory. The only exception is the closure by derogation that D-041-A decides.
- **An AI Manager that changes the kit** (proposal of CR-035, 8.2). Replaced by D31: derogations only.
- **Keep PR-5 as it was and route every negative review back to rework.** Rejected by D-041-A: the AI Manager decides on the outcome, which is an input, not an automatic loop.
- **Keep a Discovery of at least five roles.** Rejected by D-041-B: a small project pays for roles it does not need.
- **Remove the K1 judge.** Rejected (CR-039): in the first iterations it found real gaps; it measures substance once per iteration.

## Acceptance evidence

- `tools/release_diff.py` from `v1.0.0-rc.6` to the candidate: every changed line maps to RFC 0007, to this RFC or to the changelog; no heading is removed or renamed; the paragraph label "Interpreter" of the RFC 0007 text becomes "AI Manager".
- `TRACEABILITY.md`: all earlier rows kept; rows marked "RFC 0008" for each new or changed paragraph.
- No provider or model named in the Guide.
- The registry candidate (`role-profiles` `5818b13`) implements CR-035 to CR-040: `governo/manager-ai` 0.5.1 with the four laws and the derogations; the AI Coordinator with derogations and open choices; cards for Discovery, Design and proof of concept.
- **Pilots.** The AI Manager ran in pilots 6 to 8 of the kit candidate. These are pilots, not measurements. **CR-039 and CR-040 have not been tried in a real pilot**: the judge with three outcomes and content criteria, the complete Design, the backlog review by security and privacy, the real proof of concept and the tests from the criteria are implemented in the registry candidate and untested in a session.
- **Contrary evidence, stated honestly (CR-039, note on §15).** In a single informal comparison, pilot 7 with the method cost about 33 dollars and scored 5.7; a pair of agents without the method, the baseline of §15, cost about 1.6 dollars and scored 6.2: a similar result at about one twentieth of the cost. It is one run, not a campaign with hypotheses registered before it: it does not trigger the obligations of §15, Measuring the method, and the candidate stays "not measured". It is an indication to measure in a declared campaign.
- Independent review of the diff against this RFC, RFC 0007, the changelog, D24–D43, D-041-A and D-041-B.

## Open questions

1. **Vision without the Human Manager.** The Guide lets the AI Manager approve the Vision in the Human Manager's stead only when the judge finds convergence, as the registry candidate does. The Author confirms this reading or keeps the Vision always with the Human Manager.
2. **Reserved context.** The list of what the AI Manager never decides in the Human Manager's stead (spending cap, scope, real data or new suppliers, release outside the organisation, classification mode, the Vision without convergence, acceptance) is drawn from decision 8.1 of CR-035, where these items are "context of the first law". Whether one-way doors not on that list also stay with the Human Manager is not decided.
3. **Limits of closure by derogation.** D-041-A sets no exception. The Guide keeps the review and its outcome, keeps the §14 rule on a refused mandatory check, and does not count the closure as acceptance or release. Whether the risk class, or security and personal data in the blocking mode, should be excluded is a decision of the Author.
4. **Minimal Discovery.** D-041-B lets the number of roles fall below five; the Guide keeps the Facilitator and at least one User Persona, which the question round and the simulated-user tests need. The Author confirms this minimum.
5. **Role Profile format.** §13 lets the AI Manager's profile state the laws in place of the lists of actions, as the registry candidate does; the Process reviewer is not yet given a model different from the AI Manager's.

## Decision

**Accepted**, on 2026-11-28, by the Author: the decisions of CR-035 to CR-040 (D24–D43, with D27 and D28 as behaviour rules of the profile and D31 replacing decision 8.2 of CR-035), and in CR-041 D-041-A (PR-5 changed: «Modifico PR-5») and D-041-B (proportionate Discovery), with the request for a release candidate that takes in all the changes up to CR-040.

Written reasons: a Human Manager who governs by exception needs a representative that holds judgement above the procedure, decides what it can assume and reports everything it does; the four laws give it the priorities a manager gives a deputy, and the Guide's MUSTs remain the frame within which it acts. A negative review is information for a decision, not an automatic loop; closing against it is a recorded exception for which the Human Manager remains accountable. A small project should not pay for a Discovery sized for a large one, and a judge must measure whether enough is known to build, not the form of the synthesis. Design must cover what people need to run the product with real data, and feasibility must be proved by running something. The written reasons were drafted by the AI Coordinator from the Author's recorded requests and are confirmed by the Author with the final text, at the publication Do.

**Replaced decisions.** D20 (the Interpreter "converts and does not decide") is replaced by D24; RFC 0007 is replaced on the Interpreter and on the AI Coordinator's choices on promotion and level. PR-5 in its earlier form ("closure on evidence") is replaced by D-041-A.

**Deviation from the comment period.** The decision was taken before the end of the thirty-day comment period (2026-12-28), as for RFC 0006 and RFC 0007. §7.1 is community-maintained and its working groups are not yet formed: the Author accepts the text without their proposal. Both deviations are recorded here and in the changelog; they do not change the process for later RFCs, and the founding contributors may reopen any point with a new RFC.

**Implementation.** Applied in candidate 1.0.0-rc.7 of the Guide, which is not measured.
