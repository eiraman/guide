<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# RFC 0006: The managerial role extends to security, in "Why Eiraman exists"

- **Author(s):** the Author, by request; text drafted by the AI Coordinator
- **Accountable human:** Paolo Ungari (Author)
- **AI-Use:** substantial (CONTRIBUTING.md §3)
- **Assisted-by:** Claude Opus 5.5 (drafting)
- **Conflicts of interest:** none
- **Owner of the decision:** Author (Guide)
- **Affected artifacts:** Guide §2 (Why Eiraman exists); `TRACEABILITY.md`. After acceptance, in separate releases: the Italian translation, and the site and kit where they present why Eiraman exists
- **State:** accepted
- **Dates:** opened 2026-11-27 · comment period ends 2026-12-11 · accepted 2026-11-27, before the end of the comment period (deviation, see Decision)
- **Change request:** CR-031 of the project "Eiraman Open Framework"; decided by D-031

## Summary

The paragraph "Why Eiraman exists" (§2) gives one reason for the method: the limits of human-in-the-loop and human-on-the-loop control where there is no development team. This RFC adds a second one. Vibe coding sharply increases the data people handle, often without the competence needed to see the risks. In Eiraman the managerial role extends to security: a Human Manager who delegates a task knows what that choice implies for security, privacy and regulatory compliance. For one's own use this knowledge is, by default, information; in work and organisational contexts it is blocking by default: the adoption levels and the Applicability gate stop what the qualified level does not allow, except what the Human Manager decides to run above it under the conditions of §14.2 (Running above the qualified level). The mechanism already exists in Guide 1.0.0-rc.5: the classification modes, the adoption levels and the Applicability gate (§14), the Security Report (§12) and the Security Officer. The RFC states it in the theory and points to it. It adds, removes and changes no rule.

## Motivation

The Human Manager, who is also the Author of the Guide, asked on 27 November 2026 (CR-031):

> Il ruolo manageriale di Eiraman si esplicita anche nella sicurezza. Un altro dei grandi problemi del Vibe Coding è che nello sviluppare applicazioni aumentiamo considerevolmente la quantità di dati che gestiamo, spesso senza avere le competenze necessarie per capire i rischi. In Eiraman un manager umano che demanda lo sviluppo di un task sa quali implicazioni ha questa sua scelta da un punto di vista di sicurezza, privacy e compliance normativa. Questo in usi privati è una sola informazione ma diventa bloccante in contesti di lavoro e di organizzazioni. Questa è una modifica da considerare già nel «Perché esiste Eiraman».

In English:

> The managerial role of Eiraman is made explicit in security too. Another of the great problems of vibe coding is that, in developing applications, we considerably increase the amount of data we handle, often without the competence needed to understand the risks. In Eiraman a human manager who delegates the development of a task knows what implications this choice has from the point of view of security, privacy and regulatory compliance. In private use this is only information, but it becomes blocking in work and organisational contexts. This is a change to be considered already in "Why Eiraman exists".

The request continues an earlier statement of the Human Manager (CR-015, 26 November 2026): in organisations many people build small personal applications with AI without being aware of the data they handle and of the risk they are exposed to, the theft of the device being an example; the adoption levels and the check at the opening let them work consciously and limit the risk.

Since 1.0.0-rc.1 "Why Eiraman exists" speaks only of the limits of point control. RFC 0005 made the classification work in two modes and changed the item *Scope and risk management* of "Management applied to AI", but the reason the method gives for existing still says nothing of data and security. A reader who stops at §2 does not learn that the Human Manager's role covers them.

## Proposal

In §2, at the end of the paragraph **Why Eiraman exists**, after "and the AI system answers with evidence.", add:

> Vibe coding also sharply increases the data people handle, often without the competence needed to see the risks. In Eiraman the managerial role extends to security: a Human Manager who delegates a task knows what that choice implies for security, privacy and regulatory compliance, because the classification of the project and the Security Officer make it known (§14). When the adopter uses the method for themselves, this knowledge is, by default, information, recorded in the Security Report (§12); in work and organisational contexts it is blocking by default: the adoption levels and the Applicability gate stop what the qualified level does not allow, except what the Human Manager decides to run above it under the conditions of §14.2 (§14, Classification mode).

Notes on the text:

