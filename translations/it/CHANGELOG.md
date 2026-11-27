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
numbered from 1: `1.0.0-rc.5+it.1`. In [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0.html) build
metadata does not change precedence, so the translation never ranks above or below its source; the order of the revisions `+it.N` is set by `N` by
convention, not by SemVer precedence. A fix to the
translation of the same source increments `N`; a translation of a new Guide version starts again at `+it.1`.
The version source is the "Nota alla traduzione" at the top of `EIRAMAN-GUIDE.it.md`. The glossary and the notes on the
source are part of the translation and share its version. The translation is not tagged on its own: it is released with a tag of
the `guide` repository.

## [Unreleased]

**Pending update.** The English Guide 1.0.0-rc.6 ([RFC 0006](../../rfcs/0006-security-measurement-self-feeding.md), CR-031)
adds three sentences at the end of the paragraph "Why Eiraman exists" (§2), a new paragraph "The method applies
to itself" (§2), a new normative paragraph "Measuring the method" (§15) and the words "not measured" in the
Status of the title block, and changes the version label. The translation still declares 1.0.0-rc.5 and must
be updated to `1.0.0-rc.6+it.1`: translate these texts, keeping the key words of §15 with the same counts
(in §15 MUST 12 → 28, MUST NOT 2 → 4, SHOULD NOT 0 → 1, MAY 2 → 3), and update the version label and the
"Nota alla traduzione".

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

**Review.** An independent AI review of the candidate against the source gave PASS with corrections; all of
them are applied in this version. **Not verified.** No native-speaker review by a second person has taken
place; the translation was prepared with AI assistance (see the commit trailers).
