<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# RFC 0002: Regularise the Role Profile family `governo/` and its working group

- **Author(s):** the Steward
- **Accountable human:** Paolo Ungari (Steward)
- **AI-Use:** substantial (CONTRIBUTING.md §3)
- **Assisted-by:** Claude Opus 5.5
- **Conflicts of interest:** none. The Steward proposes this RFC and, in Stage 1, also decides it (see Decision maker)
- **Owner of the decision:** the Steward, in Stage 1 (GOVERNANCE §2, §3 Stage 1, §10); in Stage 1 the Steward is also the Author
- **Affected artifacts:** governance (`community/WORKING-GROUPS.md`, possibly `GOVERNANCE.md` §2), `community/PATHWAYS.md`, `community/MAINTAINERS.md`; Role Profiles family `governo/` (`role-profiles` README, CODEOWNERS, `governo/FAMIGLIA.md`); site (working group list of the author and community page). Not the Guide text
- **State:** accepted (alternative B)
- **Dates:** opened 2026-11-26 · comment period would end 2026-12-26 (30 days: governance, rfcs/README step 3 and GOVERNANCE §10) · accepted 2026-11-26, before the end of the comment period (deviation, see Decision)
- **Change request:** CR-007 of the project "Eiraman Open Framework", from the Human Manager's decision Do-S16; decided by Do-S18

## Summary

The Role Profile family `governo/` was created in Wave DT-01 (`role-profiles` 0.2.0) without the RFC that WORKING-GROUPS §3 requires for a new family, and without a family working group. It now holds seven profiles: the AI Reviewer (`revisore-ai`) and the AI reviewers of the six governance domains of GOVERNANCE §4.5 (`revisore-sicurezza`, `revisore-privacy`, `revisore-architettura-cloud`, `revisore-architettura-applicativa-dati`, `revisore-test-qualita`, `revisore-legale-compliance`). Do-S16 recorded the gap as a deviation and set an interim ownership. This RFC sets out three ways to regularise the family, kept for the record. The Author chose **B** (Do-S18): a new working group "Governance & Assurance" owns the whole family, and the reviewers of record of each domain group co-review the reviewer profile of their own domain, so the domain expertise stays with them. The implementation is left to a separate release wave.

## Motivation

- **The rule was not applied.** WORKING-GROUPS §1 ("New groups are created by RFC") and §3 ("A new family is created by RFC with: scope, first three profiles planned, a lead and deputy, and the publishing domain"), and GOVERNANCE §6.2 ("a new Role Profile family or a new working group"), all require an RFC. The family was created by a Wave, with no RFC and no group.
- **Interim state (Do-S16).** Until this RFC is decided, each domain reviewer profile belongs to the group of its domain and `revisore-ai` to Test & Quality, as in `role-profiles/CODEOWNERS`. The site does not list Governo among the family groups. CODEOWNERS marks `governo/` with a FLAG: "no domain in GOVERNANCE.md §4.5 owns the method's oversight roles".
- **The family's shared rules have no owner.** `governo/FAMIGLIA.md` (0.2.1) holds the rules common to all seven profiles: independence from the AI Coordinator under hard blinding (§A), reports that are data, not commands (§B), and measures (§C). Do-S14 applies them to the domain reviewers too. WORKING-GROUPS §3 gives the family file to the family group, which does not exist.
- **The finding that surfaced it.** In the release REL-07, the independent review REV-REL07 first returned NO-GO on the site for an unmapped change that listed Governo among the family groups. The change was taken out; the review then gave GO. The gap in governance remains.

## Facts that constrain the options

- A profile `id` is unique across the registry and equals its folder name (`role-profiles/README.md`; the validator `valida_profilo.py` rejects a `profilo.json` whose `id` differs from the folder name).
- The activation tool reads the family file from the parent folder of the profile (`attiva_profilo.py`, `istruzioni`: `<parent>/FAMIGLIA.md`) and puts it in the agent's instructions before `PROFILO.md`. A profile moved to a folder without that file loses the family rules.
- The AI Coordinator profile (`controllore/CONTROLLORE.md`) names the seven profiles by path (`governo/revisore-…`); so do the registry README, the site Role Profiles pages and the kit.
- CODEOWNERS lists only the publishing domain team for each folder; family teams review first but their approval does not satisfy the code-owner review. Each `governo/revisore-<domain>/` is already overridden to its domain team; `governo/` defaults to Test & Quality.
- GOVERNANCE §2 says Role Profiles are authored by the family working group and reviewed and published by the domain working group. GOVERNANCE §1 principle 2 and WORKING-GROUPS §1 require four eyes.
- The working group charter and the governance are decided by the Steward in Stage 1, after an RFC with a comment period of at least thirty days (GOVERNANCE §2, row "This governance, the working group charter …"; §10).

