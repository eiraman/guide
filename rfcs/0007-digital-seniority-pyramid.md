<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# RFC 0007: Digital Seniority as a pyramid, the Interpreter and the agent dialect

- **Author(s):** the AI Coordinator of change request CR-033, for the Author
- **Accountable human:** the Author
- **AI-Use:** substantial (CONTRIBUTING.md §3)
- **Assisted-by:** Claude Opus 5.5 (Claude Code)
- **Conflicts of interest:** none
- **Owner of the decision:** Author (Guide), with the DevSecOps & Tooling and FinOps working groups for §7.1
- **Affected artifacts:** Guide §2, §4, §6, §7, §7.1, §12; Role Profiles (all catalogues and a new profile); levels map; tools
- **State:** draft (local candidate on branch `cr-033-guida`, not opened as a pull request; the number is to be confirmed by a maintainer)
- **Dates:** opened — · comment period ends —

## Summary

This RFC reorganises the work of agents as a pyramid. The base does almost all the work on small engines with low reasoning; review is one level up and mostly by samples; promotion is a rare exception decided from the cause of each failure. A new role, the Interpreter, is the only channel between the Human Manager and the agents. Agents write to each other in a dialect of the profile registry. Two new differences between people and machines ground the change: agents' time is not people's time, and communication between agents is not human communication. The Human Manager approved these decisions in CR-033 (decisions D11–D23, principles PR-11 and PR-12, 27 November 2026).

## Motivation

- **Distribution today.** In registry 0.11.1, 32% of the 447 catalogued tasks are at SD4 and 62% run with high reasoning. Under «Team participation», 48 of 49 profiles joined the team at SD4.
- **Cost of review.** Reading the full output of a small engine with a larger one costs about four times the execution. A review that is not marginal against execution defeats the pyramid.
- **Where tokens go.** In four pilot runs of 27 November 2026, re-reading the accumulated context accounted for about 95% of the tokens. Long texts are written once and re-read at every later turn.
- **Sources.**
  - Pyramid and leverage: Maister, *Managing the Professional Service Firm*, 1993.
  - Acceptance sampling with switching rules: ISO 2859-1.
  - Repeated sampling with a verifier: Brown et al., *Large Language Monkeys*, 2024.
  - Test-time compute against model size: Snell et al., 2024.
  - Model cascades: FrugalGPT, 2023; AutoMix, 2024.
  - Pruning of redundant messages between agents: AgentPrune, 2025.
  - Symbolic communication between agents: Pei et al., ICML 2026.
- **Evidence.** There is none from the bench yet (§15): this RFC is a hypothesis with a stated measurement.

## Proposal

The proposed text is in the diff of `EIRAMAN-GUIDE.md` on the branch. In short:

1. **§2.** «Organisation and seniority» is staffed as a pyramid. *Acceptance sampling* joins the management practices. Two differences are added to the existing two: agents' time is not people's time; communication between agents is not human communication.
2. **§4.** The Interpreter is the only channel to the Human Manager: it converts, quotes verbatim, does not decide, and reviews the work one level below it. The reports of the AI Reviewer and of the Security Officer reach the Human Manager unchanged; the Interpreter checks only their form, so that the channel does not filter its own controls. The AI Coordinator runs at the base, carrying out a procedure that the Tools compute.
   The AI Reviewer is started by the AI Coordinator before the phase it watches and runs at events and on samples, no longer «in parallel» in continuous monitoring: review cost stays small against execution (decision 4 of the review of the profiles, 27/11).
3. **§6.**
   - The verifier works one SD level above the executor; the highest level in use is verified by the Human Manager or by another provider.
   - Review by samples: an oracle runs first; review on a different model always covers the risk class and covers a sample of the rest, under switching rules.
   - The cost of review is recorded on its own.
4. **§7.**
   - Role tiers: the Interpreter at the top; Discovery roles that interpret needs; planning and design; the base, which includes the AI Coordinator.
   - Reviewers sit one level above.
   - The SD table is restated by role.
   - Unit Cost includes review.
5. **§7.1.**
   - The catalogue states the level of the role and, per task, the type, the oracle and the risk class.
   - The map defines a ladder of reasoning steps and engine steps, local engines included.
   - Fallback is the level of the role.
   - Team participation is per run.
   - Promotion is a rare exception, decided from the recorded cause (input, environment, refusal, depth, capability or knowledge). Its order is: fix the cause, then more reasoning, then repeats up to the economic break-even, then a more capable engine. It is capped by the mandate.
   - Cost of errors in tokens.
   - The AI Coordinator MAY raise the level of a role beyond the mandate threshold, with notice in the Manager View.
6. **§12.** Messages between agents use the dialect, with fixed fields, terse English, a closed list of symbols and a format check before delivery. The dialect is never used in anything a person reads. Documents reach the Human Manager through the Interpreter.

Not changed:
- K1–K9;
- the neutrality of the Guide on providers and models (PR-6): model names stay in the registry map;
- E5 for the commitments made to people;
- §15.

Removed from the earlier draft at the Human Manager's decision:
- the indicator of the cost of errors in time;
- the Do for raises driven by time.

## Reversibility

This is a one-way door for adopters: the catalogue schema changes in every Role Profile, a new mandatory role appears, and running projects would re-plan. To roll it back, restore 1.0.0-rc.6 and registry 0.11.1, both tagged.

## Impact

- **Adopters:**
  - a new role (the Interpreter) in every project;
  - the AI Coordinator and most roles move to the base level;
  - the mandate gains three values: the threshold of the cost of errors in tokens (suggested 50% over three runs), the cap on promotions (suggested 5% of runs per cycle) and the sampling rates.
- **Role Profiles:**
  - 49 catalogues are reclassified;
  - a new `governo/interprete` profile is added;
  - the AI Coordinator profile is rewritten for the base level and for the routing procedure;
  - the dialect specification is added to the registry.
- **Tools:** the validator of the new catalogue and of the dialect, an assignment tool, and token counting.
- **Translations:** Italian 1.0.0-rc.7+it.1, on the same branch.

## Alternatives

- **Static catalogue with lowered levels.** This was the first CR-033 proposal: it keeps most agents high through team participation.
- **Pyramid with a Sonnet-level AI Coordinator and review always on a different model.** This was the third proposal: review cost dominates.
- **A dialect of truncated words and symbols.** A first test of 24 questions, run on Haiku with low reasoning, found an 8.6% token saving and one prohibition read as its opposite. The dialect therefore writes obligations and prohibitions in words, and admits a symbol only after measurement.

## Acceptance evidence

- **Pre-registered bench campaign (§15).** Arm A is 1.0.0-rc.6 with registry 0.11.1. Arm D is this RFC. Same pilots and models, at least three repetitions, every run counted.
- **Primary indicator:** cost to the right application (R3).
- **Guide indicator:** external failure (defects found after closure, Faults).
- **Also reported:** tokens re-read per accepted increment, share of work by level, promotion rate, sampling outcomes, Human Manager attention.
- **Independent review** of the diff against this RFC and decisions D11–D23.

## Open questions

1. The registry names for «business analyst» and «application architect».
2. The exact ISO 2859-1 switching thresholds in the edition in force.
3. The name and version of the dialect (draft: «Eiraman Wire» 0.2).

## Decision

*Filled in by the owner.*
