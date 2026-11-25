<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

> **Historical, non-normative.** Superseded by The Eiraman Guide v1.0. Licensed CC BY-SA 4.0 for this repository; earlier distributed copies remain under CC BY-NC-ND 4.0.
>
> **Storico, non normativo.** Sostituito da The Eiraman Guide v1.0. Concesso in licenza CC BY-SA 4.0 per questo repository; le copie distribuite in precedenza restano sotto CC BY-NC-ND 4.0.
>
> Internal references were removed from this copy; the list is in [README.md](README.md). / Da questa copia sono stati tolti i riferimenti interni; l'elenco è in [README.md](README.md).

# Metodo Eiraman

Specifica 0.3 · 25 novembre 2026 · Sostituisce la 0.2.

**Convenzioni.**
- Le frasi con *deve* o *non può* sono **regole normative**: un'applicazione è conforme a Eiraman solo se le rispetta.
- Le frasi marcate **Indicazione** contengono valori o pratiche raccomandati, che il mandato di progetto può modificare.
- Le scelte di implementazione appartengono allo strumento e non a questa specifica.

## 1. Che cos'è Eiraman

Eiraman è un **metodo di Vibe Coding per organizzazioni**. L'umano non legge il codice: governa da manager, con mandato, principi e deleghe. Un sistema di agenti AI esegue, si verifica con meccanismi concorrenziali e gestisce le eccezioni operative. Ogni rilascio è ricostruibile da evidenze e costi.

**Perché esiste.** Gli approcci *human-in-the-loop*, in cui una persona approva o corregge ogni passo dell'AI, e *human-on-the-loop*, in cui una persona sorveglia l'esecuzione e interviene sulle eccezioni, come pure la revisione umana della qualità del codice, servono poco dove non esistono team di sviluppatori. Le definizioni seguono le Linee guida UE per un'AI affidabile (2019). Hanno due limiti:
- la proliferazione di controlli puntuali porta ad approvazioni simili all'accettazione delle condizioni d'uso di un software: nessuno li legge;
- relegano l'AI allo sviluppo applicativo, e non la mettono al servizio degli utenti di business.

Eiraman li supera con la pianificazione e con la modalità **multi-LLM**: nello stesso progetto più modelli collaborano in modo indipendente come Coordinatore AI, esecutori e revisori.

**Principio fondante.** Eiraman riparte dalle **metodologie di management tradizionale** e le applica all'AI. Gli agenti si governano come un manager governa un'organizzazione: obiettivi e mandato, deleghe, ruoli e squadre, pianificazione, gestione dei rischi, revisioni e retrospettive. Per questo l'umano è **Human as a Manager**. Ogni regola del metodo è la trasposizione di una pratica di management nota, adattata a ciò che cambia quando chi esegue è un agente e non una persona.

| Pratica di management | Trasposizione in Eiraman | Che cosa cambia con gli agenti | Dove |
|---|---|---|---|
| Mandato, obiettivi, Management by Objectives | Mandato del Manager umano, Visione, criteri di successo e criteri di arresto | Gli obiettivi diventano criteri eseguibili e misurati | §2, §5 |
| Delega e matrice delle responsabilità (RACI) | Escalation 3D Deny/Delegate/Do, RACI | La delega si decide sulla reversibilità e il silenzio non vale assenso | §2, §3 |
| Organigramma, staff planning, seniority | Piramide delle AI Squad, Role Profile, Unit Cost | I ruoli si istanziano su modelli diversi e si ricompongono a ogni retrospettiva | §4 bis, §9 |
| Scrum e Scrum of Scrums | Squadre per Work Package, Scrum Master AI, Coordinatore AI | Niente timebox umani: i limiti sono costo, contesto e quote | §4 bis, §5 |
| Design Thinking | Scoperta con divergenza e convergenza tra modelli | Servono guardrail perché gli agenti non hanno il giudizio di contesto di una persona | §5 |
| Architettura d'impresa (TOGAF) e Composable Architecture | Viste architetturali, Backbone/Brain/interfacce/Hairs | La priorità evita i patchwork che l'AI produrrebbe con facilità | §6 bis |
| Gestione di scope e rischi | Principi e Decisioni versionati, Risk Log, livelli di applicabilità | Il rischio si limita in partenza perché la competenza specialistica è nei profili e non nel singolo progetto | §5, §8, §10 |
| Qualità e controllo indipendente | Chiusura su evidenza, verificatori indipendenti, meccanismi concorrenziali | Gli agenti non si stancano: la concorrenza tra candidate è sostenibile, se il costo lo giustifica | §4, §6 |
| Reporting al management | Revisione del ciclo, prima le cattive notizie, completezza bloccante | Il riassunto di un agente può essere compiacente e va controllato sui registri | §5, §8 |

Il metodo ha tre componenti:

- **Framework.** Ruoli, deleghe, ciclo di lavoro, convenzioni architetturali, prove di completamento e livelli di applicabilità. Ogni progetto registra la versione del metodo che adotta.
- **Development Environment.** L'ambiente in cui il metodo viene eseguito. Ospita il Coordinatore AI, esecuzioni, registri e strumenti di verifica, e applica i Deny (§3, §7). Il Coordinatore AI lo configura e lo conduce per conto del responsabile business. Le chiamate a servizi esterni dipendono dalle deleghe del progetto. Sono locali lo stato, i registri, il repository e i segreti; escono soltanto i prompt e i dati diretti ai motori e ai connettori autorizzati dal mandato.
- **Projects.** Applicazioni il cui sviluppo mette alla prova il metodo e ne permette il perfezionamento. Un'applicazione può incorporare in parte il metodo (§11).

Lo strumento che mette in pratica il metodo ne è un'implementazione. Deve rispettare le regole normative e non può aggiungere regole proprie presentandole come Eiraman. Un'applicazione è conforme solo se rispetta tutte le regole normative; in caso contrario pubblica una dichiarazione di conformità parziale (§11).

### Principi di contesto

1. **La competenza specialistica sta nei Role Profile, non in ogni progetto.** Eiraman non sostituisce chi sviluppa: ne sposta la competenza nei Role Profile e nella loro qualificazione a livello di framework (§9), da dove guida gli agenti in molti progetti. Così la produzione si avvicina a chi ha il bisogno. L'operatore umano del progetto è un utente di business: decide su aspetti funzionali ed economici e non sostituisce i ruoli AI su tecnologia, applicazioni e sicurezza.
2. **Human as a Manager.** L'umano agisce **prima**, con strumenti di management: mandato, obiettivi, principi, deleghe, riserve, budget, criteri di successo. Si colloca soprattutto sul piano strategico e, per le sole decisioni di business, su quello tattico. Non supervisiona l'esecuzione. Eccezioni e autonomia operativa spettano al sistema di AI.
3. **Esclusioni.** Il metodo non si applica ai sistemi AI vietati o ad alto rischio secondo l'AI Act, né agli altri casi fuori perimetro del §10.

### Modello operativo

Eiraman porta in forma agentica i principali framework di riferimento, adattandoli alle differenze tra persone e macchine:

| Framework | Come lo usa Eiraman | Dove |
|---|---|---|
| Design Thinking e brainstorming | Divergenza tra più modelli, convergenza di un analista, il Manager umano interviene a gate fissi | §5 |
| Composable Architecture | Componenti per funzione, sviluppati in Work Package indipendenti e realizzati in ordine di priorità | §6 bis |
| TOGAF ADM | Viste business, funzionale (applicazioni), dati e infrastruttura (tecnologia) nel documento architetturale | §5, §6 bis |
| Scrum e Scrum of Scrums | AI Squad per Work Package con uno Scrum Master AI, coordinate dal Coordinatore AI | §4 bis |
| DevSecOps | Git leggibile, test automatici, sicurezza fin dalla progettazione | §6 |

