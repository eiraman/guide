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

- `rfcs/0002-governo-family.md` (CR-007): regularises the Role Profile family `governo/`, created in Wave
  DT-01 without an RFC and without a family group (Do-S16). Three alternatives are kept for the record; the
  Author, who is also the Steward in Stage 1, accepted alternative B on 2026-11-26 (Do-S18): a new working
  group "Governance & Assurance" owns the family, and the reviewers of record of each domain co-review its
  reviewer profile. Accepted before the end of the thirty-day comment period, a recorded deviation as for
  RFC 0001. The implementation (community, role-profiles, site) is left to a separate release wave.
  The RFC does not change the Guide text, so the Guide version stays 1.0.0-rc.2 (VERSIONING §1: the
  version source is the Guide title block).
- `rfcs/README.md`: RFC 0002 in the index.

### Fixed

- CI, `compliance.yml`: the local-path check removes http(s) URLs from the matched lines and matches
  again, so a path segment inside a URL (such as `/home/` in an official ISO URL) is no longer flagged.
  The block is the one of `role-profiles` v0.4.1 (the whole workflow file is now identical to that one). Change Requests CR-005 and CR-006 of the
  method project.

This change is not a Guide release: the Guide version is the one in the title block of `EIRAMAN-GUIDE.md`,
and a workflow change leaves the Guide text unchanged (VERSIONING §1, notes). It stays under `[Unreleased]`,
no tag is planned for it, and it is released with the next Guide version.

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

[Unreleased]: https://github.com/eiraman/guide/compare/v1.0.0-rc.2...main
[1.0.0-rc.2]: https://github.com/eiraman/guide/compare/v1.0.0-rc.1...v1.0.0-rc.2
[1.0.0-rc.1]: https://github.com/eiraman/guide/releases/tag/v1.0.0-rc.1
