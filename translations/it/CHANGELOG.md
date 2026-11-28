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
numbered from 1: `1.0.0-rc.7+it.1`. In [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0.html) build
metadata does not change precedence, so the translation never ranks above or below its source; the order of the revisions `+it.N` is set by `N` by
convention, not by SemVer precedence. A fix to the
translation of the same source increments `N`; a translation of a new Guide version starts again at `+it.1`.
The version source is the "Nota alla traduzione" at the top of `EIRAMAN-GUIDE.it.md`. The glossary and the notes on the
source are part of the translation and share its version. The translation is not tagged on its own: it is released with a tag of
the `guide` repository.

## [Unreleased]

## [1.0.0-rc.7+it.1] - 2026-11-28

Translation of The Eiraman Guide 1.0.0-rc.7 (commit `47b3021`, not tagged), which implements
[RFC 0007](../../rfcs/0007-digital-seniority-pyramid.md) and
[RFC 0008](../../rfcs/0008-ai-manager-proportionate-discovery.md). It starts from `1.0.0-rc.6+it.1`, whose text
is kept wherever the source is unchanged. The translation was decided by the Human Manager (D-IT-1). Local
candidate: not tagged, not pushed.

Key words as in the source, section by section: in the whole text 414 DEVE/DEVONO, 75 NON DEVE/NON DEVONO, 7
DOVREBBE/DOVREBBERO, 3 NON DOVREBBE/NON DOVREBBERO and 38 PUÒ/POSSONO. The four laws of the AI Manager (§2) are
introduced by DEVE; the other sentences on the AI Manager are descriptive in the source and are rendered
without DEVE, NON DEVE or PUÒ.

### Added

- **§2**: the paragraph «Le leggi del Manager AI», with the four laws and how they work together.
- **§4**: the paragraphs «Approvazioni in vece del Manager umano» and «Deroghe del Manager AI»; three items of
  «Coordinatore AI» (state for the agents, open choices, derogations).
- **§5**: the paragraph «Do attraverso il Manager AI».
- **§7**: the paragraph «Onniscienza».
- **§8**: the paragraphs «Iterazioni», «Design completo» and «Un proof of concept reale».
- **§13**: the sentence on the Role Profile of the AI Manager.
- `GLOSSARY.it.md`: the terms of RFC 0008 (Manager AI, leggi, in vece del Manager umano, deroga, onniscienza,
  scelta aperta, stato del progetto per gli agenti, iterazione, the three outcomes of the judge, Design
  completo and the others), taken from the Role Profile of the AI Manager in the registry where it has them;
  two notes on the choices (Manager AI; Deroga e tralasciare).
- `SOURCE-NOTES.md`: points 26 to 39, on the texts of 1.0.0-rc.7; points 32 and 35 to 39 assessed against the decisions of CR-041
  (D-041-D, D-041-E, D-041-H) and marked resolved, with no change to the source or to the translation (WP-41A2).

### Changed

- **«Manager AI» in place of «Interprete»** everywhere: §4 (the paragraph is rewritten as in the source: the
  five rules of the Interpreter leave, the description of how the laws lead the AI Manager to act enters; the
  Tools attach the reports of the AI Reviewer and of the Security Officer), §7 (top of the pyramid, row SD4),
  §12 (writing rules), §14 (Dialogue with the Human Manager).
- **§1** «Pianificazione e più modelli»; **§2** *delega*, *Design Thinking* and the difference on communication
  (human language); **§3** «Human as a Manager agisce in anticipo».
- **§4** «Manager umano» (first two items), «Coordinatore AI» (opening), «Revisore di processo»,
  «Accountability interna». **§5** «Do» (opening) and «E4 · Classificatore».
- **§7** «Blinding degli agenti», «Retrospettiva», «Tolleranza». **§7.1** «Promozioni e riduzioni» (the first
  item of the list becomes part of the paragraph), «Alzare il livello di un ruolo».
- **§8** «Fasi e decisioni» (opening, Proof of concept, Design e planning), «Gruppo di Scoperta», «Giro di
  domande», «Convergenza». **§8.1** «Procedura di Scoperta» (Iterare, Revisione, Giudizio), «Proof of concept e
  MVP». **§9** «Product Backlog», «Vista del Manager». **§12** «Tre strati di documentazione» (Strategico),
  «Messaggi tra agenti».
- "Nota alla traduzione": source commit `47b3021`; the words on the proposed version and its branch leave.
- `SOURCE-NOTES.md`: the source version in the heading and in point 18.
- 2026-11-27, earlier step of this version: translation of the changes of RFC 0007 (CR-033) to the English
  Guide: pyramid of roles, review by samples, promotion rules, cost of errors, agent dialect, the AI Reviewer
  started before the phase it watches, at events and on samples. New terms added to the glossary. That step
  rendered the role then called Interpreter («Interprete»), which RFC 0008 replaces with the AI Manager.

### Removed

- The notice «Avviso: traduzione da aggiornare» at the top of `EIRAMAN-GUIDE.it.md`, and the note "Pending
  update to 1.0.0-rc.7+it.1" of this changelog with the three lines on the RFC 0007 step that followed it: the
  update they announced is this entry.
- The term «Interprete», from the text and from the glossary.

**Not verified.** No independent review of this version of the translation and no native-speaker review by a
second person have taken place; the translation was prepared with AI assistance (see the commit trailers).

**Record on the earlier version, kept from [Unreleased].**

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