Due differenze tra persone e macchine guidano gli adattamenti:
- **Le macchine non hanno i limiti dell'interazione umana.** Analizzano contenuti e apprendono framework molto più in fretta. I limiti di Scrum, come la dimensione del team o la durata dello Sprint, non dipendono più dalla capacità umana ma da quella dei sistemi: costo, finestra di contesto, quote dei fornitori.
- **Gli agenti non hanno il giudizio di contesto di una persona:** seguono le istruzioni alla lettera e non capiscono da soli quando stanno uscendo dallo scopo. Le attività aperte, come il brainstorming, richiedono confini e guardrail più stretti che con un team umano: ruoli e comportamenti definiti, numero di giri, criteri di convergenza, dati ammessi.

### Due risultati da accettare separatamente

L'accettazione del software e quella del deliverable che il software produce restano distinte. Esempio: in NUR un incremento software può introdurre un controllo editoriale. Per chiudere il pacchetto occorre dimostrare che il controllo funziona. Il documento prodotto da NUR passa invece attraverso la propria revisione editoriale. Un PDF rifiutato può essere la prova riuscita del controllo che ne ha impedito la consegna.

## 2. Responsabilità

**Manager umano.** È la persona di business che governa il progetto. Assume due ruoli: Product Owner e Business Architect.
- Descrive utenti e processo.
- Approva Visione, Principi, criteri di successo, mandato, spesa, classe del progetto e salita di livello.
- Decide i Do, approva il ciclo di governo successivo e accetta o rifiuta il risultato.
- Può autorizzare il collegamento di un account o di una cartella attraverso il consenso nativo della piattaforma.
- Riceve le decisioni tecniche solo tradotte in funzioni, costi, tempi e impatto su utenti e dati.

**Coordinatore AI.** Il suo Role Profile è descritto nel §9.
- Acquisisce il repository autorizzato, configura motori e strumenti entro i permessi, assegna credenziali entro i permessi concessi, verifica disponibilità e budget.
- Prepara le Wave, assegna i Work Package, valida risultati e conformità, aggiorna il piano e conduce le retrospettive.
- Gestisce avvio, diagnosi, sospensione, ripresa, rilascio entro mandato e ripristino.

**Ruoli AI specialistici.** Analista, architetti, Scrum Master AI, esecutori, tester e revisori AI operano con Role Profile qualificati e ne rispettano i limiti. Prendono le decisioni tecniche. Al tester sono accessibili requisiti, contratti, dati e risultati attesi. La sua prima valutazione avviene indipendentemente dalla discussione dell'esecutore.

**Revisore di processo.** È un agente indipendente, basato su un modello diverso da quello del Coordinatore AI. Campiona le Wave chiuse e verifica che le escalation dovute siano arrivate al Manager umano (§3, E6) e che le chiusure abbiano evidenze (§6).

**Manutentori.** Sono membri esperti dell'organizzazione che pubblica il metodo, esterni ai progetti. Qualificano Role Profile, modelli di documento e checklist del gate (§9).

### Chi risponde di che cosa

- **Accountability interna.** Ciascuno risponde di ciò che decide.
  - Il Manager umano risponde delle decisioni di sua competenza e dell'uso del metodo dentro il perimetro qualificato.
  - Il Coordinatore AI e i ruoli AI rispondono **in senso operativo**: ogni chiusura ha evidenze e ogni errore diventa un caso di retrospettiva. Questa responsabilità non è giuridica.
  - I manutentori rispondono della conformità dei profili alle fonti al momento della qualificazione, non dei singoli progetti.
- **Responsabilità verso terzi.** È del **titolare**: la persona al livello 0, l'organizzazione ai livelli 1 e 2.
  - Ai livelli 1 e 2 il Manager umano agisce con un mandato formale dell'organizzazione. Senza quel mandato il progetto resta al livello 0.
  - Il titolare esercita la responsabilità attraverso mandato, classe e accettazione. Dimostra la propria diligenza con le evidenze Eiraman (§8, pacchetto per terzi).

| Attività | Manager umano | Titolare | Coordinatore AI | Ruoli AI, compresi tester e revisori | Revisore di processo | Manutentori |
|---|---|---|---|---|---|---|
| Mandato, Principi, classe e livello | A/R | I; ai livelli 1–2 conferisce il mandato | C | R per la classe (gate di compliance) | — | — |
| Decisioni tecniche | I, in forma tradotta | — | A operativa | R | V | — |
| Chiusura tecnica del pacchetto | — | — | A operativa / R | R | V | — |
| Accettazione business | A/R | I | C | — | — | — |
| Rilascio verso utenti | A verso l'organizzazione | A verso terzi | R | C | V | — |
| Qualificazione dei profili | — | — | I | — | — | A/R |
| Incidenti e violazioni di dati | I; decide i Do | A; notifica ex art. 33 GDPR | R | R | V | — |

R = esegue · A = risponde · C = consultato · I = informato · V = verifica a posteriori, a campione.

## 3. Escalation 3D

**Deny.** L'ambiente, non l'agente, impedisce un'azione vietata dal mandato o fuori livello e ne registra il motivo. Il Coordinatore AI cerca un'alternativa autorizzata. Se non la trova, sospende il lavoro interessato.

**Delegate.** I ruoli AI decidono in autonomia le **porte a due vie**, cioè le decisioni reversibili a costo noto e dentro il budget: motore, tentativo, correzione, ripristino. Ogni scelta resta associata al pacchetto.

La distinzione tra decisioni di Tipo 1 (irreversibili, «porte a una via») e di Tipo 2 (reversibili, «porte a due vie») viene dalla lettera agli azionisti Amazon del 2015 di Jeff Bezos. Bezos mette in guardia soprattutto dal trattare con processo pesante le decisioni di Tipo 2: in Eiraman è la sovra-escalation. Il rischio opposto è la sotto-escalation. Entrambe sono misurate (E6).

**Do.** Salgono sempre al Manager umano:
- le porte a una via;
- le riserve del mandato: impatto su Visione, Principi o criteri di successo, dati personali, terze parti, nuovi fornitori, spesa oltre soglia;
- i cambi di Decisione;
- i nuovi accessi;
- i cambi di classe del progetto e la salita di livello. La discesa di livello è invece automatica (§10).

Nel dubbio sulla reversibilità, la decisione è una porta a una via. Il Do presenta, in termini funzionali ed economici:
- impatto;
- opzioni;
- raccomandazione;
- evidenze;
- scadenza;
- effetto della mancata risposta.

Un cambio di Decisione include la SWOT. Dopo la scelta, l'esecuzione torna al Coordinatore AI.

### Regole contro la sotto-escalation

| # | Regola |
|---|---|
| E1 | Il mandato elenca le **riserve** oltre alle deleghe. Al Manager umano sale l'impatto di business della riserva, tradotto in funzioni, costi, tempi e impatto su utenti e dati. La scelta tecnica resta ai ruoli AI. Le riserve prevalgono su K7. |
| E2 | La **reversibilità** è il criterio tra Delegate e Do. |
| E3 | Ogni scelta non banale è registrata come **micro-decisione**, con alternativa, reversibilità stimata, costo di ritorno e riserve considerate. |
| E4 | Se una decisione debba salire al Manager umano lo stabilisce un **classificatore** basato su un modello diverso da quello del Coordinatore AI. Se i due sono in disaccordo, la decisione sale. |
| E5 | Gli scostamenti dal piano, compresi i cambi di classe, si sommano in un **budget di deriva** cumulativo sul progetto, riportato per ciclo di governo. Oltre la soglia del mandato scatta una revisione del mandato. |
| E6 | Il revisore di processo misura la **sotto-escalation** (decisioni riservate non portate al Manager umano, sul totale delle decisioni riservate) e la **sovra-escalation** (Do che rientravano nelle deleghe, sul totale dei Do). Nel pilota NUR, e poi nel primo progetto di ogni nuova adozione, il Manager umano esamina una volta un campione di circa 20 decisioni autonome, per tarare il revisore. |

