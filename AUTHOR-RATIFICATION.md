<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# Editorial choices ratified by the Author

The Eiraman Guide v1.0-rc rests on fifteen editorial points (PA-1 to PA-15) reserved to the Author. The Author **ratified them on 25 November 2026**. The table gives the chosen alternative for each point and where it applies. The Guide source no longer carries "pending" markers.

| Point | Subject | Ratified choice | Where in the Guide |
|---|---|---|---|
| PA-1 | Boundary between Guide and Extended Framework | **C · Broad Guide** (about 25 pages). The Digital Seniority catalogue rules, the phase playbooks, the test practices and the requirements per adoption level, including automatic downgrade and the deliberately vulnerable test suite, are part of the Guide | §7.1, §8.1, §9.1, §14.1, §14.2 |
| PA-1 × community governance | Who maintains the new parts | **Community-maintained sections.** The sections on adoption levels, the Digital Seniority catalogue and the test practices carry a boxed note: the responsible working groups propose changes and the Author accepts them via RFC without rewriting | §0 Community-maintained sections; notes at the start of §7.1, §9.1 and §14; §15 Changing the method |
| PA-2 | Numbers in the Guide | **C · No numbers.** The Guide describes each mechanism without its value, the early warning and the Deny threshold of a Wave and the default number of candidates included. The mandate sets the values; the Extended Framework gives indicative values (Guidance) | §0 Values and Guidance; §5 Do, E5, E6, Urgent containment; §6 K3; §7.1 Fallback, Promotion and reduction; §8 Divergence, Wave, Declared and observed values; §9 High Level Architectural View; §12 Length limits, Comprehension test; §14.1 |
| PA-3 | Vendor neutrality | **A.** No model or tool names; SD1–SD5 described by task; the mapping to providers lives in the Tools | §7 Digital Seniority |
| PA-4 | Governance of the method and maintainers | **A.** Maintainers of the Extended Framework, organised in working groups; the Guide changes by RFC decided by the Author with written reasons; "the method as an Eiraman project" stays a practice of the Author | §4 Maintainers; §15 Changing the method |
| PA-5 | Contribution rule | **A.** The DCO lives only in `CONTRIBUTING.md` | none |
| PA-6 | Different model for security and personal data | **B · Recommendation everywhere.** At every adoption level, verification of Work Packages that touch security or personal data SHOULD use at least a different model; the level of independence achieved MUST be recorded | §6 Security and personal data; §7 Shared context |
| PA-7 | High-tier roles | **A.** High-tier roles MUST start from a qualified Role Profile; the mandate adds context without altering the profile | §7 Role tiers |
| PA-8 | "Human-supervised" functional tests | **A.** "The person MAY watch functional tests, but their progress MUST NOT depend on the person", now in the Guide's test practices | §9.1 Who supervises tests |
| PA-9 | Canonical English terminology | **A.** Human Manager, AI Coordinator, Method (component), tier, SD level, adoption level; Backbone, Brain, Limbs and Senses, Hairs | whole text |
| PA-10 | "Vibe coding" in the definition | **B · "Governed vibe coding".** "Eiraman is a management method for governed vibe coding: AI-built software directed by a Human Manager." The theory section uses the same term | §1 Definition; §2 Why Eiraman exists |
| PA-11 | Legal anchoring | **A.** Exclusions and requirements by category, neutral to jurisdiction; the EU legal profile with the articles is in the Extended Framework | §3; §14; §14.1 |
| PA-12 | Normative convention | **B · RFC 2119 capitals.** The key words MUST, MUST NOT, SHOULD, SHOULD NOT and MAY, interpreted as in RFC 2119 and RFC 8174 only in capitals, are declared once. Every normative row carries one, R023, R024, R040, R075, R076, R212 and R213 included; descriptive text carries none | §0 Normative language; whole text |
| PA-13 | Pilot-project examples | **A.** Generic examples only; no project names | §9 Two results; §14 Deliverables |
| PA-14 | Title, numbering and history | **A.** "The Eiraman Guide", version 1.0; the history is in `HISTORY.md`, and the Italian specification 0.3 is kept as a non-normative copy in `history/` | Title block; §16 Version history |
| PA-15 | Sources of the theory | **A.** No citations in the Guide body; sources in the body of knowledge of the Extended Framework | §2; §6 Rationale |

## Related decisions applied

- **Attribution.** "The Eiraman Guide by Paolo Ungari and contributors", in the title block, in `LICENSE.md` and in the SPDX and REUSE copyright text.
- **Historical specification.** The Italian specification 0.3 is in `history/` under CC BY-SA 4.0, with a non-normative banner; copies distributed earlier remain under CC BY-NC-ND 4.0. The internal references removed from it are listed in `history/README.md`.

## Checks on the ratified text

- **Traceability.** Every G row of the coverage table maps to exactly one paragraph of the Guide (`TRACEABILITY.md`, 189 rows).
- **Key words.** A script checks that every paragraph carrying a normative row contains a key word in capitals, and that no other paragraph does.
- **Numbers.** The only figures left in the Guide are section numbers, versions, RFC and standard numbers, rule and level identifiers (E1–E6, K1–K9, SD1–SD5, classes and levels 0 to 2) and the ratification date.

## Consistency notes for the community files

- The project governance cites Guide §5 (escalation), §13 (Role Profiles) and §14 (applicability gate). These numbers are unchanged; the new parts are subsections §7.1, §8.1, §9.1, §14.1 and §14.2.
- Level requirements, the deliberately vulnerable test suite and the Digital Seniority catalogue are now Guide text, maintained by the working groups and accepted by the Author via RFC. The community files that still place them in the Extended Framework need aligning.