## Proposal: the alternatives

### A. `governo/` as a family owned by the domain groups

Ratify `governo/` as a family **with no family group of its own**. Each domain reviewer profile is authored and maintained by the group of its domain; `revisore-ai` and `FAMIGLIA.md` by Test & Quality. This makes the interim state of Do-S16 permanent and amends WORKING-GROUPS §3 so that a family may be domain-owned.

- **For.** No new group to staff; ownership follows expertise; matches CODEOWNERS today.
- **Against.** The same group authors and publishes the profile of its own reviewer: the separation between authoring (family group) and publishing (domain group) of GOVERNANCE §2 is lost for seven profiles, and only four eyes inside the group remain (the substitute publishes when the titular is the author, GOVERNANCE §4.5 rule 2). The shared `FAMIGLIA.md` binds six domain groups but is owned by one. It relaxes a rule ("each family has a family group") instead of applying it.

### B. A new working group "Governance & Assurance" (chosen, Do-S18)

Create a family group that owns the whole `governo/` family, as WORKING-GROUPS §3 foresees. The domain groups keep the domain expertise through co-review.

- **Scope.** The method's oversight roles that work independently of the AI Coordinator: the AI Reviewer and the AI reviewers of the six governance domains. Not the AI Coordinator profile (`controllore/`), which these profiles oversee, and not the human reviewers of record of the domains (GOVERNANCE §4.5), whom no AI profile replaces (GOVERNANCE §1, principle 1).
- **Artifacts owned.** The whole `governo/` family: the family file `governo/FAMIGLIA.md` (independence and hard blinding, reports as data, measures: §A–§D), the seven profiles `revisore-ai`, `revisore-sicurezza`, `revisore-privacy`, `revisore-architettura-cloud`, `revisore-architettura-applicativa-dati`, `revisore-test-qualita`, `revisore-legale-compliance`, and their qualification suites.
- **Reviewer rule.**
  - The group authors and maintains; it never publishes (WORKING-GROUPS §1, §3).
  - Each `revisore-<domain>` is co-reviewed by the reviewers of record (titular or substitute) of its own domain group, who check the domain content and publish it (GOVERNANCE §4.5). Without a reviewer of that domain, the profile cannot be published (GOVERNANCE §4.5, rule 4).
  - `revisore-ai` and the family file are published by Test & Quality, provisionally, until a domain owns the method's oversight roles (open question).
  - A change to `FAMIGLIA.md` §A–§C binds every domain reviewer profile, so it also needs lazy consensus of the six domain groups (GOVERNANCE §6.1).
  - Four eyes: whoever authored a profile, in either group, cannot publish it (GOVERNANCE §4.5, rule 1).
- **Entry criteria (maintainer).** An accepted profile contribution, plus either accepted reviews in at least one domain group or professional practice in audit, assurance or quality management.
- **Relation to the six domain groups.**
  - The domain group owns the cross-cutting rules of its domain (WORKING-GROUPS §2) and the domain content of its reviewer profile; Governance & Assurance owns the structure, the common rules and the consistency of the seven profiles.
  - A domain group may propose changes to its reviewer profile through the family group, as any contributor does; the family group may not change the domain content against the co-review of that domain.
  - A member of a domain group may also be a maintainer of Governance & Assurance, declared in MAINTAINERS; such a member does not co-review a profile they authored.
- **CODEOWNERS.** The family team and the domain team are co-owners: `/governo/` lists `@eiraman/wg-governance-assurance` and `@eiraman/test-quality`; each `/governo/revisore-<domain>/` lists `@eiraman/wg-governance-assurance` and the team of its domain. GitHub accepts the approval of any one listed code owner, so co-ownership alone does not make the domain approval mandatory; the release wave adds the enforcement (see Implementation of B).
- **Lead and deputy.** Appointed by the Steward in Stage 1, with written reasons (GOVERNANCE §3, §4.4). Until they are appointed, the interim ownership of Do-S16 continues.
- **For.** Applies the existing rule without changing it; keeps authoring separate from publishing; gives the shared family file a single owner; keeps the domain expertise with the domain groups. The family already meets "first three profiles planned".
- **Against.** One more group to staff while no group has members; possible overlap with the domain groups, handled by the relation above.

