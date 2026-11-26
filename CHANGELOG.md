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

- **Community-maintained sections (PA-1 C).** The Digital Seniority catalogue rules (§7.1), the phase
  playbooks (§8.1), the test practices (§9.1) and the requirements per adoption level (§14.1, §14.2) are
  in the Guide, kept by the working groups and accepted by the Author by RFC.
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

[Unreleased]: https://github.com/eiraman/guide/compare/f824888ba2295143217f3eb30484d5e042b427fa...main
[1.0.0-rc.1]: https://github.com/eiraman/guide/compare/f824888ba2295143217f3eb30484d5e042b427fa...main