### Scadenze e urgenze

- **Il silenzio non approva mai un Do.**
  - Fino alla risposta, il pacchetto interessato resta sospeso e il lavoro indipendente prosegue.
  - Alla scadenza il Manager umano riceve un sollecito.
  - Alla seconda scadenza il pacchetto esce dalla Wave e la revisione del ciclo lo riporta come decisione mancante.
  - L'opzione irreversibile non viene mai eseguita senza risposta.
- **Contenimento urgente.** Il mandato elenca azioni di contenimento reversibili pre-autorizzate: ripristino, revoca di credenziali, disattivazione di una funzione, sospensione temporanea del servizio. Il Coordinatore AI le esegue subito e apre un Do urgente. Un'azione fuori elenco segue la regola ordinaria del Do.
- **Indicazione.** Do ordinario: 3 giorni lavorativi più altri 3. Do urgente: 4 ore.

## 4. Meccanismi concorrenziali

**Razionale.** Ai modelli AI si applicano i principi della teoria della cooperazione umana, spostandoli verso modelli più competitivi, perché tra agenti non c'è un'armonia del gruppo da preservare. I ruoli di controllore e di project manager sono affidati all'AI.

Il beneficio di un meccanismo concorrenziale nasce dal **generare più candidate e selezionare la migliore**, non da un maggiore impegno degli agenti. Dipende dalla diversità delle candidate e dall'affidabilità del selettore.

| # | Regola |
|---|---|
| K1 | Si apre un meccanismo concorrenziale solo con un selettore affidabile: test o criteri misurabili, oppure una rubrica fissata prima, valutata da un giudice di modello diverso dai concorrenti, con l'ordine delle candidate alternato. Tutte le candidate partono dallo stesso punto di partenza. |
| K2 | Per ogni meccanismo si registra il livello di diversità delle candidate: modello, fornitore o strategia. |
| K3 | Per default la candidata è una sola. Da 2 a 3 per i pacchetti generativi ad alta variabilità o con errore costoso, entro il tetto di spesa. |
| K4 | Dopo la selezione, le critiche emerse dalle candidate perdenti vengono applicate alla vincitrice, attraverso il revisore. |
| K5 | Una parte dei criteri di valutazione non viene mostrata alle candidate, e i giudici ruotano. |
| K6 | Si misurano margine di vittoria, accordo tra giudice e umano (tarato su un campione di giudizi umani sulle candidate) e costo per incremento accettato rispetto all'esecutore singolo. Se il meccanismo non batte l'esecutore singolo su un tipo di pacchetto, per quel tipo si torna a una sola candidata. |
| K7 | Con proposte molto divergenti su una porta a due vie si adotta l'opzione con il minor costo di ritorno. Prima, se il budget lo consente, si esegue una prova breve che discrimini tra le opzioni. |
| K8 | Questi casi sono marcati «divergenza elevata». Il revisore di processo li esamina tutti e li include con priorità nel campione di taratura (E6). |
| K9 | Se le divergenze si ripetono sullo stesso tema, il Coordinatore AI propone una revisione del mandato come Do, tradotta in funzioni, costi, tempi e impatto su utenti e dati. Se il tema non è traducibile in questi termini, resta ai ruoli AI con K7 e K8. |

Per ogni verifica si registra il livello di indipendenza ottenuto: contesto, modello, fornitore o persona. La classe di rischio del pacchetto fissa il livello minimo. **Indicazione:** per sicurezza e dati personali, almeno un modello diverso.

## 4 bis. AI Squad e Scrum agentico

### Piramide organizzativa

I ruoli AI sono organizzati in una piramide. Per ogni livello si definiscono compiti e competenze, così da assegnare a ogni ruolo un agente con il modello adatto.

| Livello | Esempi | Come lavora |
|---|---|---|
| Alto | Coordinatore AI, analista funzionale, architetti | **Personas** con un profilo professionale umano, legate agli obiettivi funzionali e di business. Più il ruolo è alto, più è specifico del progetto o del dominio |
| Medio | Scrum Master AI, revisori | Coordinano e verificano secondo template e criteri dati dal Coordinatore AI |
| Basso | Esecutori, unit tester | Ruoli molto automatizzati, che seguono regole di collaborazione di base |

- Ogni ruolo ha le basi di competenza della propria professione. Per esempio, un architetto conosce l'ADM di TOGAF, nei limiti d'uso dello standard (§5).
- Si usano possibilmente **modelli di origine diversa** per creare confronti efficaci (§4).
- A ogni ruolo si applicano **Mode e Role** secondo le linee guida del fornitore del modello, per rendere il comportamento prevedibile e controllabile nei diversi contesti (§9).
- Ogni profilo ha uno **Unit Cost**, perché l'AI non è gratis. I motori locali hanno un costo legato all'uso delle risorse locali, cioè ore macchina per una tariffa dichiarata. Lo Unit Cost serve a stimare e rendicontare il costo del progetto.

### Seniority Digitale

In un'organizzazione ogni persona lavora al livello di esperienza che il compito richiede. Eiraman applica la stessa regola agli agenti. La **Seniority Digitale** di un agente è la combinazione di **motore** e **livello di ragionamento** con cui il Coordinatore AI lo attiva. Per esempio, in Claude: Haiku, Sonnet, Opus o Fable, ciascuno con un livello di ragionamento da basso a massimo.

| Livello | Nome | Quando si usa | Esempio di configurazione in Claude |
|---|---|---|---|
| SD1 | Junior | Compiti ripetitivi con esito verificabile da un controllo deterministico | Haiku, ragionamento basso |
| SD2 | Professional | Lavoro corrente su specifica chiara | Sonnet, ragionamento medio |
| SD3 | Senior | Scelte locali di progetto, diagnosi, revisione del lavoro di altri | Sonnet, ragionamento alto |
| SD4 | Lead | Architettura, sicurezza, effetti difficili da annullare, schede Do, giudizio tra candidate | Opus, ragionamento alto |
| SD5 | Principal | Problemi nuovi o ad alto impatto, per eccezione e con motivazione registrata | Fable, ragionamento molto alto |

- **Catalogo.** Ogni Role Profile elenca i task e i deliverable che il Coordinatore AI può assegnargli, ciascuno con il livello minimo e la configurazione corrispondente per ogni strumento ammesso (Claude Code, Codex, GitHub Copilot). La corrispondenza tra livello e configurazione si mantiene in un'unica mappa del registro dei profili, da riverificare a ogni cambio di modello (§9).
- **Ripiego.** Un task che non rientra nel catalogo si esegue a SD4. Il Coordinatore AI lo registra e propone di aggiungerlo al catalogo (§11).
- **Partecipazione alle squadre.** Un agente partecipa a uno Scrum Team con la seniority **più alta** richiesta dai task che deve eseguire nel Work Package.
- **Verifica.** Il revisore o tester indipendente lavora almeno allo stesso livello dell'esecutore che verifica.
- **Promozioni e riduzioni.** Dopo due tentativi falliti per carenza di capacità, il Coordinatore AI sale di un livello e lo registra. La promozione usa i tentativi consentiti dalla scheda del Work Package (§6): se sono esauriti, apre un punto decisionale. Nella retrospettiva può abbassare il livello di un task se le prove mostrano qualità invariata a costo minore: è una porta a due vie entro la tolleranza del mandato, oltre la quale è un Do.
- **Costo.** Lo Unit Cost si tara per livello e ogni run registra livello, motore e ragionamento effettivi (§7).

### Squadre e Scrum agentico

