<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# RFC 0007: Digital Seniority as a pyramid, review by samples and the agent dialect

- **Author(s):** the Author, by request; text drafted by the AI Coordinator of change request CR-033
- **Accountable human:** Paolo Ungari (Author)
- **AI-Use:** substantial (CONTRIBUTING.md §3)
- **Assisted-by:** Claude Opus 5.5 (Claude Code)
- **Conflicts of interest:** none
- **Owner of the decision:** Author (Guide); for §7.1, a community-maintained section, the DevSecOps & Tooling and FinOps working groups, which are not yet formed (see Decision)
- **Affected artifacts:** Guide §2, §4 (AI Coordinator, AI Reviewer), §6, §7, §7.1, §12, §14 (Dialogue with the Human Manager); `TRACEABILITY.md`. In separate releases: the Role Profiles (every catalogue, the map `_seniority/`, the dialect `_dialetto/`), the Tools, the Extended Framework (Guidance) and the Italian translation
- **State:** accepted
- **Dates:** opened 2026-11-27 · comment period ends 2026-12-27 · accepted 2026-11-27, before the end of the comment period (deviation, see Decision)
- **Change request:** CR-033 of the project "Eiraman Open Framework"; decided by D11–D23 and by the principles PR-11 and PR-12
- **Replaced in part by:** [RFC 0008](0008-ai-manager-proportionate-discovery.md). The role that this RFC first proposed, the Interpreter, never entered a released Guide: RFC 0008 replaces it with the AI Manager, and it moves to the AI Manager the choices on promotion and on the level of a role that this RFC gave to the AI Coordinator. Both RFCs are applied in candidate 1.0.0-rc.7.

## Summary

This RFC reorganises the work of agents as a pyramid. The base does almost all the work on small engines with low reasoning; review is one level up and mostly by samples, with an oracle first; promotion is a rare exception decided from the recorded cause of each failure. Agents write to each other in a dialect of the profile registry, Eiraman Wire; people read only human language. Two new differences between people and machines ground the change: agents' time is not people's time, and communication between agents is not human communication. The Human Manager approved these decisions in CR-033 (D11–D23, PR-11 and PR-12, 27 November 2026).

## Motivation

**What the Human Manager asked.** The requests are quoted verbatim, in Italian, with an English translation.

- «Lascia in una sessione critica una revisione della seniority dei Role profile. Vista la complessità organizzativa userei molti più Haiku e Sonnet rispetto ad oggi. Anche i tempi di ragionamento molto alti rallentano molto il processo. Essendoci i cicli di revisione tenderei a tenerli bassi».
  *"Leave a critical review of the seniority of the Role Profiles to a session. Given the organisational complexity I would use many more Haiku and Sonnet than today. Very long reasoning also slows the process down a lot. Since there are review cycles, I would keep it low."*
- «Deve essere valido il principio con cui operano le organizzazioni della piramide. La maggior parte del lavoro deve essere fatta dalla base e si deve andare a ridurre l'effort salendo. Haiku deve essere molto più usato. Cambiamo la regola dell'assegnazione statica del task».
  *"The principle by which pyramid organisations work must hold. Most of the work must be done by the base, and effort must decrease going up. Haiku must be used much more. Let us change the rule of static task assignment."*
- «Rispetto a quanto da te detto terrei la regola che chi fa il lavoro è sempre un livelli più basso di chi lo rivede. Assumendo che le Work Unit di revisione siano minori rispetto a quelle di esecuzione».
  *"Compared with what you said, I would keep the rule that whoever does the work is always one level below whoever reviews it, assuming that the Work Units of review are smaller than those of execution."*
- «Stiamo dando per scontato che la soluzione sia aumentare il modello e non il livello di ragionamento. Approfondiamo questo punto».
  *"We are taking for granted that the solution is a bigger model and not more reasoning. Let us look into this."*
- New principles, in the Human Manager's words: «il tempo è dalla mia parte» (*"time is on my side"*) and «la comunicazione multiagente è diversa dalla comunicazione umana» (*"multi-agent communication is different from human communication"*).
- «Approvo tutti i tuoi suggerimenti» (*"I approve all your suggestions"*), on the critical evaluation that fixed D11–D23; then «Aggiorna anche la guida ed il sito con i nuovi modelli e metodi. Proviamo subito Eiraman Wire» (*"Update the Guide and the site too with the new models and methods. Let us try Eiraman Wire straight away"*).

