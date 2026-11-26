<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# Eiraman RFCs

Status: **draft**.

An RFC (Request for Comments) is the way to propose a one-way door: a change that is irreversible or costly to reverse. GOVERNANCE §6.2 lists what needs an RFC; in doubt, write one.

## Process

1. **Draft.** Copy [0000-template.md](0000-template.md) to `rfcs/0000-short-title.md` and open a pull request. Declare AI assistance and conflicts of interest as in `CONTRIBUTING.md`, in the project's `.github` repository.
2. **Number.** A maintainer assigns the next number and the owning body (Author, working group or Steering Committee).
3. **Comment period.** At least 14 days; 30 days for governance, licences, trademark and relaxation of level requirements (**proposal**). The author answers every substantive comment.
4. **Final comment.** The owner announces the intended decision; 7 more days for last objections.
5. **Decision.** The owner records *accepted*, *rejected* or *postponed* with **written reasons** in the RFC. Silence is never acceptance: an RFC without decision 30 days after the comment period is listed as *pending decision* in the quarterly report.
6. **Implementation.** Accepted RFCs are implemented by ordinary pull requests that reference them. The RFC is *implemented* when the change is in a signed release.

A rejected Guide RFC may be resubmitted with new evidence after 6 months.

## States

`draft` → `in comment` → `final comment` → `accepted` | `rejected` | `postponed` → `implemented` | `withdrawn`

## Index

| # | Title | Owner | State |
|---|---|---|---|
| [0001](0001-context-blinding-discovery.md) | Context Consistency and Independence, agent blinding, AI Reviewer and Discovery as Design Thinking AI | Author (Guide) | accepted |
| [0002](0002-governo-family.md) | Regularise the Role Profile family `governo/` and its working group | Steward (governance; also the Author in Stage 1) | accepted (alternative B) |
| [0003](0003-critical-review-corrections.md) | Corrections from the critical review of specification 0.3 | Author (Guide) | accepted |