Il lavoro degli agenti segue i principi di Scrum, modificati per la collaborazione tra AI:
- **Niente Sprint né timebox umani.** L'unità di consegna è la Wave, limitata da token, costo e durata (§5). Non si applicano i limiti di Scrum sul numero dei componenti di un team: il limite dipende dagli ambienti LLM usati.
- **Una squadra per Work Package.** Il Coordinatore AI forma ogni squadra con i ruoli e le competenze necessari al pacchetto, fino a comporre le *squad* dello Staff Planning.
- **Uno Scrum Master AI per squadra.** Coordina gli agenti della squadra, gestisce il Log Tracker insieme al pacchetto e consegna al Coordinatore AI un **report delle attività** sul template indicato dal Coordinatore AI.
- **Contesto condiviso, tranne che per il tester.** Gli agenti di una squadra condividono lo stesso contesto. L'eccezione è lo **unit tester**: riceve requisiti, contratti, dati e risultati attesi (§2), ma non la discussione della squadra, per non influenzare i test. Può operare su un motore diverso, esterno o locale, oppure sullo stesso motore senza quel contesto. Per i pacchetti che toccano sicurezza o dati personali lo stesso motore non basta: serve almeno un modello diverso (§4).
- **Squadre in concorrenza.** Lo stesso Work Package può essere assegnato a più squadre che lavorano in concorrenza, con motori o composizioni diverse. Si usa quando la parte generativa è particolarmente complessa, come la scrittura di documenti, e con le regole K1–K9. Per default la candidata resta una sola (K3).

### Scrum of Scrums e ruolo del Coordinatore AI

Il lavoro è organizzato centralmente dal Coordinatore AI, che assegna e valida il lavoro delle squadre. Rispetto a uno Scrum Master ha in più la **validazione tecnica e di conformità**:
- fissa i criteri di qualità e di funzionalità da verificare perché un pacchetto sia completato;
- verifica a fine pacchetto la corretta esecuzione (§6, Chiusura);
- risolve le dipendenze tra squadre e chiude la Wave solo dopo la verifica dell'incremento integrato.

**Retrospettiva.** Alla fine di ogni ciclo il Coordinatore AI analizza i report degli Scrum Master e:
- ottimizza la composizione delle squadre, per esempio alzando il livello di seniority di un architetto o cambiando il modello di un ruolo;
- rivede le decisioni operative.

I miglioramenti che portano risparmi senza ridurre la qualità, o riducendola entro la tolleranza fissata nel mandato, si applicano senza coinvolgere il Manager umano. Ogni possibile cambio di una Decisione approvata richiede invece il Manager umano, con la SWOT preparata dal Coordinatore AI (§3, Do).

**Flessibilità delle Decisioni.** Rispetto a Scrum tradizionale è consentita una maggiore flessibilità nel cambiare le Decisioni, perché scalare e coordinare AI Squad per gestire il cambiamento costa meno. Il costo del cambiamento e del rework si stima e si riporta nella scheda del Do.

## 5. Dalla Visione al rilascio

### Governare lo scopo

- La Visione diventa vincolante con l'approvazione del mandato. Un suo cambiamento apre un nuovo progetto.
- I Principi si congelano per versione al termine del planning. Se un Principio cambia durante l'installazione, il Coordinatore AI segna la versione come fallita, censisce lo stato installato e governa ripristino o transizione a una nuova versione.
- I **criteri di successo** di una versione e del progetto si basano su KPI misurabili nelle procedure di test.
- Le Decisioni non possono violare un Principio. Sono collegate tra loro: la modifica di una Decisione può richiedere la modifica di quelle collegate, che vanno riesaminate.
- Ogni Decisione ha identificativo, proprietario, stato, motivazione, Principi collegati e dipendenze. Una nuova Decisione rinvia a quella sostituita e ai pacchetti da riesaminare. Un risparmio che modifica una Decisione passa dal Manager umano anche quando rientra nella tolleranza di qualità.
- Ogni punto aperto indica la Wave che blocca e il criterio per chiuderlo.
- Il mandato contiene i **criteri di arresto** del progetto: spesa, numero di Wave senza incremento accettato, POC negativo.

### Ciclo di produzione

**Tutte e cinque le fasi sono eseguite dal sistema AI**, organizzato in Wave, con le stesse regole: escalation 3D, meccanismi concorrenziali, chiusura su evidenza, registrazione dei costi. Il Manager umano interviene solo nei punti di decisione indicati per ciascuna fase.

| Fase | Chi lavora (sistema AI) | Che cosa produce | Meccanismi concorrenziali tipici | Decisione del Manager umano |
|---|---|---|---|---|
| 1. Scoperta | Coordinatore AI, analista e più agenti esploratori di modelli diversi, entro guardrail | Problema, beneficio, alternative scartate, bozza di Visione; classe assegnata dal gate di applicabilità (§10) | Divergenza: più agenti generano ipotesi in modo indipendente. Convergenza: l'analista seleziona e riconduce alle evidenze degli utenti | Approva Visione, mandato e classe; può rilanciare un giro di esplorazione |
| 2. POC | Coordinatore AI, analista, architetto, esecutori, tester | Incertezza esplicitata, prova ripetibile di fattibilità, risorse e accessi necessari | Prove alternative sullo stesso quesito tecnico, quando il selettore è misurabile (K1) | Do solo se l'esito è negativo o richiede nuovi accessi o spesa |
| 3. Design e planning | Analista, architetto applicativo, architetto infrastrutturale, Scrum Master AI, Coordinatore AI | Viste di business, applicazioni, dati e tecnologia; contratti, backlog, Work Package, profili, stima dei costi, criteri di test; proposte di Principi e Decisioni | Architetture alternative valutate con rubrica fissata prima | Approva Principi, Decisioni con impatto di business e budget; i Principi si congelano |
| 4. Scale | Coordinatore AI, team AI con Scrum Master AI, tester e revisori | Incrementi software chiusi su evidenza | K1–K9 sui pacchetti generativi | Ciclo di governo: revisione periodica e Do |
| 5. Accettazione ed esercizio | Coordinatore AI, tester, ruoli di esercizio | Collaudo, release, manuali, gestione del servizio | Diagnosi alternative di un incidente | Accettazione del risultato (UAT) e Do sull'esercizio |

Il progetto può richiamare lo standard TOGAF® nella fase 3, secondo le condizioni applicabili al suo utilizzatore. Capacità e budget stabiliscono il parallelismo in ogni fase.

In esercizio, dal livello 2, valgono SLO, gestione degli incidenti e postmortem senza colpa, che sono input della retrospettiva (§10). Con l'error budget esaurito, l'ambiente applica un Deny sui rilasci non correttivi.

### Design Thinking affidato all'AI (fase 1)

Lasciati liberi, i motori AI sono potenti raccoglitori e diffusori di informazioni, ma tendono a divergere. Per questo la Scoperta segue il Design Thinking con ruoli e confini precisi.

1. **Divergenza.** Più modelli, con ruoli e comportamenti definiti, generano e dettagliano in modo indipendente ipotesi, problemi, benefici e principi della Visione. Guardrail: numero massimo di giri, fonti e dati ammessi, criteri per scartare un'ipotesi.
2. **Gate del Manager umano.** A gate prefissati il Manager umano può dare nuovi spunti, che rilanciano un giro di divergenza.
3. **Convergenza.** Un solo modello, con il ruolo di **analista funzionale**, raccoglie i contributi, li rivede coordinando gli altri agenti e li riconduce alle evidenze degli utenti. Produce l'idea di base del progetto, la bozza della Visione e una **prima versione dello Scope Management**: Visione, Principi, criteri di successo e punti aperti.
4. Il Manager umano approva la Visione oppure rilancia l'esplorazione.

### POC, Design e planning

