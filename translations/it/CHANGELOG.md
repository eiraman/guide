<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# Changelog of the Italian translation

All notable changes to the Italian translation of the Eiraman Guide,
[EIRAMAN-GUIDE.it.md](EIRAMAN-GUIDE.it.md), and to its glossary, [GLOSSARY.it.md](GLOSSARY.it.md), are
documented in this file. The format is based on [Keep a Changelog 1.1](https://keepachangelog.com/en/1.1.0/).
The English Guide, [EIRAMAN-GUIDE.md](../../EIRAMAN-GUIDE.md), is canonical and prevails in case of
difference; its changes are in the repository [CHANGELOG.md](../../CHANGELOG.md).

**Version scheme.** The version of the translation is the version of the English Guide it translates,
followed by the build metadata `+it.N`, where `N` is the revision of the translation of that source version,
numbered from 1: `1.0.0-rc.6+it.1`. In [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0.html) build
metadata does not change precedence, so the translation never ranks above or below its source; the order of the revisions `+it.N` is set by `N` by
convention, not by SemVer precedence. A fix to the
translation of the same source increments `N`; a translation of a new Guide version starts again at `+it.1`.
The version source is the "Nota alla traduzione" at the top of `EIRAMAN-GUIDE.it.md`. The glossary and the notes on the
source are part of the translation and share its version. The translation is not tagged on its own: it is released with a tag of
the `guide` repository.

## [Unreleased]

**Pending update to 1.0.0-rc.7+it.1.** The English Guide 1.0.0-rc.7 adds
[RFC 0008](../../rfcs/0008-ai-manager-proportionate-discovery.md) (CR-035 to CR-041) to the text of RFC 0007
that this translation already renders (commit `59402b6`). The Italian text is left unchanged; a translator
must translate, keeping the key words and their counts section by section (RFC 0008, Impact):
- §1, «Planning and many models» (the AI Manager among the roles);
- §2, «Management applied to AI» (*Delegation*, *Design Thinking*, *Quality control*), the fourth difference
  between people and machines (human language), and the new paragraph «The laws of the AI Manager»;
- §3, «Human as a Manager acts up front» (last sentence);
- §4, «Human Manager» (first two items), «AI Manager» in place of «Interpreter», the new paragraphs «Approvals in
  the Human Manager's stead» and «Derogations of the AI Manager», «AI Coordinator» (opening and three new
  items), «Process reviewer», «Internal accountability»;
- §5, the new paragraph «Do through the AI Manager»;
- §6, the new paragraph «Outcome of review»;
- §7, «Role tiers» (Top), the SD table (SD4), «Agent blinding», the new paragraph «Omniscience», «Retrospective»,
  «Tolerance»;
- §7.1, «Promotion and reduction», «Raising the level of a role»;
- §8, «Phases and decisions» (opening, Proof of concept, Design and planning), the new paragraph «Iterations»,
  «Discovery group», «Question round» (through the AI Manager), «Convergence», the new paragraphs «Complete
  design» and «A real proof of concept», «Governance cycle» (governance share);
- §8.1, «Discovery procedure» (Iterate, Review, Judge), «Proof of concept and MVP»;
- §9, «Product Backlog», «Definition of done», «Dissent or missing proof», the new paragraph «Closure by
  derogation», «Manager View»;
- §12, «Three layers of documentation» (Strategic), «Messages between agents», «Writing rules» (opening);
- §13, «Minimum content» (the sentence on the AI Manager);
- §14, «Dialogue with the Human Manager» (AI Manager in place of Interpreter);
- the «Nota alla traduzione» (source commit and status) and the glossary: AI Manager, omniscience, derogation,
  closure by derogation, open choice, iteration, the three outcomes of the judge.

- §14, «Dialogo con il Manager umano»: traduzione del passaggio all'Interprete.

- §4, Revisore AI: traduzione della nuova regola di avvio, a eventi e a campione.

- §4, Interprete: traduzione della riga sui rapporti del Revisore AI e del Security Officer passati senza modifiche (decisione 4 della review dei profili, CR-033).

### Changed

- 2026-11-27: translation of the changes of CR-033 (RFC 0007) to the English Guide, proposed version 1.0.0-rc.7: Interpreter, pyramid of roles, review by samples, promotion rules, cost of errors, agent dialect. The translation becomes `1.0.0-rc.7+it.1`; new terms added to the glossary. Local candidate on the branch `cr-033-guida`, not published, not tagged.
- 2026-11-27: records the Author's native-speaker review of the curated translation `1.0.0-rc.6+it.1`; the
  "Not verified" point is closed under D-IT-1. The text is not changed: the version stays `1.0.0-rc.6+it.1` and
  nothing is tagged. The entry `[1.0.0-rc.6+it.1]` below is a released entry and is kept as published (CR-032, follow-up of the release Do-S35). The English text stays canonical and prevails in case
  of difference.

## [1.0.0-rc.6+it.1] - 2026-11-27

Translation of The Eiraman Guide 1.0.0-rc.6 (commit `d39ce03`, not tagged), which implements
[RFC 0006](../../rfcs/0006-security-measurement-self-feeding.md), from change request CR-031 and the Human
Manager's decisions D-031 and D-031-B. It starts from `1.0.0-rc.5+it.1`, whose text is kept whole: only the
texts that the source adds or changes are translated. Local candidate: not tagged, not pushed.

### Added

- **§2, "Perché esiste Eiraman"**: the three sentences that the source adds at the end of the paragraph, on the
  data people handle, the managerial role extended to security and the two defaults of the classification.