### C. Split the family into the domain areas

Move each domain reviewer profile out of `governo/` into an area of its domain group, for example `sicurezza/revisore-sicurezza/`. The domain areas are not families today, so either each becomes a family of one profile, or a new kind of non-family folder is introduced. `revisore-ai` stays alone in `governo/` (which still needs A or B) or moves to `controllore/`, which is not a family either.

- **Paths and IDs.** If the folder names are kept, the `id`s stay valid, but every path changes: CODEOWNERS, `CONTROLLORE.md`, README, the site pages and the kit, and any project that pinned a path. If the folders are renamed (for example into English), the `id`s change too, because the `id` equals the folder name. Either way it is a **breaking** change of the registry.
- **Family rules.** Each new folder needs its own `FAMIGLIA.md`, or the activation tool no longer gives the agent the rules of §A–§C. Six copies of the same rules would drift.
- **Governance.** Single-profile families do not meet "first three profiles planned" (WORKING-GROUPS §3); a non-family folder needs a new kind of area in WORKING-GROUPS and in GOVERNANCE §2.
- **For.** Ownership by domain is visible in the folder layout.
- **Against.** Breaking, costly, scatters the shared rules, and still leaves `revisore-ai` unresolved.

### Recommendation and choice

The RFC recommended **B**, and the Author chose it (Do-S18). It is the only alternative that applies WORKING-GROUPS §3 as written, keeps the separation between those who write a profile and those who publish it, and gives one owner to the family rules that bind all seven profiles. A relaxes a rule and lets each domain group publish the profile of its own reviewer; C breaks paths, scatters the family rules and does not settle the AI Reviewer. B costs one group to staff, and the interim ownership of Do-S16 covers the time until it has a lead and a deputy.

## Changes per alternative

### Community

| Document | A | B | C |
|---|---|---|---|
| `WORKING-GROUPS.md` | §3: a family MAY be owned by the domain groups instead of a family group, with the owning group of each profile and of the family file named; add a "Governo" row (owners: domain groups; `revisore-ai` and family file: Test & Quality); last line: the RFC for a domain-owned family names the owning groups instead of a lead and deputy | §3: add the "Governance & Assurance" row (scope, artifacts, reviewer rule, entry criteria as above); §2: under each domain group, note that it publishes its reviewer profile in `governo/` | §2: each domain group owns its reviewer profile and folder; §3: rule for single-profile domain folders or a new kind of area; `revisore-ai` per A or B |
| `GOVERNANCE.md` | §2, row "Role Profiles": add "or, for a domain-owned family, the owning domain group (authoring)" | No change | §2, row "Role Profiles": add the domain folders |
| `PATHWAYS.md` | Role Profile author, existing families: add Governo, "owned by the domain groups"; registry count (now 47 profiles in 8 families, the text says 40 in 7) | Existing families: add Governo (Governance & Assurance); registry count | Paths of the domain reviewers; registry count |
| `MAINTAINERS.md` | "Maintainers by area": `Role Profiles / governo` → the domain groups and Test & Quality | "Working group leads": add Governance & Assurance; "Maintainers by area": `Role Profiles / governo` | "Maintainers by area": one row per new folder |
| `CHANGELOG.md` | Entry with the RFC | Entry with the RFC | Entry with the RFC |

### Role Profiles

| File | A | B | C |
|---|---|---|---|
| `README.md` | Families table: Governance, "owned by the domain groups (RFC 0002)" | Families table: Governance, "Governance & Assurance" | New folders and paths; the family table changes |
| `CODEOWNERS` | Replace the FLAG on `/governo/` with a reference to RFC 0002; owners unchanged | Comment: family maintainer team `@eiraman/wg-governance-assurance` reviews first (not listed, as for every family); FLAG reduced to `revisore-ai` and the family file; owners unchanged | Move the six overrides to the new paths; `/governo/` per A or B |
| `governo/FAMIGLIA.md` | Header: owning groups per profile | Header: owner Governance & Assurance; changes to §A–§C need the domain groups | A copy, or an equivalent file, in each new folder |
| Profiles (`PROFILO.md`, `profilo.json`) | No change | No change | Paths and family references; `CONTROLLORE.md` paths |

### Site