- **POC e MVP.** L'analista funzionale valida la fattibilità, in modo teorico oppure chiedendo al Coordinatore AI piccoli Work Package di prova. Si validano anche le risorse necessarie in termini di calcolo e di accessi. Per esempio, la capacità di un motore locale di elaborare un documento della dimensione attesa entro tempo e costo previsti.
- **Design e planning.** L'analista funzionale lavora prima con l'architetto applicativo, poi con gli architetti infrastrutturali e lo Scrum Master AI. Insieme producono:
  - il design architetturale;
  - il Product Backlog e i workstream;
  - la **stima dei costi della componente AI**;
  - la stima iniziale delle prestazioni, che sarà aggiornata dai test nella Performance Analysis.

  Il Manager umano valida le soluzioni proposte, che diventano Principi e Decisioni. Al termine i Principi sono immutabili per quella versione. Il design segue le linee guida architetturali dei vendor o delle comunità open source delle tecnologie scelte, e gli architetti hanno queste competenze nei loro profili.

### Wave e ciclo di governo

- **Wave.** È l'unità di consegna tecnica in tutte le fasi e segue il ritmo delle AI.
  - Ha un tetto di spesa e una durata massima; vale il limite raggiunto per primo.
  - All'80% della spesa il Coordinatore AI lo segnala. Al 100% scatta un Deny su nuovo lavoro e la Wave si chiude con un checkpoint.
  - Le Wave si susseguono in automatico entro mandato e budget.
  - Una Wave si chiude dopo la verifica dell'incremento integrato.
- **Ciclo di governo.** È l'unità di decisione del Manager umano e ha una cadenza di calendario. Si chiude con una sola revisione manageriale, che contiene:
  - consegne e accettazioni;
  - spesa e costo per incremento accettato;
  - stato del budget di deriva (E5);
  - numero dei casi di divergenza elevata (K8; i singoli casi restano al revisore di processo) e temi ricorrenti (K9);
  - Do aperti;
  - proposta per il ciclo successivo.

  Se il ciclo scade senza approvazione del successivo, le Wave in corso completano il pacchetto attivo e non ne aprono di nuovi.
- **Carico di escalation.** È un indicatore del ciclo di governo e non blocca mai un Do dovuto. Si legge insieme alla sotto-escalation.
  - Si contano i Do ordinari di tutte le fasi e le escalation K9.
  - Non si contano i Do urgenti, conteggiati a parte, né le decisioni previste dalle fasi.
  - I Do non urgenti si raggruppano nella revisione del ciclo, salvo quelli che bloccano il percorso critico.
- **Indicazione.** Ciclo settimanale; riferimento di 3 Do ordinari per ciclo; circa 30 minuti di attenzione del Manager umano a settimana. Ogni utente può fissare valori propri nel mandato. La revisione del ciclo mostra sempre il valore dichiarato accanto a quello osservato. Il valore si cambia solo alla revisione del ciclo.

## 6. Contratti di lavoro e verifiche

### Composizione

I componenti (Backbone, Brain, Hands/Foot/Eyes/Ears, Hairs) sono definiti nel §6 bis. Ogni componente dichiara contratto, dati, dipendenze, prova di integrazione e, se periferico, verifica del comportamento alla sua rimozione. Il primo percorso utilizzabile attraversa Backbone e Brain e include le interfacce essenziali. Priorità e regole di dettaglio sono nel §6 bis.

### Scheda minima di un Work Package

La scheda registra:
- progetto e Wave, ID, revisione iniziale;
- criteri di successo ed esclusioni;
- Principi e Decisioni, dipendenze;
- profili e versioni;
- budget e tentativi consentiti;
- risultato atteso e verificatore;
- procedura di ripresa.

Il consuntivo include tutte le candidate, anche quelle scartate.

I criteri funzionali si scrivono nella forma Dato/Quando/Allora. Quelli non funzionali si riferiscono alle caratteristiche ISO/IEC 25010. Un Work Package è pronto solo quando i suoi criteri sono eseguibili.

### Chiusura

- **Evidenza positiva.** Il Coordinatore AI chiude il pacchetto quando i controlli obbligatori sulla candidata identificata sono superati e le evidenze sono identificabili. Una modifica alla candidata riapre le verifiche interessate.
- **Dissenso o prova mancante.** Il pacchetto resta aperto.
  - Con un requisito chiaro si ripete la prova o si incarica un secondo verificatore.
  - Con un requisito ambiguo si apre un punto decisionale.
  - Si registrano esito, dissenso e motivazione della chiusura.
- **Test.** Componente, integrazione, sistema e accettazione. Corrispondenza con «DevSecOps e test»: unit test = componente; test funzionali con script o utente simulato = integrazione e sistema; UAT = accettazione.
- **Ancore deterministiche.** A ogni rilascio si eseguono analisi statica, analisi di dipendenze e licenze e ricerca di segreti. Al livello 2 si aggiunge la scansione dinamica. I ruoli AI ne interpretano gli esiti, non li sostituiscono.

### DevSecOps e test

Il lavoro segue le pratiche DevSecOps, dove applicabili:
- **Registro Git** dell'applicazione e delle versioni, con commenti scritti per essere letti anche da persone.
- **Security by Design**, con analisi statica (SAST) e, al livello 2, penetration test (§10).
- **Test fortemente automatizzati**, eseguiti da agenti dedicati:

| Tipo | Chi e come | Esito |
|---|---|---|
| **Unit test** | Alla fine di ogni Work Package, eseguiti dal tester AI indipendente. Verificano anche i componenti di sicurezza e prestazioni | Aggiornano la Security Risk Posture e la Performance Analysis |
| **Test funzionale con script** | L'agente lancia lo script di test, registra i log e verifica il completamento o il fallimento | Per errori grossolani che non toccano qualità né Decisioni, l'agente corregge in autonomia, come porta a due vie |
| **Test funzionale con utente simulato** | Un agente simula un utilizzatore tipo e usa l'applicazione come farebbe una persona | Va eseguito in ambienti stabili, perché costa di più |
| **UAT (collaudo finale)** | Una persona svolge il compito di business, e l'AI la assiste registrando osservazioni e informazioni mancanti | Il Manager umano decide sull'accettazione |

I test funzionali sono *supervisionati dall'umano*: la persona può osservarli, ma non deve intervenire per farli procedere. L'UAT è *supervisionato dall'AI*: la persona esegue, l'AI registra.

## 6 bis. Architettura componibile

L'idea alla base di un'applicazione si scompone in **componenti legati alle funzioni**, modellati e sviluppati in modo indipendente nei Work Package. Nel Vibe Coding il punto centrale è la **priorità di realizzazione**. La flessibilità dell'AI rende facile aggiungere pezzi, e senza un catalogo e un ordine si costruiscono patchwork troppo complessi.

| Componente | Che cosa è | Regola di priorità |
|---|---|---|
| **Backbone** | I componenti centrali, necessari al core deliverable | Si realizza prima di tutti gli altri componenti. copre in forma minima tutti i principali percorsi del core deliverable |
| **Brain** | La logica dell'applicazione, sempre più spesso fatta di motori AI interni o esterni | I compiti del Brain si catalogano come **trusted** o **untrusted**. Da questo dipende quali compiti si delegano ai motori e quali restano sotto controllo deterministico o richiedono un Do (§3, §7) |
| **Hands, Foot, Eyes, Ears** | Le interfacce con cui l'applicazione comunica e interagisce con gli utenti. Sono spesso la parte che più si estende | Poggiano su Backbone e Brain. Si sviluppano presto in forma essenziale, dentro il primo percorso utilizzabile, e in forma avanzata solo dopo che i componenti precedenti sono stabili |
| **Hairs** | Le funzioni più periferiche, aggiunte o tolte in qualsiasi momento, anche per piccoli compiti specifici | Ultime in priorità; si aggiungono o si tagliano in qualsiasi momento. prima di toglierne una si verifica che il nucleo superi la regressione |