- **§2, "Il metodo si applica a sé stesso"**: the new descriptive paragraph.
- **§15, "Misurare il metodo"**: the new normative paragraph, with the key words of the source one for one. In
  §15 the translation now carries 28 DEVE/DEVONO (was 12), 4 NON DEVE/NON DEVONO (was 2), 1 NON DOVREBBERO
  (was 0), 3 PUÒ/POSSONO (was 2) and no DOVREBBE, as the source; in the whole text 366, 68, 7 DOVREBBE, 3 NON
  DOVREBBE and 38.
- `GLOSSARY.it.md`, new section 9 "Misura del metodo": banco di prova (test bench), collaudo al banco (bench
  testing), collaudatori (testers), Fault, campagna di misura, baseline (kept in English), Manager umano
  simulato, brief, «non misurata», «non dimostrato», indicatore primario, costo di riallineamento, applicazioni
  di prova and the other terms of the new texts; three notes on the choices (Collaudo, Baseline, Fault). The
  section "Note sulle scelte" keeps its text and becomes section 10.
- `SOURCE-NOTES.md`: points 19 to 25, on the texts added by 1.0.0-rc.6.

### Changed

- Title block: version label 1.0.0-rc.6; Status with «non misurata (§15, Misurare il metodo)».
- "Nota alla traduzione": source version 1.0.0-rc.6, commit `d39ce03`; version of the translation
  `1.0.0-rc.6+it.1`. The mention of the tag is dropped, because the source is not tagged.
- `SOURCE-NOTES.md`: the source version in the heading and in point 18.
- This changelog: the note "Pending update", written with the source, is replaced by this entry.

**Review.** An independent AI review of the candidate (commit `e2355f5`) gave PASS with one minor correction
and two refinements, applied in this version: «sé stesso» with the accent in §2 (was «se stesso»), «non pone
alcun obbligo a carico di chi adotta» in §15, and point 25 of `SOURCE-NOTES.md`. **Not verified.** No
native-speaker review by a second person has taken place; the translation was prepared with AI assistance (see the commit trailers).

## [1.0.0-rc.5+it.1] - 2026-11-27

First Italian translation, of The Eiraman Guide 1.0.0-rc.5 (commit `2635a69`, tag `v1.0.0-rc.5`). Local
candidate: not tagged, not pushed. From change request CR-029 and the Human Manager's decision D-IT-1: the
Italian text is the curated translation foreseen by the principle that English is canonical and Italian a
curated translation, and is taken as valid without a further approval of the text.

### Added

- `EIRAMAN-GUIDE.it.md`: complete translation of the Guide, sections 0 to 16, with the same section numbers,
  paragraphs, lists, tables and cross-references as the source, line for line. A "Nota alla traduzione" at the
  top names the source version and commit, states that the English text is canonical and prevails, and gives
  the mapping of the normative key words: MUST = DEVE (DEVONO), MUST NOT = NON DEVE (NON DEVONO), SHOULD =
  DOVREBBE (DOVREBBERO), SHOULD NOT = NON DOVREBBE (NON DOVREBBERO), MAY = PUÒ (POSSONO), always in capitals.
  The translation carries 350 DEVE/DEVONO, 66 NON DEVE/NON DEVONO, 7 DOVREBBE/DOVREBBERO, 2 NON DOVREBBE and
  37 PUÒ/POSSONO, the same counts as the source key words, section by section.
- `GLOSSARY.it.md`: English–Italian glossary of the terms used, with the source of each Italian term
  (specification 0.3, Role Profiles, website, or new for this translation).
- `SOURCE-NOTES.md`: the points of the English source found ambiguous or odd while translating, each with
  its section, a short quotation and how it is rendered. They are translated faithfully and not corrected;
  correcting the source needs an RFC.

### Changed

Corrections of the independent AI review of the first candidate (commit `f2ba990`), applied before this version
was fixed (commit `4b4a4cc`) and listed here as part of its history:

- §3: «NON DEVE sostituirsi ai ruoli AI» (was «sostituire i ruoli AI»; the one blocking finding).
- §0: «sono scritte interamente in maiuscolo»; «PUÒ restituire una proposta» here and in the notes of §7.1,
  §9.1 and §14 and in §15 (was «rinviare»).
- §1: «i log» for *logs*, twice (was «i registri»).
- §7: «figure con un profilo professionale umano» (was «personas»); «DEVE delimitarne il comportamento».
- §8: «template qualificabili», «template qualificato» for the Business Analyst and the User Personas (was
  «modelli»); «Le risposte alle domande non chieste»; «nuovi input» (was «spunti»).
- §8.1: «che richiedono un Do»; «la capacità di calcolo»; «dei fornitori» (was «dei vendor»).
- §10: «i test di regressione». §11: «orientano questa sezione»; «Classi di dati per fornitore» (was
  «provider»).
- §12 and §14.1: *layer* is «strato» (was «livello»); §14.1: «l'insieme minimo» (was «il set minimo»).
- §14: «alle domande che il Manager umano pone in base a Dialogo con il Manager umano».
- "Nota alla traduzione": the translation is curated and approved by the Author (decision D-IT-1); the key
  words «rendono le parole chiave inglesi con lo stesso significato».
- Glossary rows and notes aligned with these choices; `SOURCE-NOTES.md` added with 18 points; in the version
  scheme, the sentence on the order of the revisions `+it.N`.

**Review.** An independent AI review of the candidate against the source gave PASS with corrections; all of
them are applied in this version. **Not verified.** No native-speaker review by a second person has taken
place; the translation was prepared with AI assistance (see the commit trailers).