| Item | A | B | C |
|---|---|---|---|
| Author and community page, "Family groups" (`content.py`, Italian and English) | Add "Governo (domain groups)" | Add "Governance & Assurance" | No new family group; Role Profiles pages and kit follow the new paths |

### Versions (VERSIONING)

| Artifact | A | B | C |
|---|---|---|---|
| `community` (0.3.0) | WORKING-GROUPS §3 no longer requires a family group: a requirement removed, MAJOR, so in `0.y.z` a MINOR marked **breaking** (§2.1, §2.6): 0.4.0 | A group and a practice added: MINOR (§2.1): 0.4.0 | New kind of area and changes to §2 and GOVERNANCE §2: MINOR at least; breaking if a family requirement is relaxed: 0.4.0 |
| `role-profiles` registry (0.4.1) | Documentation and comments only: PATCH (§2.2): 0.4.2 | PATCH: 0.4.2 | Paths moved: breaking, MINOR marked **breaking** in `0.y.z`: 0.5.0. A renamed folder also changes an `id`, which is MAJOR for that profile (§2.2) |
| `governo/FAMIGLIA.md` (0.2.1) | Header only: PATCH | Header and the new co-review rule: MINOR | New files per folder |
| AI Coordinator profile | No change | No change | Paths: PATCH |
| `site` (0.7.0) | Content: MINOR (§2.4): 0.8.0; kit PATCH if the bundled family file has a PATCH | Same as A | MINOR; kit MINOR, because the bundled registry has a MINOR |
| `tools` | No change | No change | No code change; the activation tool's behaviour depends on the family file of each new folder |
| `guide` | No change of the Guide text or version | Same | Same |

## Implementation of B

For a separate release wave, under RELEASING. The interim ownership of Do-S16 stays until that wave is released.

| Repository | File | Exact change | Version (VERSIONING) |
|---|---|---|---|
| `community` | `WORKING-GROUPS.md` §3 | Add the row **Governance & Assurance**: scope, artifacts owned, reviewer rule (co-review by the reviewers of record of each domain; `revisore-ai` and family file by Test & Quality, provisionally; changes to FAMIGLIA §A–§C with lazy consensus of the six domain groups), entry criteria, as in B above | MINOR: a group and a rule added (§2.1) |
| `community` | `WORKING-GROUPS.md` §2 | In "Artifacts owned" of each domain group: "co-review and publication of its AI reviewer profile in `governo/`"; Test & Quality also: "`revisore-ai` and `governo/FAMIGLIA.md`, provisionally" | Same MINOR |
| `community` | `WORKING-GROUPS.md` §5 | Open point: no domain owns the method's oversight roles | Same MINOR |
| `community` | `GOVERNANCE.md` | No change: §2 "Role Profiles" (family group authors, domain group reviews and publishes) already covers B. If the wave adds co-review to §4.5, it is a governance amendment (§10) | None |
| `community` | `PATHWAYS.md` | Role Profile author, existing families: add "Governance (Governance & Assurance)"; registry count from "40 profiles in 7 families" to the current "47 profiles in 8 families" | Same MINOR (PATCH alone) |
| `community` | `MAINTAINERS.md` | "Working group leads": add Governance & Assurance (`<handle>`, `<handle>`, no); "Maintainers by area": add `Role Profiles / governo` | Same MINOR (PATCH alone, §2.5) |
| `community` | `CHANGELOG.md` | Entry citing RFC 0002 and Do-S18 | `community` 0.3.0 → 0.4.0 |
| `role-profiles` | `CODEOWNERS` | `/governo/` → `@eiraman/wg-governance-assurance @eiraman/test-quality`; each `/governo/revisore-<domain>/` → `@eiraman/wg-governance-assurance` plus its domain team; replace the FLAG with "family owned by Governance & Assurance (RFC 0002); `revisore-ai` and FAMIGLIA published by Test & Quality, provisionally"; update the header comment, which says that each folder lists only the domain team | Registry PATCH |
| `role-profiles` | Enforcement | A required check, or a ruleset, so that a change under `/governo/revisore-<domain>/` needs the approval of that domain team, not only of the family team. Owner: DevSecOps & Tooling | Registry PATCH if CI only; `.github` per its own rules |
| `role-profiles` | `README.md` | Families table: Governance, `governo/`, 7, with "Governance & Assurance (RFC 0002)" | Registry PATCH |
| `role-profiles` | `governo/FAMIGLIA.md` | Header: owner Governance & Assurance; co-review by the reviewers of record of each domain; rules §A–§D unchanged | Family file 0.2.1 → 0.2.2 (PATCH) |
| `role-profiles` | `CHANGELOG.md` | Entry citing RFC 0002 | Registry 0.4.1 → 0.4.2 (PATCH, §2.2) |
| `site` | `generator/content.py`, Italian and English | "Gruppi di famiglia" / "Family groups": add "Governance & Assurance"; the description of family groups stays | Site 0.7.0 → 0.8.0 (MINOR, content, §2.4); kit PATCH, because the bundled `governo/FAMIGLIA.md` has a PATCH |
| `guide` | none | The Guide text does not name families or groups | None |