Il **Product Backlog** etichetta ogni workstream con il componente e la priorità, e lo collega alle Decisioni e ai punti aperti da cui dipende.

**Documento architetturale.** Il documento architetturale, sviluppato secondo le viste TOGAF di business, applicazioni, dati e tecnologia, specifica ai livelli dati e infrastruttura le best practice usate per disegnare e integrare l'architettura in modo componibile. Per esempio, le richieste a un motore LLM **locale** si gestiscono diversamente da quelle a un motore **esterno**: piccole richieste pacchettizzate nel primo caso, una richiesta unica nel secondo. la scelta si misura sullo stesso carico, confrontando qualità, latenza, costo e vincoli sui dati.

## 7. Ambiente, esecuzione e sicurezza degli agenti

### Esecuzione e recupero

- **Apertura del progetto.** Il Coordinatore AI:
  - risolve la versione del metodo e dei profili;
  - verifica lo stato del repository e le capacità disponibili;
  - configura runner e connettori;
  - prova le autorizzazioni necessarie.

  Un accesso che richiede il titolare dell'account apre una richiesta circoscritta. L'ambiente applica i vincoli sugli strumenti e conserva i segreti nel deposito credenziali della piattaforma.
- **Esecuzioni.** Ogni esecuzione ha ID, stato persistito, versione degli input, checkpoint, budget e limite di tentativi.
- **Ripresa.** Dopo un'interruzione il Coordinatore AI riconcilia lo stato con gli effetti già prodotti prima di ripartire. Se il Coordinatore AI non è disponibile, il runtime conserva il lavoro e impedisce nuove operazioni fuori controllo. Al riavvio il Coordinatore AI verifica l'ultima consegna, poi riprende o ripristina la versione precedente.

### Sicurezza degli agenti e tracciabilità

- **Security Risk Posture.** Identifica i requisiti di sicurezza e classifica l'applicazione in base a esigenze, contesto e tipo di dati trattati. Riporta i requisiti di compliance da applicare (per esempio GDPR), i dati personali e come sono gestiti, i perimetri di sicurezza, le porte e i servizi aperti, e le specifiche che garantiscono il livello di sicurezza di ogni componente architetturale. L'approccio è Security by Design.
- La Security Risk Posture include anche una sezione **Agenti**. Per ogni ruolo indica strumenti ammessi, destinazioni di rete, dati leggibili e azioni irreversibili, che sono sempre Do. Riferimento: OWASP Top 10 per LLM e applicazioni agentiche.
- I compiti del Brain catalogati **untrusted** (§6 bis) non si delegano a un motore senza un controllo deterministico del risultato. Se l'azione è irreversibile, è un Do.
- **Test negativo obbligatorio.** Un input con un'istruzione ostile deve produrre un Deny registrato.
- Ogni run registra l'hash del profilo, l'identificativo esatto del modello, la configurazione effettiva e lo Unit Cost. Il prodotto include una SBOM. L'obiettivo è la tracciabilità, perché l'output di un LLM non è riproducibile in modo deterministico.
- Il mandato contiene la tabella delle **classi di dati per provider**: quali provider sono ammessi per ciascuna classe, tenendo conto di conservazione e addestramento.

La delega considera separatamente provenienza dei dati, permessi del ruolo, destinazioni consentite e reversibilità.

## 8. Documentazione

| Livello | Destinatario | Contenuto | Verifica |
|---|---|---|---|
| Strategico | Manager umano, che approva | Visione, Principi, criteri di successo, mandato | Manager umano |
| Manageriale | Manager umano, che legge e decide per eccezione | Scheda di progetto, piano in milestone, vista architetturale di alto livello, schede decisione, rischi di business, dashboard, revisione del ciclo, esito UAT, rendiconto, sintesi di sicurezza e prestazioni | Revisore AI |
| Operativo | Agenti | Architettura, backlog, Work Package e Staff Planning, Log Tracker, registri di dettaglio, evidenze di test | Sistema di AI |

**Regole di redazione per il Manager umano.**
1. Linguaggio di business.
2. Apertura con le quattro domande: cosa è cambiato, cosa si chiede, entro quando, cosa succede se non risponde.
3. Prima le variazioni rispetto all'ultima lettura.
4. Limiti di lunghezza: una pagina per scheda decisione.
5. Esiti, non procedure.
6. Ogni affermazione verificabile è collegata a un'evidenza, e il revisore AI controlla il collegamento.
7. **Prova di comprensione** da parte di un agente con il profilo del Manager umano, tarata una volta dal Manager umano su circa 5 documenti.
8. **Set minimo per livello**, indicato nei requisiti del §10.
9. **Prima le cattive notizie:** test falliti, rischi aperti, dissensi, rifiuti, decisioni mancanti.
10. **Controllo di completezza:** un'omissione rispetto ai registri operativi blocca la consegna del documento.
11. **Pacchetto di evidenze per terzi:** su richiesta, per un singolo rilascio; al livello 2 è pronto a ogni rilascio. Contiene mandato, classe e livello, profili e versioni, controlli ed esiti, verifiche indipendenti, rischi accettati e accettazione.
12. **Modelli qualificati:** ogni tipo di documento ha un modello versionato e qualificato dai manutentori.

**Rilascio.**
- Manuale di installazione e uso a ogni livello; Executive Description e Performance Analysis quando previsti dal livello. Sono verificati a ogni rilascio.
- La Performance Analysis confronta le prestazioni del prodotto con le attese.
- Il rendiconto mostra separatamente costi di sviluppo e costi di utilizzo dell'applicazione.
- Un avanzamento espresso in percentuale dichiara il denominatore.

**Artefatti di governo.**
- **High Level Plan:** il piano di alto livello delle attività, presentato al Manager umano in milestone.
- **High Level Architectural View:** una pagina, con un disegno, che mostra al Manager umano di quali parti è fatto il prodotto, in termini comprensibili a chi non è del mestiere:
  - i punti di contatto con le persone, per esempio una pagina web, un'app o un'email;
  - dove stanno i dati, per esempio un database, un archivio di documenti o un foglio di calcolo, e quali classi di dati contengono;
  - i servizi esterni e i motori AI usati, distinguendo quelli locali da quelli esterni all'organizzazione;
  - i flussi principali tra le parti e i confini, cioè che cosa esce dall'organizzazione e chi vi accede.

  Non riporta sistemi operativi, linguaggi, versioni, librerie né configurazioni: quei dettagli restano nel documento architetturale operativo (§6 bis), da cui la vista è derivata. Il Coordinatore AI la aggiorna quando una parte nasce, cambia o scompare. Un cambiamento che aggiunge un servizio esterno o sposta dati fuori dall'organizzazione è un Do.
- **Risk Log:** i rischi di fallimento del progetto e la loro gestione secondo il Risk Management. Al Manager umano arrivano i rischi di business; il dettaglio resta operativo.
- **Executive Description:** breve descrizione del prodotto e delle sue funzioni, per presentarlo a chi non è del mestiere. Il Coordinatore AI la tiene aggiornata e verificata.
- **Product Backlog:** contiene i workstream che le squadre possono svolgere, etichettati e ordinati secondo l'architettura componibile (§6 bis).
- **Work Package e Staff Planning:** definiscono i pacchetti e le competenze, cioè i ruoli AI, fino alla composizione delle squadre (§4 bis).
- **Performance Analysis:** riporta le prestazioni più significative del prodotto, per esempio il tempo di produzione di un documento. Si stima nel design e si aggiorna con i test.
- **Log Tracker:** non è pensato per essere letto da persone. È il registro generale di tutte le attività, usato dal Coordinatore AI per seguire l'avanzamento delle squadre.
- **Dashboard di avanzamento:** pagina HTML aggiornata dal Coordinatore AI, con la percentuale di avanzamento di ogni fase, dichiarandone il denominatore. Contiene anche un albero dei Work Package (completati, in corso con percentuale, da fare) con la stima di costo di ciascuno; per ogni pacchetto il Manager umano vede descrizione, deliverable e composizione della squadra per Role Profile. Una pagina collegata raccoglie i documenti strategici e manageriali del progetto.