The model names in the requests stay in this RFC as quotations; the Guide names no provider or model (PR-6), and the levels map of the profile registry holds them.

**Evidence.**
- **Distribution.** In registry 0.11.1, 32% of the 447 catalogued tasks were at SD4 and 62% ran with high reasoning. Under «Team participation», 48 of 49 profiles joined the team at SD4: almost every agent ran at the highest level.
- **Cost of review.** Reading the full output of a small engine with a larger one costs about four times the execution. A review that is not marginal against execution defeats the pyramid.
- **Where tokens go.** In the pilots of 27 November 2026, re-reading the accumulated context accounted for about 95% of the tokens.
- **The dialect.** A first test of the dialect (Wire 0.1, 24 questions with known answers, a small engine with low reasoning) saved 8.6% of tokens and understood 23 of 24 messages against 24 of 24 for the originals. The error was a prohibition written as a symbol and read as its opposite. Hence the safety rule: obligations and prohibitions are written in words.
- **Sources.** Pyramid and leverage: Maister, *Managing the Professional Service Firm*, 1993. Acceptance sampling with switching rules: ISO 2859-1. Repeated sampling with a verifier: Brown et al., *Large Language Monkeys*, 2024. Test-time compute against model size: Snell et al., 2024. Model cascades: FrugalGPT, 2023; AutoMix, 2024. Pruning of redundant messages between agents: AgentPrune, 2025. Symbolic communication between agents: Pei et al., ICML 2026.

## Proposal

The text is in `EIRAMAN-GUIDE.md` 1.0.0-rc.7. In short:

1. **§2.** «Organisation and seniority» is staffed as a pyramid; *acceptance sampling* joins the management practices. Two differences join the existing two: agents' time is not people's time (PR-11); communication between agents is not human communication (PR-12), so agents write to each other in the dialect of the registry and anything a person reads is in human language.
2. **§4.** The AI Coordinator runs at the base, carrying out a procedure that the Tools compute. The AI Reviewer is started before the phase it watches and runs at events and on samples, no longer «in parallel» in continuous monitoring (decision 4 of the review of the profiles, 27 November 2026): an obligation is narrowed so that review stays small against execution.
3. **§6.** The verifier works one SD level above the executor; the highest level in use is verified by the Human Manager or by another provider. «Review by samples»: an oracle runs first; review on a different model always covers the risk class and covers a sample of the rest, under switching rules; the cost of review is recorded on its own.
4. **§7.** Role tiers restated as a pyramid; reviewers one level above; the SD table restated by role; Unit Cost includes review.
5. **§7.1.** The catalogue states the level of the role and, per task, the type, the oracle and the risk class; the map defines a ladder of reasoning steps and engine steps, local engines included; fallback is the level of the role; team participation is per run; promotion is a rare exception decided from the recorded cause (input, environment, refusal, depth, capability or knowledge), in the order: fix the cause, more reasoning, repeats up to the economic break-even, a more capable engine, capped by the mandate; the cost of errors is measured in tokens.
6. **§12.** «Messages between agents»: fixed fields, terse English, a closed list of symbols, a format check before delivery; never in anything a person reads.

**Replaced by RFC 0008 before release.** The Interpreter (§4, §7, §12, §14) becomes the AI Manager; the choices on promotion, on lowering a task and on raising the level of a role, which this RFC gave to the AI Coordinator, become open choices that the AI Manager decides (CR-036, D26). RFC 0008 also adds to §12 that a symbol enters the list only after a measurement and that obligations and prohibitions are written in words, which this RFC's Motivation already argued.

**Not changed:** K1–K9; the neutrality of the Guide on providers and models (PR-6); E5 for the commitments made to people; §15.

**Removed from the earlier draft at the Human Manager's decision:** the indicator of the cost of errors in time and the Do for raises driven by time (D17).

## Reversibility

This is a one-way door for adopters: the catalogue schema changes in every Role Profile and running projects would re-plan. While the Guide is a release candidate, rolling back costs a new candidate built from 1.0.0-rc.6, with registry 0.11.1; both are tagged.

## Impact