- "blocking by default" follows §14, Classification mode: without a choice the informative mode applies when the adopter uses the method for themselves and the blocking mode in every other case, doubt included; the Human Manager may choose the informative mode, unless the rules of the organisation impose the blocking one. "Binding" without qualification would have contradicted that rule.
- "by default" in the first half follows the same rule: for one's own use the informative mode applies only when no mode is chosen, and the Human Manager may choose the blocking one.
- "except what the Human Manager decides to run above it" follows §14.2, Running above the qualified level: in the blocking mode a class 1 project may run in an adoption qualified at level 0 by an explicit, recorded decision of the Human Manager, and no other class or level. Without the exception the sentence would have contradicted that rule.
- The text carries no RFC 2119 key word: §2 is theory, and the rules it points to are in §12 and §14.
- It names no provider, product or jurisdiction (PA-3, PA-11).
- The item *Scope and risk management* of "Management applied to AI" already says that the adoption levels "limit risk up front or, in the informative mode, make it known" (RFC 0005). It is consistent with the new text and is not changed.

## Reversibility

A change to the Guide text is a one-way door (GOVERNANCE §6.2). This one is descriptive: it adds, removes and reverses no obligation, so for a version in force it would not be a MAJOR or a MINOR change under VERSIONING. While the Guide is a release candidate, rolling back costs a new candidate that removes the three sentences.

## Impact

- **Normative.** None. No key word is added, removed or changed; no rule of §12 or §14 changes. The counts of RFC 2119 key words in `EIRAMAN-GUIDE.md` are those of 1.0.0-rc.5.
- **Adopters.** None on projects in progress or on applicability levels. The Guide now states up front that the role of the Human Manager covers the security, privacy and compliance implications of delegating.
- **Role Profiles.** None to requalify.
- **Tools.** None.
- **Translations.** The Italian translation (`translations/it/`, 1.0.0-rc.5+it.1) must translate the three sentences and move to 1.0.0-rc.6+it.1.
- **Site and kit.** Where they present why Eiraman exists, they may echo the new reason, in their own releases.
- **Version.** Descriptive change to a pre-release of 1.0.0, not in force: released as the next candidate, rc.6.

## Alternatives

- **Do nothing.** The theory keeps giving one reason only, and the reader meets security first as a set of rules in §14.
- **A paragraph of its own in §2**, with its own label. Not chosen: the Human Manager asked for the change in "Why Eiraman exists", and a new label would add a coverage row for one idea.
- **A rule in §2 with a key word**, for example that the Human Manager MUST know the implications of delegating. Not chosen: §2 has been theory since rc.1, and the rules that make the implications known are already in §12 and §14.
- **A new context principle in §3.** Not chosen: the mechanism exists; what was missing is the reason.
- **"Binding" in organisations without qualification**, as the request reads. Not chosen: in the Guide the Human Manager may choose the informative mode unless the organisation imposes the blocking one; "blocking by default" says the same thing without contradicting §14.
- **Change the item *Scope and risk management* too.** Not needed: it already matches.

## Acceptance evidence

- `tools/release_diff.py` from `v1.0.0-rc.5` to the candidate: in `EIRAMAN-GUIDE.md` the only changed lines are the version label and the paragraph Why Eiraman exists, whose old text is kept whole as the start of the new one; RFC 2119 counts unchanged; no heading removed or renamed.
- `TRACEABILITY.md`: all earlier rows kept; one row marked "RFC 0006".
- Independent review of the diff against the changelog and CR-031.
- The Author's approval of the final text at the publication Do.

## Open questions

- **Wording.** The direction is decided (D-031); the Author approves the final text at the publication Do.
- **Comment period.** Fourteen days from opening, for a Guide RFC that does not relax level requirements. An earlier decision is a deviation to record, as for the earlier RFCs.

## Decision

**Accepted**, on 2026-11-27, by the Author (D-031): approved direction; final text approval at the publication Do.

Written reasons: vibe coding increases the data people handle, often beyond what they can judge, and the method already makes the implications of delegating known through the classification modes, the adoption levels, the Applicability gate and the Security Report; the reason the Guide gives for existing should say so. The change is descriptive and adds no rule. The written reasons were drafted by the AI Coordinator from the Author's recorded request and are confirmed by the Author with the final text, at the publication Do.

**Deviation from the comment period.** The decision was taken before the end of the comment period (2026-12-11), which `rfcs/README.md` sets at fourteen days. The deviation is recorded here and in the changelog; it does not change the process for later RFCs.

**Implementation.** Applied in candidate 1.0.0-rc.6 of the Guide.
