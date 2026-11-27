<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# Notes on the source

Points of the English source, [EIRAMAN-GUIDE.md](../../EIRAMAN-GUIDE.md) 1.0.0-rc.6 (commit `d39ce03`), found
ambiguous or odd while preparing the Italian translation, [EIRAMAN-GUIDE.it.md](EIRAMAN-GUIDE.it.md). Each
point is translated faithfully and is not corrected: the English text is canonical, and a correction of the
source needs an RFC. These notes are part of the translation and share its version and its
[CHANGELOG](CHANGELOG.md). They are not normative.

| # | Section | Source text | Point | Italian rendering |
|---|---|---|---|---|
| 1 | §0 Purpose, Normative language; §15 Conformance | "what makes an application conformant"; "An application conforms" | "application" can mean a software application or an application of the method | «applicazione», which keeps both readings |
| 2 | §0 Normative language | "SHOULD NOT" | The key word is defined, but no rule of the Guide uses it: its two occurrences are in the definition | «NON DOVREBBE», in the definition only |
| 3 | §4 Human Manager | "MUST receive technical decisions translated into …" | The obligation is placed on the Human Manager, who receives, not on who delivers | «DEVE ricevere le decisioni tecniche tradotte in …» |
| 4 | §4 Liability towards third parties | "in the informative mode the owner exercises this responsibility through mandate and acceptance. The owner exercises this responsibility through mandate, class and acceptance" | Two nearly identical sentences, the special case before the general rule; the second does not say that it holds in the blocking mode | Both sentences kept, in the same order: «nella modalità informativa il titolare esercita questa responsabilità attraverso mandato e accettazione. Il titolare esercita questa responsabilità attraverso mandato, classe e accettazione» |
| 5 | §5 Deny | "unless a requirement of level 1 that the paragraph makes due is due and not met" | Convoluted: "due" twice, and "the paragraph" refers to a paragraph of §14.2 | «a meno che un requisito del livello 1 che quel paragrafo rende dovuto sia dovuto e non soddisfatto» |
| 6 | §5 Deny | "any data other than test data, masked data included" | "masked data included" can attach to the data blocked or to the test data | Read as data blocked, consistent with "only on test data": «ogni dato diverso dai dati di prova, compresi i dati mascherati» |
| 7 | §5 Rules against under-escalation | "E6 · Measurement", "E6 · Calibration" | Two rules carry the same identifier | «E6 · Misura», «E6 · Taratura» |
| 8 | §6 K8 | "Such cases MUST be flagged as high divergence" | "Such cases" refers to the cases of K7, across the list item | «Questi casi DEVONO essere segnalati come divergenza elevata» |
| 9 | §7 Digital Seniority | "SD level" | The abbreviation SD is never expanded in English; it comes from the Italian "Seniority Digitale" | «livello SD» |
| 10 | §8 Phases and decisions | "It becomes a Do only if the outcome is negative" | The subject of "It" is uncertain: the phase or its outcome | Subject left implicit: «Diventa un Do solo se l'esito è negativo» |
| 11 | §8 Question round | "The answers not asked MUST be taken as correct" | Elliptic: it means the supposed answers to the questions not sent to the Human Manager | «Le risposte alle domande non chieste DEVONO essere prese per corrette» |
| 12 | §8.1 | "Proof of concept and MVP"; "a mock-up (MOC)" | The title names the MVP, which the text does not treat; MOC is an unusual abbreviation | «Proof of concept e MVP»; «un mock-up (MOC)» |
| 13 | §12 Three layers; Evidence | "Verified by an AI reviewer"; "the AI reviewer MUST check the link" | Lower-case "AI reviewer" against the role "AI Reviewer" of §4: it is not stated whether it is the same role | «revisore AI» here, «Revisore AI» for the role of §4 |
| 14 | §14 Classification mode | "at the approval of the mandate included"; "otherwise a different mode MUST have a new project" | One very long paragraph; both phrases are elliptic | «nemmeno all'approvazione del mandato»; «altrimenti una modalità diversa DEVE avere un nuovo progetto» |
| 15 | §14.1 Level 1 · Evidence | "detection of a deliberately vulnerable test suite" | Literally the suite is detected, not the vulnerabilities placed in it (specification 0.3: "rilevazione di una suite di vulnerabilità inserite di proposito") | Literal: «rilevazione di una suite di prova deliberatamente vulnerabile» |
| 16 | §14.2 Running above the qualified level | "the exception below for the work on test data does not apply to it" | "it" can be the doubt or the case of a class in doubt; "below" points to the next sentence | «l'eccezione indicata sotto per il lavoro su dati di prova non si applica a questo caso» |
| 17 | §14.2 Running above the qualified level | "moving up follows Moving up" | Self-reference to the paragraph of the same name | «la salita segue Salita» |
| 18 | §16 Version history | "Version 1.0 supersedes the Italian specification 0.3" | The document is 1.0.0-rc.6, a release candidate not yet in force | «La versione 1.0 sostituisce la specifica italiana 0.3» |
| 19 | §2 Why Eiraman exists | "this knowledge is, by default, information"; "in work and organisational contexts it is blocking by default" | §14 names the modes "informative" and "blocking" and sets the blocking mode "in every other case", doubt included; here the wording is looser ("information", "work and organisational contexts") | «questa conoscenza è, per impostazione predefinita, informazione»; «nei contesti di lavoro e organizzativi è bloccante per impostazione predefinita» |
| 20 | §15 Measuring the method | "the Maintainers (§4) for the Extended Framework and, with them, the Role Profiles and Tools" | "them" has no clear antecedent (the Maintainers, or the Extended Framework, which is singular); "Maintainers" is capitalised here and not elsewhere | «i Manutentori (§4) per il Framework esteso e, con essi, i Role Profile e gli Strumenti» |
| 21 | §15 Measuring the method | "they MUST record as a fault, that is, any failure of the delivery to do what its instructions say or what was asked, everything that does not work" | The definition of fault is inserted between the verb and its object | Same order: «DEVONO registrare come Fault, cioè ogni caso in cui la consegna non fa ciò che le sue istruzioni dicono o ciò che è stato chiesto, tutto ciò che non funziona» |
| 22 | §15 Measuring the method | "whoever coordinates the work on the method MUST propose to the Human Manager" | The role is not among those of §4, and "the Human Manager" of the method is not defined in the Guide | «chi coordina il lavoro sul metodo DEVE proporre al Manager umano» |
| 23 | §15 Measuring the method | "for a class of project"; "the classes the bench represents" | "class" can be the project classes 0 to 2 of §14 or a kind of project | «per una classe di progetto»; «le classi che il banco rappresenta» |
| 24 | §15 Measuring the method | "An outcome of "not demonstrated" is enough for neither" | "neither" refers to the two consequences of the two sentences before it (reducing or removing a rule; stating the baseline for a class) | «Un esito «non dimostrato» non basta né per l'una né per l'altra cosa» |