- **Normative.** RFC 2119 key words in `EIRAMAN-GUIDE.md`, from 1.0.0-rc.6 to the text of this RFC (commit `59402b6`, before RFC 0008), per section: §2 MUST 0 → 2; §4 MUST NOT 1 → 3, MUST 24 → 29 (of which MUST NOT 2 and MUST 4 in the Interpreter, replaced by RFC 0008); §6 MUST 19 → 24, MAY 0 → 1; §7.1 MUST NOT 0 → 2, MUST 10 → 18, MAY 3 → 4; §12 MUST NOT 1 → 2, MUST 24 → 26; §14 unchanged in count. Totals: MUST 366 → 388, MUST NOT 68 → 73, SHOULD 7 → 7, SHOULD NOT 3 → 3, MAY 38 → 40. The counts of the released candidate, with RFC 0008, are in RFC 0008.
- **Adopters.** Most roles, the AI Coordinator included, move to the base level; the mandate gains the threshold of the cost of errors in tokens, the cap on promotions and the sampling rates (Guidance gives 50% over three runs, 5% of runs per cycle and the ISO 2859-1 plans).
- **Role Profiles.** Every catalogue is reclassified by role, type, oracle and risk class; the levels map and the local engines are revised; the dialect specification enters the registry (`_dialetto/`).
- **Tools.** The validator of the new catalogue and of the dialect, an assignment tool and token counting.
- **Translations.** The Italian translation of this RFC's text exists (`1.0.0-rc.7+it.1` draft); the changes of RFC 0008 are pending (translations/it).

## Alternatives

- **Static catalogue with lowered levels.** The first CR-033 proposal: it kept most agents high through team participation.
- **A pyramid with a middle-model AI Coordinator and review always on a different model.** The third proposal: review cost dominates.
- **A dialect of truncated words and symbols.** Rejected after the first test: truncation does not reduce tokens, and a prohibition was read as its opposite.
- **Doing nothing.** Leaves the cost of almost every run at the highest level.

## Acceptance evidence

- `tools/release_diff.py` from `v1.0.0-rc.6` to the candidate: every changed line maps to this RFC, to RFC 0008 or to the changelog.
- `TRACEABILITY.md`: all earlier rows kept; rows marked "RFC 0007" for each new or changed paragraph.
- No provider or model named in the Guide.
- Registry candidate (CR-033): `valida_profilo.py` 52/52; tools tests OK on the candidate registry and on 0.11.0; independent review of the registry candidate with no blocking finding.
- Pilots A1 1 to 3 of 27 November 2026 ran the dialect between two sessions; they are pilots, not measurements.
- **Not available:** a bench campaign (§15). The candidate declares itself "not measured". The campaign is pre-registered in the framework candidate: arm A is 1.0.0-rc.6 with registry 0.11.1, arm D this RFC with RFC 0008; primary indicator the cost to the right application, Guide indicator the external failure.
- Independent review of the diff against this RFC, RFC 0008, the changelog and D11–D23.

## Open questions

1. The exact ISO 2859-1 switching thresholds in the edition in force, before they enter Guidance.
2. The sources marked as not verified in the CR-033 notes, before they enter Guidance.
3. For the User Personas, a local engine is an SD1 configuration for an SD3 role: to be settled in qualification.

## Decision

**Accepted**, on 2026-11-27, by the Author: decisions D11–D23 and principles PR-11 and PR-12 (CR-033, «Approvo tutti i tuoi suggerimenti»), and the request to update the Guide (CR-033, «Aggiorna anche la guida ed il sito»); the publication of a release candidate with all the change requests up to CR-040 was requested on 2026-11-28 (CR-041).

Written reasons: a project of agents is an organisation, and the pyramid is how organisations keep cost proportionate to the difficulty of the work; review must cost little against execution, so it is staffed one level up, with an oracle first and samples outside the risk class; promotion follows the diagnosis of the failure because more reasoning on the same engine is far cheaper than a larger engine; agents waste most tokens re-reading text written for people, so they write to each other in a measured dialect, and people keep human language. The written reasons were drafted by the AI Coordinator from the Author's recorded requests and are confirmed by the Author with the final text, at the publication Do.

**Replaced in part.** The Interpreter, and the AI Coordinator's choices on promotion and level, are replaced by RFC 0008, accepted on 2026-11-28 (CR-035 to CR-038, CR-041).

**Deviation from the comment period.** The decision was taken before the end of the thirty-day comment period (2026-12-27), as for RFC 0006. §7.1 is community-maintained and its working groups are not yet formed: the Author accepts the text without their proposal. Both deviations are recorded here and in the changelog; they do not change the process for later RFCs, and the founding contributors may reopen any point with a new RFC.

**Implementation.** Applied in candidate 1.0.0-rc.7 of the Guide, which is not measured.