## Decision maker

In Stage 1 the Steward decides, with written reasons:

- the working group charter and the governance are owned by the Steward in Stage 1 (GOVERNANCE §2, table, row "This governance, the working group charter and licence policy for new material") and amended by RFC with a comment period of at least thirty days, decided by the Steward (GOVERNANCE §10);
- the creation of working groups is a duty of the Steering Committee (GOVERNANCE §4.3), held by the Steward in Stage 1 (GOVERNANCE §3, Stage 1);
- a new family or working group needs an RFC (GOVERNANCE §6.2; WORKING-GROUPS §1 and §3).

The Author decides only Guide RFCs (GOVERNANCE §6.3); this RFC does not change the Guide text. In Stage 1 the Steward and the Author are the same person (GOVERNANCE §3), so the decision recorded below as the Author's (Do-S18) is also the Steward's decision under GOVERNANCE §2 and §10.

## Reversibility

Creating a group or a family rule is a one-way door in the governance (GOVERNANCE §1 principle 5, §6.2). A and B are cheap to reverse in the files (rows and comments), but reversing them moves ownership again and, for A, would restore a requirement (breaking). C is costly to reverse: moving the folders back breaks paths a second time.

## Impact

- **Adopters.** None for A and B: paths and profiles do not change. C breaks every pinned path to a domain reviewer.
- **Role Profiles.** The seven `governo/` profiles keep their state *draft*; their qualification still needs a human reviewer of each domain (Do-S13, Do-S15).
- **Tools.** None for A and B. For C, the activation tool needs a family file in every new folder.
- **Site.** The Governo entry appears among the family groups only after the decision (Do-S16).
- **Translations.** None published.

## Alternatives not developed

- **Do nothing.** Leaves a family that breaks WORKING-GROUPS §3 and a deviation open without end.
- **Move `governo/` into `controllore/`.** Puts the overseers in the folder of the role they oversee, against the independence of FAMIGLIA §A.

## Acceptance evidence

- The decision recorded below, with written reasons, after the comment period.
- The community, role-profiles and site releases that implement it, each with its `release_diff` report and independent scope review (RELEASING).
- For C only: the validator and the activation tool run on every moved profile.

## Open questions

- **Publishing domain of `revisore-ai` and of the family file.** No domain of GOVERNANCE §4.5 owns the method's oversight roles; Test & Quality publishes them provisionally, as for `controllore/`. A new domain would need its own RFC (GOVERNANCE §4.5, §6.2).
- **The Steward proposes and decides.** In Stage 1 the Steward is both the proposer of this RFC and its decision maker. The comment period, written reasons and the independent scope review of the releases are the checks available.
- **Site before the release.** Do-S16 keeps Governo off the family groups list until the implementation wave is released; the Role Profiles page already shows the family and its seven profiles.
- **Enforcing co-review.** CODEOWNERS cannot require two owners; the required check or ruleset is to be designed by DevSecOps & Tooling in the release wave.

## Decision

**Accepted, alternative B**, on 2026-11-26, by the Author, who in Stage 1 is also the Steward (Do-S18).

Written reasons: B applies WORKING-GROUPS §3 as written, keeps authoring separate from publishing, gives one owner to the family rules, and keeps the domain expertise with the domain groups through co-review. No community member is active yet; founding contributors may reopen it with a new RFC.

**Deviation from the comment period.** The decision was taken on the day the RFC was opened, before the thirty days that GOVERNANCE §10 and `rfcs/README.md` set for governance changes, as Do-S07 did for RFC 0001. The deviation is recorded here and in the changelog; it does not change the process for later RFCs.

**Implementation.** In a separate release wave, as listed in "Implementation of B". Until it is released, the interim ownership of Do-S16 applies.