**Forma degli artefatti di controllo.** In logica Scrum, ogni progetto e ogni Manager umano decidono la forma degli artefatti che usano per il controllo. Dashboard, viste e documenti descritti qui sono un punto di partenza: il Manager umano li adatta nel ciclo di sviluppo e controllo dell'applicazione, e la scelta si registra come decisione di progetto. Restano fermi i contenuti minimi richiesti dalle regole di redazione e dal livello (§10).

**Misura.** Per ciclo di governo si registrano minuti di lettura, decisioni, domande di chiarimento e omissioni intercettate.

## 9. Role Profile e manutenzione del metodo

Un Role Profile contiene:
- scopo, responsabilità, azioni consentite e vietate, contratto di comunicazione;
- **fonti normative con riferimento puntuale** alla clausola dello standard da cui deriva ogni regola;
- **strumenti deterministici obbligatori** e come interpretarne gli esiti;
- **suite di qualificazione** con casi a risposta nota;
- **modelli abilitati** e livello di ragionamento;
- **limiti dichiarati**: se un pacchetto vi ricade, il progetto esce dal perimetro;
- **curatore e revisore**, data e scadenza della qualificazione;
- **repository documentale** del ruolo, cioè le fonti in cui l'agente cerca informazioni per i suoi compiti. Per esempio, per un architetto di un vendor cloud, il sito con le specifiche di prodotto e le architetture di riferimento;
- **motori abilitati** cloud e locali, con i requisiti minimi. Per un motore locale, per esempio, la dimensione minima in miliardi di parametri;
- **catalogo dei task per livello di Seniority Digitale** (§4 bis): quali compiti il ruolo può svolgere e con quale motore e livello di ragionamento. Il Coordinatore AI sceglie la configurazione per ogni Work Package;
- **Mode e Role** secondo le linee guida del fornitore del modello;
- **Unit Cost** del profilo per ciascun motore e livello di Seniority Digitale;
- **catalogo dei task e dei deliverable** che il Coordinatore AI può assegnare al ruolo, con il livello di Seniority Digitale di ciascuno e la configurazione di attivazione per ogni strumento ammesso; i task fuori catalogo si eseguono a SD4 (§4 bis).

**Struttura nel registro Git.** Ogni Role Profile è una cartella nel registro Git, con due tipi di file:
- **file Markdown di istanziazione:** descrizione, scopi, metodologie, regole di comunicazione, azioni consentite e vietate (per esempio, un architetto non modifica il codice e uno sviluppatore non modifica i documenti architetturali), repository documentale;
- **file descrittivi:** motori abilitati, catalogo dei task per livello di Seniority Digitale, Unit Cost, qualificazione.

Il Coordinatore AI apprende dal registro Git il proprio profilo e le competenze necessarie, e istanzia i Role Profile richiesti dalle varie fasi.

**Pubblicazione.** Prima un LLM esegue la **pre-valutazione**: suite, coerenza con le fonti, formato, ricerca di istruzioni anomale. L'LLM può respingere un profilo, ma non approvarlo. Poi il **revisore esperto del dominio** lo pubblica in una versione firmata.

**Regole di manutenzione.**
- Quattro occhi: l'autore di una modifica non può esserne il revisore.
- Ogni dominio ha un revisore titolare e un sostituto: architettura cloud, sicurezza, architettura applicativa e dati, test e qualità, privacy, legale e compliance.
- A ogni cambio di modello la suite riesegue tutti i profili, e il revisore esamina solo le differenze di comportamento.
- Un profilo non riqualificato entro il termine viene sospeso.
- Un dominio senza revisore non può pubblicare profili.
- Chi contribuisce cede o licenzia il contributo secondo le regole dell'organizzazione.
- Il revisore risponde della correttezza del profilo rispetto alle fonti al momento della revisione, non dei progetti che lo usano.
- Le stesse regole valgono per i modelli di documento e per la checklist del gate.

## 10. Livelli di applicabilità

### Principio

Nei progetti Eiraman la competenza specialistica è nei Role Profile qualificati e non nella presenza di specialisti in ogni progetto. Il rischio che il responsabile business non può valutare va quindi limitato in partenza. Ogni adozione di Eiraman ha un **livello qualificato** e ogni progetto ha una **classe**. Un progetto può essere eseguito solo se la sua classe non supera il livello qualificato di chi lo adotta. Le classi valgono anche per i deliverable che un prodotto genera. Chi usa il metodo per sé resta al livello 0. Per salire deve soddisfare i requisiti del livello successivo e dimostrarli con evidenze.

### Classi di progetto

| Classe | Utenti | Dati | Esposizione | Esempi |
|---|---|---|---|---|
| 0 | Solo chi adotta | Nessun dato personale di altri | Locale o nessuna | Strumenti personali, generatori di documenti per uso proprio |
| 1 | Colleghi della stessa organizzazione | Dati personali comuni di colleghi | Rete interna o cloud con identità aziendale | Applicazioni di reparto |
| 2 | Clienti, fornitori o pubblico autenticato | Dati personali comuni di terzi, volumi contenuti | Internet con autenticazione | Portali, servizi self-service, documenti destinati a clienti |

**Fuori perimetro, a qualsiasi livello:**
- dati particolari o giudiziari (artt. 9–10 GDPR);
- dati di minori;
- trattamento su larga scala;
- trattamento per cui lo screening rende obbligatoria una DPIA (art. 35 GDPR);
- decisioni automatizzate su persone (art. 22 GDPR);
- pagamenti gestiti nel codice prodotto;
- AI vietata o ad alto rischio secondo l'AI Act;
- titolare soggetto alla direttiva NIS2;
- software distribuito da installare o dispositivi soggetti al Cyber Resilience Act, in attesa di requisiti dedicati;
- normative di settore;
- sicurezza fisica.

### Gate di applicabilità

Un ruolo AI di compliance assegna la classe con una checklist versionata e qualificata dai manutentori. Il gate si esegue all'apertura del progetto, a ogni Wave e a ogni cambio di mandato. Se un criterio di esclusione scatta, o se il caso è dubbio, il progetto è fuori perimetro e il responsabile business ne viene informato.

La checklist distingue i **criteri di esclusione**, elencati sopra, dai **requisiti**, che vanno soddisfatti ma non escludono. Per esempio:
- la trasparenza verso gli utenti di chatbot e contenuti generati (art. 50 AI Act);
- un DPO già designato quando l'organizzazione vi è tenuta (art. 37 GDPR).

La checklist non sostituisce una consulenza legale.

### Requisiti per livello

I requisiti sono cumulativi.

**Livello 0 · Uso personale**
- *Framework:* Role Profile di base qualificati. Analisi statica, controllo di dipendenze e licenze, ricerca di segreti a ogni rilascio. Documenti per il Manager umano: scheda di progetto, schede decisione, revisione del ciclo di governo, manuale di installazione e uso.
- *Organizzazione:* chi adotta è titolare e responsabile del progetto e di ciò che il progetto produce.
- *Evidenze:* nessuna evidenza preliminare.

**Livello 1 · Team interno.** Per salire dal livello 0:
- *Framework:*
  - profili di sicurezza e privacy qualificati per la classe 1;
  - autenticazione solo tramite l'identità aziendale;
  - prova di backup e ripristino prima del rilascio;
  - regole su contenuto e conservazione dei log;
  - screening DPIA a ogni cambio di trattamento;
  - procedura di notifica delle violazioni entro 72 ore (art. 33 GDPR), scritta per il Manager umano;
  - documenti aggiuntivi per il Manager umano: sintesi manageriale della Security Risk Posture, scheda del trattamento per il titolare, Executive Description.
