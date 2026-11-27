<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# Changelog

All notable changes to the Eiraman Guide are documented in this file. The format is based on
[Keep a Changelog 1.1](https://keepachangelog.com/en/1.1.0/), and versions follow the rules for normative
texts in [community/VERSIONING.md](https://github.com/eiraman/community/blob/main/VERSIONING.md): MAJOR when
an obligation is removed or reversed, MINOR when one is added or broadened, PATCH for editorial changes
with no change of meaning. [HISTORY.md](HISTORY.md) keeps the narrative history of the method.

## [Unreleased]

### Added

- `translations/it/`: the Italian curated translation of the Guide 1.0.0-rc.5, `EIRAMAN-GUIDE.it.md`, with its
  glossary `GLOSSARY.it.md`, the notes on the source `SOURCE-NOTES.md` and its own `CHANGELOG.md`; version of the translation `1.0.0-rc.5+it.1` (the
  source version plus the translation revision as SemVer build metadata). From change request CR-029 and the
  Human Manager's decision D-IT-1. The English text stays canonical and prevails in case of difference; it is
  not changed, so the Guide version is not changed and nothing is tagged (VERSIONING §1, notes). The
  translation keeps every normative key word of the source, rendered in capitals as DEVE, NON DEVE, DOVREBBE,
  NON DOVREBBE and PUÒ, with the same counts section by section; it adds, removes and changes no obligation.
  Row for the translation in `README.md`.

### Changed

- `translations/it/`: the Italian translation is updated to the Guide 1.0.0-rc.6, version of the translation
  `1.0.0-rc.6+it.1` (CR-031, decisions D-031 and D-031-B). It translates the three sentences added to "Why
  Eiraman exists" and the paragraph "The method applies to itself" (§2), the paragraph "Measuring the method"
  (§15), with the same key words as the source (in §15: 28 DEVE/DEVONO, 4 NON DEVE/NON DEVONO, 1 NON
  DOVREBBERO, 3 PUÒ/POSSONO), and the Status "not measured"; glossary and notes on the source updated; the
  note "Pending update" of `translations/it/CHANGELOG.md` is replaced by the entry of that version. The English
  text is not changed.
- `translations/it/CHANGELOG.md`, `[Unreleased]`: records the Author's native-speaker review of the Italian translation `1.0.0-rc.6+it.1` on
  2026-11-27, with no change to the text; the "Not verified" point is closed under D-IT-1 (CR-032). The Guide version and the
  translation version are unchanged, and nothing is tagged (VERSIONING §1, notes).

## [1.0.0-rc.6] - 2026-11-27

Sixth release candidate. Not yet in force and **not measured**: no measurement campaign of the method has been
completed. It implements [RFC 0006](rfcs/0006-security-measurement-self-feeding.md), from change request CR-031.
The Author approved its direction on 27 November 2026 (D-031, extended by D-031-B), before the end of its
thirty-day comment period: a recorded deviation; the Author approves the final text at the publication Do.
D-031-B replaces the decision of 26 November 2026 that kept the rules on measuring the method out of the Guide
until a campaign was completed (RFC 0003, "Not included"). Obligations are added for those who maintain the
method, none for adopters; the RFC 2119 key words change only in §15: MUST 350 → 366, MUST NOT 66 → 68,
SHOULD NOT 2 → 3, MAY 37 → 38 in the whole Guide.

### Added

- **§15, Measuring the method** (MUST, MUST NOT, SHOULD NOT, MAY), binding the Author and the Maintainers (§4),
  not adopters: each version of the Guide, with the Extended Framework, Role Profiles and Tools released with
  it, MUST be measured on a test bench against a declared baseline, the simplest configuration without the
  method (two agents, a designer at a Digital Seniority suited to design and an implementer at a lower one, no
  AI Coordinator, no reviewer, a single candidate; levels and models in the Extended Framework); a release
  that does not change the Guide is covered by the campaign of its version; a version MAY be released before
  its campaign is completed and MUST then declare itself "not measured"; equal conditions (request, files and
  tools, simulated Human Manager, limits) and isolated runs MUST apply, and a run beyond the limits counts as
  failed; the baseline MUST be run again at every change of model and comparisons MUST be made only between
  the same models; bench testing MUST take the delivery as it is and record every fault, defined; testers MUST
  be independent of the developers and SHOULD NOT use models more capable than those measured, and Seniority of
  the verifier (§6) does not apply to them; requests, briefs and expected results MUST be written by others
  than the maintainers and frozen before the campaign, the measured agents MUST NOT see briefs or expected
  results, and judged indicators MUST follow K1; bench testing is distinct from the acceptance testing of
  §9.1; hypotheses, with indicator, margin and repetitions, MUST be recorded before a campaign and MUST NOT
  change after it, and every result MUST be kept and counted; when a test that removes a rule excludes a
  benefit above the margin, a proposal to reduce or remove it MUST go to the Human Manager; when the baseline
  is demonstrated to obtain the same result at lower cost for a class, the Author MUST state it in the Guide
  and indicate the baseline; "not demonstrated" is enough for neither. Indicators, applications, repetitions,
  limits and the models of the baseline are Guidance of the Extended Framework (`guidance/BENCH.md`, in
  preparation in the framework candidate 0.3.0).
- **§2, The method applies to itself** (descriptive, new paragraph): each rule is a hypothesis measured against
  a baseline, the same tasks without the method; the method feeds itself: the Human Manager gives the
  direction, the agents translate it by the principles of the method into change requests, specific choices
  and suggestions, and the Human Manager decides through Do escalations.
- `rfcs/0006-security-measurement-self-feeding.md`, accepted (D-031, D-031-B), and its row in `rfcs/README.md`.

### Changed

- **§2, Why Eiraman exists** (descriptive): a second reason for the method. Vibe coding sharply increases the
  data people handle, often without the competence needed to see the risks; in Eiraman the managerial role
  extends to security, and a Human Manager who delegates a task knows what it implies for security, privacy
  and regulatory compliance, through the classification and the Security Officer (§14). For one's own use this
  is, by default, information, recorded in the Security Report (§12); in work and organisational contexts it is
  blocking by default: the adoption levels and the Applicability gate stop what the qualified level does not
  allow, except what the Human Manager decides to run above it under the conditions of §14.2 (§14,
  Classification mode). The earlier text of the paragraph is kept whole.
- **Title block, Status** (descriptive): "not measured (§15, Measuring the method)"; the same in `README.md`.
- Title block, `README.md` and row R002 of `TRACEABILITY.md`: version 1.0.0-rc.6; `README.md` lists RFC 0006.
- `TRACEABILITY.md`: four rows marked "RFC 0006" (RFC0006-03 normative; RFC0006-01, -02 and -04 descriptive);
  all earlier rows kept; in the Count check, a line for the rows added by RFC 0006 (4 rows, 1 normative and 3
  descriptive).
- `translations/it/CHANGELOG.md`: note under [Unreleased] that the Italian translation, which still declares
  1.0.0-rc.5, must be updated to `1.0.0-rc.6+it.1`, with the texts to translate. The text of the translation is
  not changed.

## [1.0.0-rc.5] - 2026-11-27

Fifth release candidate. Not yet in force. It implements
[RFC 0005](rfcs/0005-classification-modes.md), from change requests CR-022 and CR-023 and the Human Manager's
decisions recorded in them. The Author accepted RFC 0005 on 27 November 2026 (Do-S29), before the end of its
comment period and for the community-maintained sections §14 and §14.2: two recorded deviations. No run of the
test bench has used either classification mode or the question round.

### Added

- **§14, Classification mode** (MUST, MUST NOT, MAY): the classification works in a blocking or an informative
  mode. In the informative mode the same rules stop nothing; the Security Officer records the class and every
  finding in the Security Report and the Human Manager answers for proceeding. The Human Manager may choose
  the mode at the opening; the mandate records it. Without a choice, informative MUST apply for personal use
  and blocking in every other case, doubt included. An organisation may impose the blocking mode on the
  projects opened and versions approved while its rules are in force. The mode MUST NOT change during a
  project, except for a new version under such rules.
- **§14, Classification mode, informative mode** — **relaxed rules**: the classification MUST NOT stop or
  reduce any action; the rules of §14.2 that stop a project or limit its data or releases do not, except that
  the environment MUST Deny the work depending on a lapsed requirement set by another rule; a requirement of
  §14.1 other than Error budget that no other rule sets MAY be left unmet and MUST be listed in the report.
  Error budget MUST apply in both modes. Evidence of a project in the informative mode MUST NOT count towards
  a higher level.
- **§14, Classification mode, refusals** (both modes; MUST, MUST NOT): an action a model refuses MUST NOT be
  performed by the same model with another request, nor by another model, candidate or Digital Seniority level;
  the output of every competing candidate for it MUST be discarded; the refusal is recorded in the Security
  Report in the informative mode, and in the Log Tracker and the cycle review in the blocking mode; it MUST NOT
  count as a failure for lack of capability (§7.1); the Work Package is closed without the action when its
  mandatory checks pass, or re-planned; in doubt between refusal and incapacity it is a refusal. **Changed
  rule** of §9 Dissent or missing proof: a refused mandatory check keeps the package open, MUST NOT be repeated
  or assigned to another verifier, and goes to the Human Manager as a Do.
- **§14, Out of scope in the informative mode** — **relaxed rule**: the excluded cases, AI systems that the law
  prohibits included, MUST NOT stop the project and MUST be recorded; a case that fits no class MUST be recorded
  as out of scope; the project record states it in place of the class.
- **§14, Security Officer in the informative mode** (MUST, MUST NOT, MAY) — **relaxed rules**: silent, it MUST
  NOT start an exchange with the Human Manager or write to them outside the Security Report and the answers
  under Dialogue with the Human Manager; the scope MUST NOT be reduced on grounds of the classification; what it
  cannot determine is recorded as not determined; reversible protections MAY be applied by delegation and are
  recorded; Risk profile, Treatments and Questions for the organisation apply in the blocking mode only, so the
  limit to test data while the organisation answers does not apply; in the Manager View the Security Report is
  attached in place of the risk profile; the findings of security, privacy and legal and compliance reviewers on
  class, presence of personal data and exclusions are recorded in the report and MUST NOT keep a package open or
  stop or reopen a phase; their other findings follow §9.
- **§14, Local engines in the informative mode** (MUST, MUST NOT): the mandate states the local engines that run
  the agents or are part of the product; none is used before the Human Manager approves it, with the mandate
  or by a Do; adding one later is a Do; the report names the engines.
- **§12, Security Report** (MUST, MUST NOT): shipped with every release in the informative mode, with fixed
  contents, updated at every Wave and release.
- **§8, Question round** (MUST, MUST NOT): before divergence every executor says what is not known and who
  should be asked; the User Personas answer with source and confidence; the least certain questions, up to the
  number the mandate sets (before its approval, the number communicated at the start of Discovery), reach the
  Human Manager with the answer supposed; the others become visible assumptions.
- **§8.1, Discovery procedure**: step *Questions*, once, before the first round.
- `rfcs/0005-classification-modes.md`, accepted (Do-S29), and its row in `rfcs/README.md`.

### Changed

- **§14, Principle** — **relaxed rule**: the prohibition to run above the qualified level holds in the blocking
  mode; every project MUST have a class or, in the informative mode, the record that it fits none.
- **§14, Deliverables** — **relaxed rule**: the example holds in the blocking mode; in the informative mode the
  class of the deliverables MUST be recorded.
- **§14, Out of scope at any level** — **relaxed rule**: the MUST NOT holds in the blocking mode.
- **§14, Project classes** — **relaxed rule**: exception for a case that fits no class.
- **§14, Applicability gate** — **relaxed rule**: out-of-scope treatment in the blocking mode only; in the
  informative mode the gate MUST NOT stop the project and MUST record its findings; a repeated gate with
  unchanged scope MAY be recorded by reference to the last run.
- **§3, Some uses are excluded** — **relaxed rule**, a context principle: the exclusion holds in the blocking
  mode.
- **§2, Management applied to AI**: adoption levels limit risk up front or make it known.
- **§4, Internal accountability** and **Liability towards third parties**: the Human Manager answers for
  proceeding in the informative mode.
- **§4, Human Manager** — **relaxed rule**: approval of the project class in the blocking mode only; the same in
  **§8, Phases and decisions**, Discovery.
- **§5, Deny** — **relaxed rule**: Deny for the adoption level in the blocking mode.
- **§5, Do** — **relaxed rules**: in the informative mode personal data, third parties and changes of class MUST
  NOT go to the Human Manager as a Do on that ground alone, even where the mandate reserves the first two.
- **§5, E5 · Drift budget** — **relaxed rule**: in the informative mode a change of class MUST NOT count towards
  the drift budget or be reported as an item of its own, and is recorded in the Security Report; the spending
  and time it causes count as any deviation.
- **§14.2, Class change** — **relaxed rule**: the Do and the four options in the blocking mode only.
- **§8, Gates**: one gate MUST follow the question round.
- **§8.1, Roles in the Discovery group**: the User Personas give first answers to the question round.
- **§9, Project record** (MUST broadened): it names the classification mode.
- **§9, Shape of control artifacts** — **relaxed rule**: in the informative mode content that only §14.1
  requires MAY be left out; the documents §12 lists are kept.
- **§12, Three layers of documentation** and **Third-party evidence pack** (MUST broadened): the managerial
  layer includes the Security Report in the informative mode; the pack names the classification mode and, in the
  informative mode, MUST include the Security Report.
- **§13, Minimum content** — **relaxed rule**: in the informative mode a limit of the Security Officer or of a
  security, privacy or legal and compliance profile is recorded instead of taking the project out of the method.
- Title block, `README.md` and row R002 of `TRACEABILITY.md`: version 1.0.0-rc.5; `README.md` lists RFC 0005.
- `TRACEABILITY.md`: twenty-nine rows marked "RFC 0005"; all earlier rows kept.

## [1.0.0-rc.4] - 2026-11-26

Fourth release candidate. Not yet in force. It implements
[RFC 0004](rfcs/0004-running-above-qualified-level.md), proposed by the Steward on behalf of the working
groups not yet formed, from change requests CR-013 and CR-014 and the decisions of the Human Manager recorded
there. The Author accepted RFC 0004 on 26 November 2026 (Do-S26), before the end of its thirty-day comment
period and for the community-maintained sections §14, §14.1 and §14.2: two recorded deviations.
Two rules are relaxed (the §14 Principle and the doubtful cases of the Applicability gate) and obligations
are added. Relaxing a rule would be a MAJOR change for a
version in force (VERSIONING §2.1); the Guide is not in force, so the change is released as the next candidate.

### Added

- **§14.2, Running above the qualified level** (MAY, MUST, MUST NOT): by an explicit and recorded decision,
  taken on the risk profile of the Security Officer, the Human Manager may let a project of class 1 run in an
  adoption qualified at level 0, and no other class or level. Each project has its own decision. The Do
  states the risk accepted and how each requirement will be met; the decision is recorded in the project
  record with a declaration that the project runs above the qualified level, and the third-party evidence
  pack MUST carry that declaration. All the
  Method requirements of level 1 are due before the first release, and a preview is not a release. Personal
  data of colleagues are not processed until all the Method and Organisation requirements of level 1 are met,
  the formal mandate included; until then the project works on test or masked data. In doubt between class 1
  and a higher class, the higher class is assumed, also when the doubt depends on a question for the
  organisation; the exception for the work on test data does not apply to that doubt. A case the gate treats as out of scope, or that leaves the scope of the method under §13, is
  not admitted by decision, except that, while the only doubt is a question for the organisation not yet
  answered, the decision may cover the work on test data alone; once the organisation answers, the gate
  MUST run again and going beyond that work MUST have a new decision. An overdue or lapsed requirement of level 1 brings the
  permitted class back to the one of the qualified level until it is met, and Automatic downgrade applies.
  The AI Coordinator reports the state at every cycle review and proposes moving up once the evidence exists;
  the experience counts as experience at level 0 for moving up. The decision waives only the Evidence of
  experience at level 0 required for moving up and does not qualify the adopter for level 1.
- **§14, Risk profile, Treatments, Questions for the organisation, Dialogue with the Human Manager,
  Independence of the Security Officer** (MUST, MUST NOT, MAY, SHOULD): the Security Officer delivers a risk
  profile with the treatments it proposes when the class exceeds the level or an exclusion is triggered, and
  the profile MUST also say when the decision of §14.2 is available and what it requires; no treatment
  passes a case out of scope at any level, and a reduced scope is a new scope that MUST pass the gate again;
  for the questions that belong to the organisation it says who can answer and prepares the question, an
  answer by the Human Manager alone does not resolve them, until the organisation answers the case MUST be
  treated as in doubt, and in the meantime, if no exclusion criterion is triggered, work may go on only on
  test data, with no real data and no release; the Human Manager may question it through the AI Coordinator,
  which does not alter the content, and the original risk profile MUST be attached unchanged in the Manager
  View; it does not act as a reviewer, the roles of security reviewer and privacy reviewer MUST NOT be held
  on the same project by it or by an agent instantiated from its Role Profile, and it SHOULD run on a model
  different from the AI Coordinator's where one is available.
- `rfcs/0004-running-above-qualified-level.md`, accepted (Do-S26), and its row in `rfcs/README.md`.

### Changed

- **§14, Principle**: **relaxed rule**. A project MUST NOT run if its class exceeds the qualified level,
  except by the decision of the Human Manager that §14.2 allows.
- **§14, Applicability gate** (MUST, MUST NOT, MAY): the Security Officer, an AI compliance role under its
  own qualified Role Profile, assigns the class; the AI Coordinator invokes it and MUST NOT assign the class
  itself. **Relaxed rule** for doubtful cases: a doubtful case stays out of scope, but when the only doubt is
  a question for the organisation not yet answered the work on test data may go on (see Questions for the
  organisation), also for a project within the qualified level.
- **§14.2, Class change** (exception tied to §14.2 Running above the qualified level): a fourth option, to let the project run by decision where §14.2 allows it.
- **§14.1, Level 0 · Organisation** (exception tied to §14.2): a project that runs above the qualified level under a mandate of the
  organisation is owned, with what it produces, by that organisation.
- **§4, Liability towards third parties**: for such a project, liability lies with that organisation.
- **§5, Deny** (MUST broadened, with an exception tied to §14.2): for an admitted project class 1 takes the place of the adoption level,
  unless a requirement of level 1 is due and not met; while work goes on only on test data, the environment
  also blocks any other data and every release.
- **§5, Do**: the decision to run a project above the qualified level is in the list.
- **§7, Hard blinding** (MUST broadened): it applies to the Security Officer too.
- Title block, `README.md` and row R002 of `TRACEABILITY.md`: version 1.0.0-rc.4; `README.md` lists RFC 0004.
- `TRACEABILITY.md`: fourteen rows marked "RFC 0004" for the new or changed paragraphs; all earlier rows kept.

## [1.0.0-rc.3] - 2026-11-26

Third release candidate. Not yet in force. It implements [RFC 0003](rfcs/0003-critical-review-corrections.md),
proposed by the Steward, also on behalf of the working groups not yet formed, from change request CR-009 and
the Human Manager's decisions D0 to D10 on the findings of the critical review of specification 0.3, with the
later decisions recorded in CR-009. The Author accepted RFC 0003 on 26 November 2026 (Do-S19), before the end
of its comment period and for the community-maintained sections §7.1, §9.1 and §14 with §14.1: two recorded
deviations.
Obligations are added or broadened, and two rules are replaced (see RFC 0003, "Rules replaced"). Replacing
a rule would be a MAJOR change for a version in force (VERSIONING §2.1); the Guide is not in force, so the
change is released as the next candidate. The release also carries RFC 0002, which does
not change the Guide text, and the CI fix that waited under `[Unreleased]`.

### Added

- **§2, two transpositions**: internal control and segregation of duties; bills of materials and
  supply-chain traceability. The list has eleven items.
- **§5, Do**: changes that add an external service or move data outside the organisation are in the general
  list (MUST), as already required by §9 High Level Architectural View, which now refers to §5.
- **§5, E6 Measurement** (MUST): under-escalation and over-escalation are estimates over a sample, reported
  with the number of decisions examined and their confidence interval; a threshold is met only if the
  unfavourable bound stays within it. This makes the evidence for level 1 (§14.1) stricter.
- **§6, K6** (MUST): the mandate sets the type of package, the minimum number of packages and the minimum
  margin over a single executor.
- **§7, Hard blinding** (MUST broadened): it applies to the Discovery judge too.
- **§7.1, Catalogue** (descriptive): the map is the maintainers' assessment; untested configurations are
  marked.
- **§7.1, Fallback** (MUST broadened): the cycle review reports the share of tasks run outside the catalogue.
- **§7.1, Team participation** (MAY): tasks of different levels may go to different agents, when the saving
  exceeds the cost of handing over the context.
- **§7.1, Promotion and reduction** (MUST): a task outside the catalogue is promoted at the first failure
  for lack of capability; "unchanged quality" means no increase in defects after closure or in rework.
- **§8, Convergence** (MUST): Discovery convergence follows K1. Criteria are fixed before divergence; after
  the Discovery reviewers a judge on a model different from those of the group, distinct from the reviewers
  and under hard blinding, assesses the result before it reaches the Human Manager. When no such model is
  available the choice goes to the Human Manager as a Do. Amends the convergence of RFC 0001.
- **§8, Governance cycle** (MUST broadened): the management review reports the governance share, that is the
  cost of governance roles, the applicability gate and managerial documents over the total cost of the
  cycle, and the share of tasks run outside the catalogue.
- **§8.1, Discovery procedure** (descriptive): step Judge.
- **§9, Risk Log and Manager View** (descriptive): new paragraphs that define the two terms.
- **§9.1, Test levels** (descriptive): security and performance testing is proportionate to the risk. The
  sentence was in specification 0.2 and had been dropped without a changelog entry.
- **§10, Brain** (MUST): the mandate sets the criteria by which a Brain task is trusted or untrusted, and
  the role that applies them.
- **§11, Run traceability** (MUST broadened): each run records the role of the agent, labelled as
  governance or production.
- **§14.1, Operational documents** (MUST): at every level, the Product Backlog, the Work Package records,
  the run records and, for each team, the staffing plan and the Log Tracker.
- `rfcs/0003-critical-review-corrections.md`, accepted (Do-S19), and its row in `rfcs/README.md`.
- `rfcs/0002-governo-family.md` (CR-007): regularises the Role Profile family `governo/`, created in Wave
  DT-01 without an RFC and without a family group (Do-S16). Three alternatives are kept for the record; the
  Author, who is also the Steward in Stage 1, accepted alternative B on 2026-11-26 (Do-S18): a new working
  group "Governance & Assurance" owns the family, and the reviewers of record of each domain co-review its
  reviewer profile. Accepted before the end of the thirty-day comment period, a recorded deviation as for
  RFC 0001. The implementation (community, role-profiles, site) is left to a separate release wave.
  The RFC does not change the Guide text.
- `rfcs/README.md`: RFC 0002 in the index.
- `HISTORY.md`: table of the changes from 0.2 to 0.3 that the narrative did not list.

### Changed

- **§9.1, scripted functional tests**: **replaced rule**. The test agent MUST NOT fix on its own either the
  candidate or its own test script; it reports every error to the AI Coordinator, which assigns the fix
  (MUST NOT, MUST, MAY). The sentence that let the agent fix gross errors on its own is removed.
- **§10, Backbone**: **replaced rule**. The first usable path runs through the Backbone in minimal form,
  together with the Brain and the essential interfaces; the Backbone is then completed before the other
  components are extended (MUST). "Built before all other components" is removed. Component contract refers
  to it.
- **§5, E5 Drift budget** (MUST broadened): expressed in spending and in time; class changes are also
  reported as an item of their own.
- **§7, Retrospective**: a model can be changed only among those the Role Profile enables and the mandate
  admits; operational decisions are the micro-decisions that touch neither approved Decisions nor reserved
  matters.
- **§8, Gates**: the AI Coordinator sets the gates and communicates them at the start of Discovery.
- **§14.1, Level 0 and Level 1 · Method** (MUST broadened): at level 0 the documents for the Human Manager
  include the milestone plan within the project record, the business risks within the cycle review, the High
  Level Architectural View and the progress dashboard; at level 1 the milestone plan and the business risks
  of the Risk Log become documents of their own.
- **§1 and §14**: "business owner" becomes "Human Manager" in three places.
- Title block, `README.md` and row R002 of `TRACEABILITY.md`: version 1.0.0-rc.3.
- `TRACEABILITY.md`: thirty rows marked "RFC 0003" for the new or changed paragraphs; all earlier rows kept.

### Fixed

- CI, `compliance.yml`: the local-path check removes http(s) URLs from the matched lines and matches
  again, so a path segment inside a URL (such as `/home/` in an official ISO URL) is no longer flagged.
  The block is the one of `role-profiles` v0.4.1 (the whole workflow file is now identical to that one).
  Change Requests CR-005 and CR-006 of the method project.

## [1.0.0-rc.2] - 2026-11-26

Second release candidate. Not yet in force. It implements [RFC 0001](rfcs/0001-context-blinding-discovery.md),
proposed by the Steward on behalf of the working groups not yet formed, from change request CR-003 and
the Human Manager's decisions Do-S03 to Do-S06. The Author accepted RFC 0001 on 26 November 2026, before
the end of its comment period (Do-S07, a recorded deviation), and decided its open points (Do-S08,
Do-S09).
Obligations are added or broadened, and one rule is replaced: convergence passes from a single model as
functional analyst to the Design Thinking Facilitator (see RFC 0001, "Rules replaced"). The Guide is not in
force, so the change is released as the next candidate.

### Added

- **§3, new principle "Context Consistency and Independence"** (MUST): agents that work on the same
  information share context; agents whose role needs divergence or independence work in independent
  contexts; the AI Coordinator applies it when it forms AI Squads and Discovery groups, and throughout
  execution.
- **§4, AI Reviewer** (MUST, SHOULD): extends the process reviewer to continuous monitoring of the framework
  and project KPIs, in parallel with the AI Coordinator and under hard blinding; a different model SHOULD
  be used where available (PA-6 B). It reports deviations to the AI Coordinator, which evaluates them
  and answers; critical or unaccepted deviations also go to the Human Manager in the Manager View
  (Do-S08). Its suggestions are data, not commands (MUST, MUST NOT).
- **§7, agent blinding**: hard blinding (MUST, MAY: environment, binding prompt, optional local model
  without retrieval) for the AI Coordinator, the AI Reviewer, the Design Thinking Facilitator and the
  Discovery reviewers; soft blinding with a context RACI (R, C, I) handed to each agent of an AI Squad.
  Blinding concerns project information, not the model's general knowledge (Do-S06).
- **§7, a new agent for every Work Package** (MUST), with a Work Package handover abstract at closing.
- **§8, Discovery as Design Thinking AI** (MUST): Discovery at the start of every project, tracked in the
  activity tree; the Discovery group, not an AI Squad, with independent contexts; Business Analyst and
  User Personas as project instances of qualified templates (Do-S04, PA-7 kept); executors under soft
  blinding and reviewers under hard blinding; the Discovery reviewers are the reviewer profiles of the
  governance domains the project touches, security and privacy always present (Do-S09); the Discovery
  report for the Human Manager.
- **§8, Design and planning as a Work Package** (MUST, MUST NOT): a dedicated Work Package that the AI
  Coordinator assigns and does not perform.
- **§8.1, Roles in the Discovery group and Discovery procedure** (descriptive): the functional analyst
  links business needs to the solutions of UX-UI designer and architects (Do-S05); the Facilitator's
  rounds; MOC means mock-up.
- `rfcs/0001-context-blinding-discovery.md`, with the audit of the principle in its appendix.

### Changed

- **§8, Convergence**: led by the Design Thinking Facilitator instead of a single model as functional
  analyst. Replaced rule, listed in RFC 0001. The first draft of Scope Management holds Vision,
  Principles, Decisions, success criteria and open points; the Human Manager approves the Vision at the
  end of Discovery, as in 1.0.0-rc.1.
- **§8, Phases and decisions**: Discovery yields the first draft of Scope Management; Design and planning
  refines its Principles and Decisions. The approvals, and the freezing of the Principles at the end of
  planning, are unchanged.
- **§7, Shared context, except for the unit tester**: a team shares one context within a Work Package.
  The unit tester rule is unchanged.
- **§8.1, Who works in each phase**: Discovery by the Discovery group; Design and planning by the team of a
  dedicated Work Package, without the AI Coordinator.
- **§9, Work Package record**: adds the context RACI and the Work Package handover abstracts (MUST
  broadened).
- **§9.1, Test types**: simulated-user functional tests are run by the User Personas (Do-S03). "Who
  supervises tests" keeps the PA-8 wording.
- **§3**: "Three principles" becomes "Four principles". Title block, `README.md` and row R002 of
  `TRACEABILITY.md`: version 1.0.0-rc.2.
- `TRACEABILITY.md`: twenty-one rows marked "RFC 0001" for the new or changed paragraphs; all earlier rows kept.
- `rfcs/README.md`: RFC 0001 in the index, accepted.
- **Verification note (D-VER-1).** The "Count check" of `TRACEABILITY.md` declares that key words in the
  boxed community-maintained notes, the §0 note on community-maintained sections and §15 Changing the
  method are not counted, since they carry RFC-process rules with no coverage row. It documents how the
  traceability check counts; no rule changes.

### Removed

- No rule without a replacement. The ten Guide lines that changed are quoted, old and new, in RFC 0001,
  "Rules replaced"; the only replaced rule is the convergence rule.

### Fixed

- **1.0.0-rc.1 entry, "Community-maintained sections"**: it listed the phase playbooks (§8.1) among the
  community-maintained sections. Under the Author's ratification (PA-1 × D-OPEN-4) only the adoption
  levels, the Digital Seniority catalogue and the test practices are community-maintained; §8.1 is
  maintained by the Author. The Guide text was already correct.

## [1.0.0-rc.1] - 2026-11-26

First release candidate of the Eiraman Guide. Not yet in force. It supersedes the Italian specification
0.3, which stays in `history/` as a non-normative copy.

The same normative content was published on 25 November 2026, during the restricted launch, under the
label "1.0-rc" (commit `f824888` of `github.com/eiraman/guide`, not tagged). This release adds only the
version label and the release files below; the tag `v1.0.0-rc.1` goes on the release commit of
26 November 2026, not retroactively on `f824888`.

Release changes against `f824888`:

- Version label normalised to Semantic Versioning: "1.0-rc" is now `1.0.0-rc.1` in the title block, in
  `README.md` and in row R002 of `TRACEABILITY.md`. No rule changes. Earlier records that say "v1.0-rc"
  (`AUTHOR-RATIFICATION.md`, the title of `TRACEABILITY.md`) refer to the same version.
- This changelog, and the CI workflow `changelog.yml`.

The main changes from the Italian specification 0.3, in summary. The row-by-row mapping is in
[TRACEABILITY.md](TRACEABILITY.md) (189 rows, each mapped to exactly one Guide paragraph), and the
editorial choices with their reasons are in [AUTHOR-RATIFICATION.md](AUTHOR-RATIFICATION.md) (PA-1 to PA-15).

### Changed

- **Language and licence.** Canonical English, under CC BY-SA 4.0; an Italian translation will follow.
  Copies of the specification distributed earlier keep CC BY-NC-ND 4.0.
- **Split of the method.** The specification 0.3 is split into this Guide (the stable core, changed only
  by RFC decided by the Author), the Extended Framework, the Tools and the Cases.
- **Normative language (PA-12).** Every normative rule carries an RFC 2119 / RFC 8174 key word in capitals
  (MUST, MUST NOT, SHOULD, SHOULD NOT, MAY); descriptive text carries none.
- **No numbers (PA-2).** The Guide describes each mechanism without its value. The mandate sets the values;
  the Extended Framework publishes indicative values (Guidance). This covers, among others, the Wave cost
  thresholds and the default number of candidates.
- **Definition (PA-10).** "Eiraman is a management method for governed vibe coding: AI-built software
  directed by a Human Manager."
- **Different model for security and personal data (PA-6).** A recommendation at every adoption level
  (SHOULD), with the level of independence achieved recorded (MUST).
- **Vendor neutrality (PA-3).** No model or tool names; Digital Seniority levels SD1–SD5 are described by
  task, and the mapping to providers lives in the Tools.
- **Legal anchoring (PA-11).** Exclusions and requirements by category, neutral to jurisdiction; the EU
  legal profile moves to the Extended Framework.
- **Examples (PA-13).** Generic examples only, with no project names; internal references of the
  specification were removed.
- **Terminology (PA-9).** Human Manager, AI Coordinator, tier, SD level, adoption level.

### Added

- **Broad Guide (PA-1 C).** The Digital Seniority catalogue rules (§7.1), the phase playbooks (§8.1), the
  test practices (§9.1) and the requirements per adoption level (§14.1, §14.2) are in the Guide. All but
  the phase playbooks are community-maintained sections, kept by the working groups and accepted by the
  Author by RFC; the phase playbooks are maintained by the Author (corrected in 1.0.0-rc.2).
- **Changing the method.** Maintainers and working groups for the Extended Framework, and the RFC process
  for the Guide (§4, §15).
- `history/`: the Italian specification 0.3, non-normative, under CC BY-SA 4.0; `rfcs/` with the RFC
  template.

### Removed

- The DCO rule (PA-5): it lives only in `CONTRIBUTING.md` of the organisation.
- "The method as an Eiraman project" (PA-4) as a Guide rule: it stays a practice of the Author.
- Citations in the Guide body (PA-15): sources go to the body of knowledge of the Extended Framework.

## Before 1.0.0-rc.1

The method was published before as an Italian specification, numbered 0.1, 0.2 and 0.3 (November 2026),
which are not versions of this Guide and were not released from this repository. Their content is
summarised in [HISTORY.md](HISTORY.md); the text of 0.3 is in [history/](history/).

[Unreleased]: https://github.com/eiraman/guide/compare/v1.0.0-rc.6...main
[1.0.0-rc.6]: https://github.com/eiraman/guide/compare/v1.0.0-rc.5...v1.0.0-rc.6
[1.0.0-rc.5]: https://github.com/eiraman/guide/compare/v1.0.0-rc.4...v1.0.0-rc.5
[1.0.0-rc.4]: https://github.com/eiraman/guide/compare/v1.0.0-rc.3...v1.0.0-rc.4
[1.0.0-rc.3]: https://github.com/eiraman/guide/compare/v1.0.0-rc.2...v1.0.0-rc.3
[1.0.0-rc.2]: https://github.com/eiraman/guide/compare/v1.0.0-rc.1...v1.0.0-rc.2
[1.0.0-rc.1]: https://github.com/eiraman/guide/releases/tag/v1.0.0-rc.1