- *Organizzazione:*
  - organizzazione titolare identificata;
  - mandato formale al Manager umano;
  - politiche IT aziendali come input vincolante del mandato;
  - DPO designato, se l'organizzazione vi è tenuta.
- *Evidenze:* esperienza al livello 0 con risultati misurati:
  - sotto-escalation entro la soglia, dopo la taratura;
  - rilevazione di una suite di vulnerabilità inserite di proposito almeno alla soglia fissata dai manutentori;
  - nessun rilievo critico aperto al rilascio.

**Livello 2 · Utenti esterni.** Per salire dal livello 1:
- *Framework:*
  - requisiti OWASP ASVS di livello 1 selezionati e verificati;
  - scansione dinamica a ogni rilascio;
  - autenticazione e pagamenti solo tramite fornitori certificati;
  - esercizio con SLO, gestione degli incidenti e postmortem;
  - politica di aggiornamento delle dipendenze e di correzione delle vulnerabilità, bloccante del rilascio se il prodotto è offerto in un'attività commerciale (direttiva (UE) 2024/2853, art. 11, par. 2);
  - documenti aggiuntivi per il Manager umano: sintesi del penetration test, Performance Analysis;
  - pacchetto di evidenze per terzi pronto a ogni rilascio.
- *Organizzazione:*
  - penetration test esterno acquistato come servizio, al primo rilascio e poi periodicamente; il Coordinatore AI ne prepara perimetro e autorizzazione, il Manager umano ne decide il costo;
  - contratti con i fornitori che trattano dati (art. 28 GDPR).
- *Evidenze:* esercizio al livello 1 per un periodo definito senza incidenti gravi; esito positivo del penetration test sulla prima release di classe 2.

### Salita e discesa

- **Salita.** È una porta a una via e quindi un Do. Il Coordinatore AI presenta un dossier manageriale con:
  - requisiti soddisfatti;
  - evidenze;
  - costi ricorrenti;
  - rischi residui.

  Un revisore indipendente verifica le evidenze prima del Do.
- **Discesa automatica.** Se un requisito decade (profilo sospeso, penetration test scaduto, incidente grave aperto), l'ambiente applica un Deny. Sono ammessi solo rilasci correttivi finché il requisito non viene ripristinato o il progetto non torna alla classe consentita.
- **Cambio di classe.** È sempre un Do e conta nel budget di deriva. Se la nuova classe supera il livello, il Manager umano sceglie tra:
  - ridurre il perimetro;
  - affidare il componente critico a un fornitore certificato;
  - uscire dal metodo per quel progetto.

### Punti aperti

| Punto | Blocca | Criterio di chiusura |
|---|---|---|
| Soglie numeriche: suite di vulnerabilità, sotto-escalation, durata dell'esercizio al livello 1 | Prima salita al livello 1 | Proposta dei manutentori dopo il pilota NUR, approvata dal Manager umano |
| Periodicità del penetration test | Prima salita al livello 2 | Decisione economica del Manager umano su proposta del Coordinatore AI |
| Contenuto della checklist del gate | Livello 0 | Checklist versionata e qualificata dai manutentori |
| Interfaccia per il Manager umano (app dedicata o estensione VS Code) | Prima adozione fuori dal pilota | Percorso valutato nel pilota NUR: apertura del progetto, conferimento del mandato, decisione su un'eccezione, consultazione delle evidenze, accettazione del risultato. Il Coordinatore AI svolge l'intero lavoro tecnico; la scelta spetta al Manager umano |

## 11. Projects, applicazione parziale e ritorno al metodo

**Scheda di progetto.** Identifica:
- applicazione, utenti, deliverable, repository e revisione;
- versione di Eiraman usata, classe e livello;
- componenti Eiraman incorporati nel prodotto e adattamenti;
- criteri di successo.

Il Coordinatore AI conserva due collegamenti distinti: tra pacchetto e release software, e tra esecuzione del prodotto e deliverable generato. Per ogni componente adottato si registra dove opera e con quale versione.

**Applicazione parziale.**
- Un prodotto che incorpora parti del metodo pubblica una **dichiarazione di conformità parziale**, con le regole applicate e quelle non applicate. Non può presentarsi come conforme a Eiraman senza questa qualificazione.
- Le **classi** di applicabilità valgono anche per i deliverable del prodotto. Per esempio, un'adozione di livello 0 non può usare NUR per produrre documenti destinati a clienti, che sono di classe 2.
- Ogni componente incorporabile dichiara contratto, prove di regressione, versione e regole implementate.

**Ritorno al metodo.**
- *Osservazione.* La retrospettiva collega caso riproducibile, regola applicata, esito e costo. Il Coordinatore AI individua se l'origine riguarda dati, applicazione, ambiente o metodo.
- *Proposta.* Una correzione specifica resta nel backlog dell'applicazione. Per una regola o un componente riusabile servono contratto, prova, limiti e impatto sui progetti esistenti. Ogni modifica di Principi o Decisioni segue le approvazioni previste.
- *Adozione.* La modifica approvata si versiona, con compatibilità, prova di regressione e progetti che la adottano. Il progetto che l'ha motivata conserva il riferimento al cambiamento. Un altro progetto può adottare il solo componente pertinente.

**Il metodo come progetto.** La gestione del metodo è anch'essa un progetto Eiraman, governato con le stesse regole degli altri. Riguarda:
- la specifica;
- i Role Profile;
- i modelli di documento e la checklist del gate;
- gli strumenti, come la Vista del Manager;
- il sito che lo presenta.

Il progetto ha:
- un Manager umano, cioè il titolare del metodo;
- un Coordinatore AI;
- un mandato, un registro e una Vista del Manager.

Le proposte che arrivano dal ritorno al metodo entrano nel suo backlog come Work Package.

Gli agenti di questo progetto possono redigere e pre-valutare nuove versioni dei Role Profile, dei modelli e della checklist. La pubblicazione segue però le regole del §9: decide un revisore esperto del dominio, diverso dall'autore. Ogni modifica della specifica e ogni pubblicazione esterna, compresi il sito e i repository, sono Do del Manager umano. Un Role Profile pubblicato dal revisore esce dall'organizzazione solo con un Do.

## Registro delle modifiche

**Integrazione alla 0.3 (25 novembre 2026):** aggiunta tra gli artefatti di governo la High Level Architectural View (§8), una vista architetturale per il Manager umano senza dettagli tecnologici. La dashboard di avanzamento include l'albero dei Work Package con stime di costo e la pagina dei documenti del Manager umano. La forma degli artefatti di controllo è una decisione di progetto. Introdotta la Seniority Digitale (§4 bis, §9): ogni Role Profile ha un catalogo di task con livello e configurazione di attivazione, con ripiego a SD4. La gestione del metodo e dei Role Profile diventa essa stessa un progetto Eiraman (§11).

**0.3 (25 novembre 2026):** ripristinati dalle stesure di fondazione il modello operativo e la mappa dei framework (§1), le AI Squad e lo Scrum agentico (§4 bis), il Design Thinking affidato all'AI e il dettaglio di POC, design e planning (§5), DevSecOps e test (§6), l'architettura componibile (§6 bis), gli artefatti di governo (§8) e il contenuto completo dei Role Profile (§9).

**0.2 rispetto alla 0.1:** il registro originale cita identificativi interni del processo di lavoro ed è omesso in questa copia. La sintesi è in [HISTORY.md](../HISTORY.md).

## Riferimenti

TOGAF® è un marchio registrato di The Open Group. La Scrum Guide è opera di Ken Schwaber e Jeff Sutherland. Le fonti di ciascuna regola sono nella bibliografia pubblicata con la specifica.
