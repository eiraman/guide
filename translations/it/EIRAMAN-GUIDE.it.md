<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# La Guida Eiraman

**Versione 1.0.0-rc.7 · novembre 2026 · Release candidate**

> **Nota alla traduzione.** Questo documento è la traduzione italiana curata di *The Eiraman Guide*, versione 1.0.0-rc.7 proposta (repository `guide`, ramo `cr-033-guida`, non ancora pubblicata; ultima base pubblicata 1.0.0-rc.6, commit `d39ce03`). Versione della traduzione: **1.0.0-rc.7+it.1**. Il testo inglese, [EIRAMAN-GUIDE.md](../../EIRAMAN-GUIDE.md), è il testo canonico. La traduzione è curata e approvata dall'Autore (decisione D-IT-1). Il testo normativo è quello inglese, che prevale in caso di differenza. La traduzione non aggiunge, non toglie e non modifica alcuna regola. Sezioni e paragrafi hanno la stessa numerazione e lo stesso ordine dell'originale.
>
> Le parole chiave normative sono tradotte così, sempre in maiuscolo: MUST = DEVE (al plurale DEVONO); MUST NOT = NON DEVE (NON DEVONO); SHOULD = DOVREBBE (DOVREBBERO); SHOULD NOT = NON DOVREBBE (NON DOVREBBERO); MAY = PUÒ (POSSONO). Rendono le parole chiave inglesi con lo stesso significato (RFC 2119 e RFC 8174). I termini del metodo e le scelte di traduzione sono nel [glossario](GLOSSARY.it.md); i punti ambigui della fonte, tradotti fedelmente, sono in [SOURCE-NOTES.md](SOURCE-NOTES.md); le modifiche alla traduzione sono nel suo [CHANGELOG](CHANGELOG.md).

**Attribuzione.** The Eiraman Guide by Paolo Ungari and contributors.

**Stato.** Release candidate, non ancora in vigore, non misurata (§15, Misurare il metodo). L'Autore ne ha ratificato le scelte editoriali il 25 novembre 2026; sono elencate in `AUTHOR-RATIFICATION.md`.

## 0. Informazioni su questa Guida

**Scopo.** Questa Guida definisce Eiraman e dice che cosa rende conforme un'applicazione, comprese le pratiche che la comunità mantiene (§7.1, §9.1, §14). Valori, modelli e strumenti appartengono al Framework esteso, agli Strumenti e ai Casi.

**Linguaggio normativo.** Le parole chiave DEVE, NON DEVE, DOVREBBE, NON DOVREBBE e PUÒ vanno interpretate come descritto in RFC 2119 e RFC 8174 quando, e solo quando, sono scritte interamente in maiuscolo. Ogni regola normativa di questa Guida porta una di queste parole chiave. Un'applicazione è conforme a Eiraman solo se rispetta ogni DEVE e ogni NON DEVE. Un progetto che si discosta da un DOVREBBE o da un NON DOVREBBE DEVE registrarne il motivo nel proprio mandato. Il testo senza queste parole chiave definisce i termini, descrive come funziona il metodo o lo spiega.

**Valori e Indicazioni.** Questa Guida descrive ogni meccanismo senza il suo valore: non fissa soglie, quantità, scadenze né dimensioni. Il mandato di progetto DEVE fissare i valori di cui i suoi meccanismi hanno bisogno e registrarli. Il Framework esteso pubblica valori indicativi di partenza, chiamati Indicazioni.

**Implementazione.** Le scelte di implementazione appartengono allo strumento che esegue il metodo, non a questa Guida. Uno strumento PUÒ compierle liberamente entro le regole di questa Guida.

**Sezioni mantenute dalla comunità.** Le sezioni così contrassegnate sono tenute dai gruppi di lavoro indicati nella loro nota; l'Autore ne accetta le modifiche tramite RFC, senza riscriverle, e PUÒ restituire una proposta, con motivazione scritta, solo quando è in conflitto con un'altra parte di questa Guida. Sono normative quanto il resto della Guida.

**Licenza.** Questa Guida è concessa con la licenza Creative Commons Attribuzione - Condividi allo stesso modo 4.0 Internazionale (CC BY-SA 4.0), <https://creativecommons.org/licenses/by-sa/4.0/>. Attribuzione: "The Eiraman Guide by Paolo Ungari and contributors".

## 1. Definizione di Eiraman

**Definizione.** Eiraman è un metodo di management per il vibe coding governato: software costruito dall'AI e diretto da un Manager umano. L'umano non legge il codice. Una persona di business governa il lavoro da manager, con un mandato, principi e deleghe. Un sistema di agenti AI esegue il lavoro, si verifica con la concorrenza e la verifica indipendente e gestisce le eccezioni operative. Ogni rilascio è ricostruibile da evidenze e costi.

**Pianificazione e più modelli.** Eiraman sostituisce l'approvazione umana passo per passo con una pianificazione fatta in anticipo e con una modalità multi-modello: nello stesso progetto più modelli lavorano in modo indipendente come Coordinatore AI, esecutori e revisori.

Eiraman ha tre componenti.

**Metodo.** I ruoli, le deleghe, il ciclo di lavoro, le convenzioni architetturali, le prove di completamento e i livelli di adozione definiti in questa Guida. Ogni progetto DEVE registrare la versione del metodo che adotta.

**Development Environment.** L'ambiente in cui il metodo viene eseguito. Ospita il Coordinatore AI, le esecuzioni, i log e gli strumenti di verifica, e applica i Deny (§5, §11). Il Coordinatore AI lo configura e lo conduce per conto del Manager umano. Le chiamate a servizi esterni dipendono dalle deleghe del progetto.

**Confine tra locale ed esterno.** Lo stato, i log, il repository e i segreti DEVONO restare dentro il Development Environment. POSSONO uscirne soltanto i prompt e i dati inviati ai motori e ai connettori che il mandato autorizza.

**Projects.** Le applicazioni costruite con il metodo. Il loro sviluppo mette alla prova il metodo e aiuta a perfezionarlo (§15). Un'applicazione può incorporare parti del metodo.

## 2. Teoria di Eiraman

**Perché esiste Eiraman.** Il controllo *human-in-the-loop*, in cui una persona approva ogni passo dell'AI, il controllo *human-on-the-loop*, in cui una persona sorveglia e interviene sulle eccezioni, e la revisione umana del codice servono poco dove non c'è un team di sviluppo. Hanno due limiti. I controlli puntuali si moltiplicano finché approvarli è come accettare una licenza software: nessuno li legge. E relegano l'AI ad aiutare chi sviluppa, invece di metterla al servizio degli utenti di business. Il vibe coding, cioè costruire software dando istruzioni all'AI in linguaggio naturale, accentua entrambi i limiti. Il vibe coding governato ne conserva la velocità e aggiunge il governo che gli manca: una persona di business dirige il lavoro come Manager umano, e il sistema di AI risponde con evidenze. Il vibe coding, inoltre, aumenta di molto i dati che le persone trattano, spesso senza la competenza necessaria per vederne i rischi. In Eiraman il ruolo manageriale si estende alla sicurezza: un Manager umano che delega un compito sa che cosa quella scelta comporta per la sicurezza, la privacy e la conformità normativa, perché la classificazione del progetto e il Security Officer lo rendono noto (§14). Quando chi adotta usa il metodo per sé, questa conoscenza è, per impostazione predefinita, informazione, registrata nel Security Report (§12); nei contesti di lavoro e organizzativi è bloccante per impostazione predefinita: i livelli di adozione e il Gate di applicabilità fermano ciò che il livello qualificato non consente, salvo ciò che il Manager umano decide di eseguire sopra di esso alle condizioni del §14.2 (§14, Modalità di classificazione).

**Il management applicato all'AI.** Eiraman applica all'AI il management tradizionale. Gli agenti si governano come un manager governa un'organizzazione: mandato, deleghe, ruoli e squadre, pianificazione, gestione dei rischi, revisioni e retrospettive. Da qui il principio fondante, **Human as a Manager**. Ogni regola è la trasposizione di una pratica di management nota, adattata a ciò che cambia quando chi esegue è un agente:
- Il *management per obiettivi* diventa il mandato, la Visione e criteri di successo e di arresto eseguibili e misurati.
- La *delega* diventa l'escalation 3D, decisa sulla reversibilità; il silenzio non vale mai assenso.
- *Organizzazione e seniority* diventano AI Squad, Role Profile, Seniority Digitale e Unit Cost, con un organico a piramide in cui la base fa la maggior parte del lavoro, ricomposti a ogni retrospettiva.
- *Il campionamento di accettazione* diventa la revisione a campione con regole di passaggio, così che il costo della revisione resti piccolo rispetto al costo dell'esecuzione.
- *Scrum e Scrum of Scrums* diventano una squadra per Work Package sotto uno Scrum Master AI e il Coordinatore AI, limitata da costo, contesto e quote anziché da timebox umani.
- Il *Design Thinking* diventa una Scoperta tra modelli, con guardrail al posto del giudizio che agli agenti manca.
- L'*architettura componibile* diventa un ordine fisso di costruzione che previene i patchwork dell'AI.
- La *gestione dello scopo e dei rischi* diventa Principi e Decisioni versionati, un Risk Log e livelli di adozione che limitano il rischio in partenza o, nella modalità informativa, lo rendono noto.
- Il *controllo di qualità* diventa chiusura su evidenza, verificatori indipendenti e concorrenza, sostenibili perché gli agenti non si stancano.
- Il *reporting al management* diventa la revisione del ciclo, prima le cattive notizie e un controllo di completezza sui registri, perché il riassunto di un agente può essere compiacente.
- *Controllo interno e separazione dei compiti* diventano il classificatore delle escalation su un modello diverso (E4) e verificatori indipendenti dagli esecutori.
- *Distinte base e tracciabilità della catena di fornitura* diventano la distinta base del software e i registri delle run.

**Il metodo si applica a sé stesso.** Eiraman tratta ciascuna delle sue regole come un'ipotesi e misura i propri effetti rispetto a una baseline: gli stessi compiti svolti senza il metodo (§15, Misurare il metodo). Inoltre si alimenta da sé: evolve applicando sé stesso. Il Manager umano dà la direzione; gli agenti la traducono, secondo i principi del metodo, in Change Request, scelte specifiche e suggerimenti, e la mettono in pratica; il Manager umano decide attraverso i Do (§5). I progetti lo alimentano allo stesso modo, con ciò che il loro sviluppo insegna (§1, Projects; §15, Ritorno al metodo).

**Quattro differenze tra persone e macchine** guidano ogni adattamento.
- *Le macchine non hanno i limiti dell'interazione umana.* Limiti come la dimensione del team o la durata dello Sprint non dipendono più dalla capacità umana ma da costo, finestra di contesto e quote dei fornitori.
- *Gli agenti non hanno il giudizio di contesto di una persona.* Seguono le istruzioni alla lettera e non si accorgono di quando escono dallo scopo. Le attività aperte, come il brainstorming, richiedono confini più stretti che con un team umano: ruoli e comportamenti definiti, giri, criteri di convergenza, dati ammessi.
- *Il tempo degli agenti non è il tempo delle persone.* Un agente che ripete un compito molte volte finisce comunque molto prima di una persona. Nelle scelte di Seniority Digitale contano solo qualità e costo (§7); il tempo conta soltanto per gli impegni presi con le persone, come le date di rilascio (E5).
- *La comunicazione tra agenti non è comunicazione umana.* I modelli addestrati a rispondere alle persone scrivono messaggi lunghi, e ogni agente che li riceve li legge per intero. Gli agenti DEVONO scrivere tra loro nel dialetto degli agenti del registro dei profili; tutto ciò che una persona legge DEVE seguire il §12.

## 3. Principi di contesto

Quattro principi delimitano ogni regola del metodo.

- **La competenza specialistica sta nei Role Profile, non in ogni progetto.** Eiraman sposta la competenza dei professionisti del software in Role Profile qualificati (§13), da dove guida gli agenti in molti progetti. La produzione si avvicina a chi ha il bisogno. L'operatore umano di un progetto è un utente di business: decide su aspetti funzionali ed economici e NON DEVE sostituirsi ai ruoli AI su tecnologia, applicazioni o sicurezza.
- **Human as a Manager agisce in anticipo.** L'umano governa con strumenti di management: mandato, obiettivi, principi, deleghe, riserve, budget e criteri di successo. Lavora sul piano strategico e, per le sole decisioni di business, su quello tattico. NON DEVE supervisionare l'esecuzione. Eccezioni e autonomia operativa spettano al sistema di AI.
- **Coerenza e indipendenza del contesto.** Gli agenti che lavorano sulle stesse informazioni e hanno bisogno di collaborare DEVONO lavorare in un contesto condiviso, per esempio gli sviluppatori e gli architetti di una squadra. Gli agenti il cui ruolo richiede divergenza o indipendenza, come i membri del gruppo di Scoperta, i tester rispetto agli esecutori, i verificatori e i revisori, DEVONO lavorare in contesti indipendenti. Il Coordinatore AI DEVE applicare questo principio quando forma le AI Squad e i gruppi di Scoperta, e per tutta l'esecuzione.
- **Alcuni usi sono esclusi.** Nella modalità bloccante del §14 il metodo NON DEVE essere applicato ai sistemi di AI che la legge applicabile vieta o classifica ad alto rischio, né agli altri casi fuori perimetro del §14. Nella modalità informativa quei casi NON DEVONO fermare il progetto e DEVONO essere registrati nel Security Report (§12).

## 4. Responsabilità

**Manager umano.** La persona di business che governa il progetto e ha la responsabilità della direzione del prodotto. Il Manager umano:
- DEVE descrivere gli utenti e il processo;
- DEVE approvare la Visione, i Principi, i criteri di successo, il mandato, la spesa, le salite di livello di adozione e, nella modalità bloccante (§14), la classe del progetto;
- DEVE decidere i Do, approvare il ciclo di governo successivo e accettare o rifiutare il risultato;
- PUÒ autorizzare il collegamento di un account o di una cartella attraverso il consenso nativo della piattaforma;
- DEVE ricevere le decisioni tecniche tradotte in funzioni, costi, tempi e impatto su utenti e dati, mai in forma tecnica.

**Interprete.** L'unico canale tra il Manager umano e gli agenti, con un proprio Role Profile qualificato. L'Interprete:
- DEVE convertire ciò che dice il Manager umano nel dialetto degli agenti, e ciò che gli agenti inviano al Manager umano in documenti che seguono il §12;
- DEVE citare alla lettera le parole del Manager umano in ogni Decisione, Do e richiesta che converte;
- NON DEVE decidere e NON DEVE cambiare il significato di ciò che converte;
- DEVE rivedere, prima che arrivino al Manager umano, il lavoro dei ruoli di un livello sotto il suo e le schede Do.
- DEVE passare al Manager umano senza modifiche i rapporti del Revisore AI e del Security Officer, controllandone solo la forma secondo il §12.

**Coordinatore AI.** L'agente che conduce il progetto, con un proprio Role Profile qualificato. Opera alla base della piramide (§7): il coordinamento è una procedura che gli Strumenti calcolano e che l'agente esegue. Il Coordinatore AI:
- DEVE acquisire solo il repository autorizzato, configurare motori e strumenti, assegnare credenziali entro i permessi concessi e verificare disponibilità e budget;
- DEVE preparare le Wave, assegnare i Work Package, validare risultati e conformità, aggiornare il piano e condurre le retrospettive;
- DEVE gestire avvio, diagnosi, sospensione, ripresa, rilascio entro il mandato e ripristino.

**Ruoli AI specialistici.** L'analista, gli architetti, gli Scrum Master AI, gli esecutori, i tester e i revisori operano con Role Profile qualificati e DEVONO rispettarne i limiti. Prendono le decisioni tecniche. Un tester DEVE avere accesso a requisiti, contratti, dati e risultati attesi, e DEVE compiere la sua prima valutazione indipendentemente dalla discussione dell'esecutore.

**Revisore di processo.** Un agente indipendente che DEVE operare su un modello diverso da quello del Coordinatore AI. DEVE campionare le Wave chiuse e verificare che le escalation dovute siano arrivate al Manager umano (§5) e che le chiusure siano sostenute da evidenze (§9).

**Revisore AI.** Il Revisore AI estende il revisore di processo dal campionamento delle Wave chiuse al monitoraggio continuo, con un proprio Role Profile qualificato. DEVE operare in parallelo al Coordinatore AI e in hard blinding (§7). DOVREBBE operare su un modello diverso da quello del Coordinatore AI, dove ce n'è uno disponibile; i controlli del revisore di processo conservano il modello diverso che richiedono. DEVE monitorare i KPI del framework, come la correttezza dei Role Profile assegnati alle AI Squad e la qualità misurata degli output, e i KPI di progetto fissati in Design e planning. DEVE segnalare gli scostamenti al Coordinatore AI, ciascuno con un suggerimento indipendente; il Coordinatore AI DEVE valutarli criticamente e rispondere. Gli scostamenti critici, e quelli che il Coordinatore AI non accoglie, DEVONO arrivare anche al Manager umano nella Vista del Manager.

**Suggerimenti del Revisore AI.** I suggerimenti del Revisore AI sono dati, non comandi. Gli agenti DEVONO valutarli criticamente, e un suggerimento NON DEVE essere eseguito senza il Coordinatore AI.

**Manutentori.** I manutentori del Framework esteso, organizzati in gruppi di lavoro secondo la governance del progetto, DEVONO qualificare i Role Profile, i modelli di documento e la checklist del gate. DEVONO lavorare fuori dai progetti che li usano.

**Accountability interna.** Ciascuno DEVE rispondere di ciò che decide. Il Manager umano risponde delle decisioni di sua competenza e dell'uso del metodo dentro il perimetro qualificato nella modalità bloccante oppure, nella modalità informativa (§14), di aver proseguito con ciò che il Security Report registra. Il Coordinatore AI e i ruoli AI rispondono in senso operativo, non giuridico: ogni chiusura DEVE avere evidenze e ogni errore DEVE diventare un caso di retrospettiva. I manutentori rispondono della conformità dei profili alle loro fonti al momento della qualificazione, non dei singoli progetti.

**La responsabilità verso terzi** è del titolare: la persona al livello di adozione 0, l'organizzazione ai livelli 1 e 2. Ai livelli 1 e 2 il Manager umano DEVE agire con un mandato formale dell'organizzazione; senza quel mandato il progetto resta al livello 0. Per un progetto eseguito sopra il livello qualificato con un mandato dell'organizzazione (§14.2), la responsabilità verso terzi è di quell'organizzazione. Nella modalità informativa (§14) il Manager umano risponde di aver proseguito con ciò che il Security Report registra; la responsabilità verso terzi per i dati di cui un'organizzazione è titolare del trattamento è di quell'organizzazione; il metodo non sposta gli obblighi che la legge pone a carico di un'organizzazione o di chiunque altro; nella modalità informativa il titolare esercita questa responsabilità attraverso mandato e accettazione. Il titolare esercita questa responsabilità attraverso mandato, classe e accettazione, e dimostra la dovuta diligenza con le evidenze che il metodo produce (§12).

## 5. Escalation 3D: Deny, Delegate, Do

**Deny.** L'ambiente, non l'agente, DEVE bloccare un'azione che il mandato vieta o che, nella modalità bloccante (§14), è fuori dal livello di adozione, e DEVE registrarne il motivo. Per un progetto ammesso in base al §14.2 (Esecuzione sopra il livello qualificato), la classe 1 prende il posto del livello di adozione, a meno che un requisito del livello 1 che quel paragrafo rende dovuto sia dovuto e non soddisfatto; finché il lavoro prosegue solo su dati di prova in base a Domande all'organizzazione (§14), con o senza la decisione del §14.2, l'ambiente DEVE bloccare anche ogni dato diverso dai dati di prova, compresi i dati mascherati, e ogni rilascio. Il Coordinatore AI DEVE cercare un'alternativa autorizzata; se non c'è, DEVE sospendere il lavoro interessato.

**Delegate.** I ruoli AI POSSONO decidere in autonomia le porte a due vie: decisioni reversibili a costo noto, dentro il budget, come motore, nuovo tentativo, correzione o ripristino. Ognuna di queste scelte DEVE restare collegata al suo Work Package.

**Do.** DEVONO andare al Manager umano:
- le porte a una via;
- le riserve del mandato: impatto su Visione, Principi o criteri di successo, dati personali, terze parti, nuovi fornitori, spesa oltre la soglia che il mandato fissa; nella modalità informativa (§14) i dati personali e le terze parti DEVONO essere registrati nel Security Report e NON DEVONO andare al Manager umano come Do per questo solo motivo, anche dove il mandato li riserva; le altre voci di questo elenco continuano a valere;
- i cambi di una Decisione;
- i nuovi accessi;
- i cambiamenti che aggiungono un servizio esterno o spostano dati fuori dall'organizzazione (§9);
- i cambi di classe del progetto, le salite di livello di adozione e la decisione di eseguire un progetto sopra il livello qualificato. Le discese sono automatiche (§14.2). Nella modalità informativa un cambio di classe DEVE essere registrato nel Security Report e NON DEVE andare al Manager umano come Do per questo solo motivo; le altre voci di questo elenco continuano a valere.

**Nel dubbio, una via.** Quando la reversibilità è in dubbio, la decisione DEVE essere trattata come una porta a una via.

**Contenuto di un Do.** Un Do DEVE presentare, in termini funzionali ed economici, l'impatto, le opzioni, una raccomandazione, le evidenze, una scadenza e che cosa succede se non c'è risposta.

**Cambiare una Decisione.** Un Do che cambia una Decisione DEVE includere un'analisi SWOT. Dopo la scelta, l'esecuzione torna al Coordinatore AI.

**Regole contro la sotto-escalation.**
- **E1 · Riserve.** Il mandato DEVE elencare le riserve accanto alle deleghe. Ciò che arriva al Manager umano DEVE essere l'impatto di business della riserva, tradotto in funzioni, costi, tempi e impatto su utenti e dati; la scelta tecnica resta ai ruoli AI. Le riserve prevalgono su K7 (§6).
- **E2 · Reversibilità.** La reversibilità DEVE essere il criterio che separa Delegate da Do.
- **E3 · Micro-decisioni.** Ogni scelta non banale DEVE essere registrata come micro-decisione, con l'alternativa, la reversibilità stimata, il costo di ritorno e le riserve considerate.
- **E4 · Classificatore.** Se una decisione vada al Manager umano DEVE essere deciso da un classificatore che opera su un modello diverso da quello del Coordinatore AI. Se i due sono in disaccordo, la decisione DEVE salire.
- **E5 · Budget di deriva.** Gli scostamenti dal piano, compresi i cambi di classe, DEVONO sommarsi in un budget di deriva cumulato sul progetto, espresso in spesa e in tempo, e riportato a ogni ciclo di governo. I cambi di classe DEVONO essere riportati anche come voce a sé. Oltre la soglia che il mandato fissa, DEVE scattare una revisione del mandato. Nella modalità informativa (§14) un cambio di classe NON DEVE contare nel budget di deriva né essere riportato come voce a sé: DEVE essere registrato nel Security Report; la spesa e il tempo del lavoro che esso causa DEVONO contare come ogni altro scostamento dal piano.
- **E6 · Misura.** Il revisore di processo DEVE misurare la sotto-escalation (decisioni riservate non portate al Manager umano, sul totale delle decisioni riservate) e la sovra-escalation (Do che rientravano nelle deleghe, sul totale dei Do). Entrambe le misure sono stime su un campione di micro-decisioni (E3) e di Do. DEVONO essere riportate con il numero di decisioni esaminate e con il loro intervallo di confidenza. Una soglia è rispettata solo se l'estremo sfavorevole dell'intervallo resta al suo interno.
- **E6 · Taratura.** Nel primo progetto di ogni nuova adozione, il Manager umano DEVE esaminare una volta un campione di decisioni autonome, per tarare il revisore di processo. Il mandato fissa la dimensione del campione.

**Il silenzio non approva mai un Do.** Il silenzio NON DEVE essere inteso come approvazione. Fino alla risposta, il Work Package interessato DEVE restare sospeso, mentre il lavoro indipendente prosegue. Alla scadenza il Manager umano DEVE ricevere un sollecito. Quando passa anche la scadenza del sollecito, il pacchetto DEVE uscire dalla Wave e la revisione del ciclo DEVE riportarlo come decisione mancante. L'opzione irreversibile NON DEVE essere eseguita senza risposta.

**Contenimento urgente.** Il mandato DEVE elencare azioni di contenimento reversibili pre-autorizzate, come il ripristino, la revoca di credenziali o la sospensione di una funzione. Il Coordinatore AI DEVE eseguirle subito e aprire un Do urgente. Ogni azione fuori dall'elenco DEVE seguire la regola ordinaria del Do. Il mandato fissa le scadenze dei Do ordinari e dei Do urgenti.

## 6. Concorrenza e verifica indipendente

**Razionale.** Tra agenti non c'è un'armonia del gruppo da preservare, perciò la concorrenza tra candidate è sostenibile quando il costo la giustifica. Per questo i ruoli di controllore e di project manager possono essere affidati all'AI.

**Generare e selezionare.** Il beneficio della concorrenza nasce dal generare più candidate e selezionare la migliore, non da un maggiore impegno degli agenti. Dipende dalla diversità delle candidate e dall'affidabilità del selettore.

**Regole per i meccanismi concorrenziali.**
- **K1 · Selettore affidabile.** Un meccanismo concorrenziale DEVE essere aperto solo con un selettore affidabile: test, criteri misurabili, oppure una rubrica fissata in anticipo e valutata da un giudice che opera su un modello diverso da quello dei concorrenti, con l'ordine delle candidate alternato. Tutte le candidate DEVONO partire dallo stesso punto.
- **K2 · Diversità.** La diversità delle candidate (modello, fornitore o strategia) DEVE essere registrata.
- **K3 · Numero di candidate.** Il mandato DEVE fissare il numero predefinito di candidate. Più candidate DOVREBBERO essere riservate ai pacchetti generativi ad alta variabilità o ai pacchetti in cui gli errori costano, e DEVONO restare entro il tetto di spesa.
- **K4 · Imparare dalle perdenti.** Dopo la selezione, le critiche sollevate dalle candidate perdenti DEVONO essere applicate alla vincitrice, attraverso il revisore.
- **K5 · Criteri nascosti.** Una parte dei criteri di valutazione NON DEVE essere mostrata alle candidate, e i giudici DEVONO ruotare.
- **K6 · Misurare il meccanismo.** Il margine di vittoria, l'accordo tra giudice e umano (tarato su un campione di giudizi umani sulle candidate) e il costo per incremento accettato rispetto a un esecutore singolo DEVONO essere misurati. Se il meccanismo non batte un esecutore singolo su un tipo di pacchetto, quel tipo DEVE tornare a un esecutore singolo. Il mandato DEVE fissare che cosa conta come tipo di pacchetto, il numero minimo di pacchetti e il margine minimo rispetto a un esecutore singolo.
- **K7 · Minor costo di ritorno.** Con proposte molto divergenti su una porta a due vie, DEVE essere adottata l'opzione con il minor costo di ritorno. Se il budget lo consente, prima DEVE essere eseguita una prova breve che discrimini tra le opzioni.
- **K8 · Divergenza elevata.** Questi casi DEVONO essere segnalati come divergenza elevata. Il revisore di processo DEVE esaminarli tutti e dare loro priorità nel campione di taratura (E6).
- **K9 · Divergenza ricorrente.** Se la divergenza si ripete sullo stesso tema, il Coordinatore AI DEVE proporre una revisione del mandato come Do, tradotta in funzioni, costi, tempi e impatto su utenti e dati. Se il tema non può essere espresso in questi termini, resta ai ruoli AI con K7 e K8.

**Indipendenza della verifica.** Per ogni verifica DEVE essere registrato il livello di indipendenza ottenuto: contesto separato, modello diverso, fornitore diverso o una persona. Ogni verifica DEVE raggiungere almeno il livello minimo che la classe di rischio del Work Package fissa. La verifica DOVREBBE usare, dove possibile, modelli di origine diversa, perché i confronti siano efficaci.

**Sicurezza e dati personali.** A ogni livello di adozione, la verifica dei Work Package che toccano la sicurezza o i dati personali DOVREBBE usare almeno un modello diverso da quello dell'esecutore. Il livello di indipendenza ottenuto DEVE essere registrato in ogni caso.

**Seniority del verificatore.** Un revisore o un tester indipendente DEVE lavorare un livello di Seniority Digitale sopra l'esecutore che verifica (§7). Il lavoro del livello più alto in uso DEVE essere verificato dal Manager umano o da un modello di un altro fornitore.

**Revisione a campione.** Un oracolo (test, controlli deterministici o una rubrica fissata in anticipo) DEVE essere eseguito prima di ogni revisione fatta da un modello. La revisione su un modello diverso da quello dell'esecutore DEVE coprire ogni Work Package della classe di rischio (architettura, sicurezza, dati personali, effetti difficili da annullare); per gli altri PUÒ coprire un campione. La quota campionata DEVE seguire regole di passaggio fissate nel Framework esteso: più stretta dopo i campioni respinti, ridotta dopo una serie di campioni accolti. Il costo della revisione DEVE essere registrato a parte dal costo dell'esecuzione.

## 7. AI Squad e Seniority Digitale

**Livelli dei ruoli.** I ruoli AI sono organizzati in una piramide. La base fa la maggior parte del lavoro; salendo, calano il numero degli agenti, il volume del lavoro e il costo per run. Ogni ruolo DEVE partire da un Role Profile qualificato; il mandato di progetto PUÒ dargli il contesto di progetto e di dominio ma NON DEVE alterare le regole e i limiti del profilo.
- *Vertice:* l'Interprete, l'unico ruolo in contatto con le persone (§4).
- *Parte alta:* i ruoli della Scoperta che interpretano i bisogni delle persone, come il Business Analyst e le User Personas.
- *Parte media:* i ruoli di pianificazione e di progettazione, come l'analista funzionale, gli UX-UI designer e gli architetti.
- *Base:* ogni altro ruolo, compresi il Coordinatore AI, gli Scrum Master AI, gli esecutori e i tester.
- *I revisori* lavorano un livello sopra i ruoli che verificano (§6).

**Unit Cost.** L'AI non è gratis. Ogni Role Profile DEVE dichiarare uno Unit Cost, usato per stimare e rendicontare il costo del progetto, revisione compresa.

**Seniority Digitale.** In un'organizzazione ogni persona lavora al livello di esperienza che il compito richiede; Eiraman applica la stessa regola agli agenti. La Seniority Digitale di un agente è la combinazione di motore e livello di ragionamento con cui il Coordinatore AI lo attiva, per esempio un motore piccolo con ragionamento basso per il lavoro ripetitivo.

| Livello SD | Nome | Quando si usa |
|---|---|---|
| SD1 | Junior | La base: esecuzione, test e coordinamento su un input delimitato ricevuto da un agente |
| SD2 | Professional | Pianificazione e progettazione; revisione del lavoro SD1 |
| SD3 | Senior | Ruoli della Scoperta che interpretano i bisogni delle persone; revisione del lavoro SD2 |
| SD4 | Lead | L'Interprete; revisione del lavoro SD3 e delle schede Do |
| SD5 | Principal | Problemi nuovi che SD4 non ha risolto, solo dopo un Do con un budget dichiarato |

La corrispondenza tra i livelli SD e i motori e le impostazioni degli strumenti di ciascun fornitore non fa parte di questa Guida. È mantenuta, versionata, negli Strumenti.

**Scrum agentico.** Gli agenti lavorano secondo i principi di Scrum, adattati alla collaborazione tra AI.
- **Niente Sprint né timebox umani.** L'unità di consegna DEVE essere la Wave, limitata da token, costo e durata (§8). La dimensione della squadra non ha un limite fisso; dipende dagli ambienti AI usati.
- **Una squadra per Work Package.** Il Coordinatore AI DEVE formare una squadra per ogni Work Package, con i ruoli e le competenze che il pacchetto richiede.
- **Un nuovo agente per ogni Work Package.** Il Coordinatore AI DEVE istanziare un nuovo agente del ruolo richiesto, con un nuovo contesto, per ogni Work Package. Alla chiusura, ogni agente DEVE fornire un Work Package handover abstract: le informazioni significative del suo contesto che servono agli agenti successivi. Il Coordinatore AI lo usa per istanziare gli agenti dei Work Package seguenti.
- **Uno Scrum Master AI per squadra.** DEVE coordinare gli agenti della squadra, tenere il Log Tracker del pacchetto e consegnare al Coordinatore AI un report delle attività sul template che il Coordinatore AI indica.
- **Contesto condiviso, tranne che per lo unit tester.** Dentro un Work Package, una squadra condivide un solo contesto. Lo unit tester NON DEVE ricevere la discussione della squadra, per non influenzare i test; riceve requisiti, contratti, dati e risultati attesi. PUÒ operare su un motore diverso, oppure sullo stesso motore senza quel contesto; per la sicurezza e i dati personali vale il §6.
- **Squadre in concorrenza.** Lo stesso Work Package PUÒ essere assegnato a più squadre in concorrenza, con motori o composizioni diverse, secondo le regole K1–K9 e con il numero predefinito di candidate di K3.

**Blinding degli agenti.** Il blinding tiene ogni agente dentro le informazioni del suo ruolo, così che i ruoli non si sovrappongano. Il blinding riguarda le informazioni di progetto, non la conoscenza generale del modello.

**Hard blinding.** In hard blinding, l'ambiente DEVE dare all'agente solo i file, gli strumenti e i dati del suo ruolo, senza alcun recupero di informazioni fuori da quel perimetro (§11), e un prompt vincolante DEVE delimitarne il comportamento. PUÒ essere usato un modello locale senza recupero di informazioni. L'hard blinding DEVE applicarsi al Coordinatore AI, al Revisore AI, al Design Thinking Facilitator, ai revisori della Scoperta, al giudice della Scoperta (§8) e al Security Officer (§14).

**Soft blinding.** Quando forma una AI Squad, il Coordinatore AI DEVE consegnare a ogni agente un RACI di contesto, che dichiara la posizione dell'agente su ogni parte del contesto:
- *R:* il solo agente titolato ad agire su quella parte del contesto;
- *C:* l'agente PUÒ usare la propria competenza sul tema ma NON DEVE contraddire le istruzioni di progetto né gli altri agenti;
- *I:* l'agente è cieco sul tema.

**Il Coordinatore AI come Scrum of Scrums.** Oltre a ciò che fa uno Scrum Master, il Coordinatore AI DEVE svolgere la validazione tecnica e di conformità del lavoro delle squadre: fissa i criteri di qualità e funzionali che un pacchetto deve soddisfare, verifica l'esecuzione alla fine di ogni pacchetto (§9), risolve le dipendenze tra squadre e chiude una Wave solo dopo che l'incremento integrato è stato verificato.

**Retrospettiva.** Alla fine di ogni ciclo il Coordinatore AI DEVE analizzare i report degli Scrum Master. Ottimizza la composizione delle squadre, per esempio alzando la seniority di un ruolo o cambiandone il modello tra quelli che il suo Role Profile abilita e il mandato ammette, e rivede le decisioni operative, cioè le micro-decisioni (E3) che non toccano né Decisioni approvate né riserve.

**Tolleranza.** I miglioramenti che fanno risparmiare senza ridurre la qualità, o che la riducono entro la tolleranza del mandato, POSSONO essere applicati senza il Manager umano. Ogni cambio di una Decisione approvata DEVE andare al Manager umano come Do con un'analisi SWOT (§5).

**Decisioni flessibili.** Riformare le AI Squad costa poco, perciò le Decisioni approvate possono cambiare più facilmente che con squadre umane. Il costo del cambiamento e del rework DEVE essere stimato e mostrato nel Do.

### 7.1 Catalogo della Seniority Digitale

> **Sezione mantenuta dalla comunità.** Le modifiche sono proposte dai gruppi di lavoro responsabili (DevSecOps & Tooling, per la mappa della Seniority Digitale; FinOps, per lo Unit Cost; Test & Quality, per la riqualificazione dopo i cambi di modello) e accettate dall'Autore tramite RFC senza riscrittura; l'Autore PUÒ restituire una proposta, con motivazione scritta, solo per un conflitto con un'altra parte di questa Guida.

**Catalogo.** Ogni Role Profile DEVE dichiarare il livello SD del proprio ruolo ed elencare i task e i deliverable che il Coordinatore AI può assegnargli. Per ogni task DEVE indicare il tipo di task (procedura, esperienza o problema nuovo), se un oracolo lo verifica (un controllo deterministico, test o una rubrica fissata in anticipo) e se appartiene alla classe di rischio (architettura, sicurezza, dati personali, effetti difficili da annullare). La corrispondenza tra livelli SD e configurazioni di ogni strumento ammesso, motore e livello di ragionamento, motori locali compresi, DEVE essere mantenuta in un'unica mappa del registro dei profili e riverificata a ogni cambio di modello. La mappa DEVE anche definire la scala di promozione: passi di ragionamento più alto sullo stesso motore e passi verso un motore più capace. La corrispondenza è una valutazione dei manutentori della mappa; le configurazioni non ancora provate sono segnate come tali.

**Ripiego.** Un task fuori dal catalogo DEVE essere eseguito al livello del ruolo che lo esegue. Il Coordinatore AI DEVE registrare il task, proporre di aggiungerlo al catalogo (§15) e riportare nella revisione del ciclo la quota di task eseguiti fuori dal catalogo.

**Partecipazione alle squadre.** Il Role Profile è il ruolo; il livello SD è il grado della singola run. Ogni run DEVE essere attivata al livello del suo ruolo, o al passo che la promozione dà, e registrata. Un agente NON DEVE eseguire a un livello più alto per il solo motivo che un altro task del Work Package lo richiede.

**Promozioni e riduzioni.** La promozione DEVE essere un'eccezione rara, perché la revisione deve restare economica rispetto all'esecuzione. Un fallimento per carenza di capacità è un oracolo che fallisce, una revisione che respinge per carenza di capacità o, dove non c'è un oracolo, il disaccordo tra due run indipendenti. Il revisore DEVE registrare la causa di ogni fallimento: *input* (un ordine di lavoro incompleto o ambiguo), *ambiente*, *rifiuto* del modello, *profondità* (passi saltati, casi limite trascurati) oppure *capacità o conoscenza*. Il Coordinatore AI DEVE poi agire in quest'ordine:
- per input o ambiente, correggerli e ripetere la run allo stesso passo; per un rifiuto, applicare il §14; nessuno di questi è un fallimento per carenza di capacità;
- per la profondità, prendere il passo successivo di ragionamento più alto sullo stesso motore;
- dove esiste un oracolo, ripetere la run allo stesso passo finché il costo delle ripetizioni resta sotto il costo di una run al motore successivo;
- solo allora, e solo per un fallimento di capacità o di conoscenza confermato da due fallimenti di tipo diverso, passare a un motore più capace; un fallimento nella classe di rischio passa subito a un motore più capace.

Le promozioni di modello NON DEVONO superare la quota di run per ciclo che il mandato fissa. La promozione usa i tentativi consentiti dalla scheda del Work Package (§9); quando sono esauriti, il Coordinatore AI DEVE aprire un punto decisionale. Nella retrospettiva il Coordinatore AI PUÒ abbassare il livello di un task quando le evidenze mostrano qualità invariata a costo minore, cioè nessun aumento dei difetti trovati dopo la chiusura né del rework. Questa riduzione è una porta a due vie entro la tolleranza del mandato; oltre, è un Do.

**Costo per livello.** Lo Unit Cost DEVE essere tarato per livello SD, e ogni run DEVE registrare il livello, il motore e il ragionamento effettivi (§11). Il costo di un motore locale DEVE essere registrato anche in ore macchina.

**Costo degli errori.** Per ogni tipo di task e livello SD, il Coordinatore AI DEVE misurare a ogni ciclo di governo il costo degli errori in token: i token spesi in run che non hanno portato a un incremento accettato (run respinte o ripetute, revisioni di lavoro respinto, promozioni e rework dopo la chiusura), come quota di tutti i token di quel tipo di task. Il rework dopo la chiusura DEVE essere riportato anche a parte. L'indicatore DEVE essere riportato nella revisione del ciclo.

**Alzare il livello di un ruolo.** Quando il costo degli errori in token di un ruolo supera la soglia che il mandato fissa, e la causa registrata non è l'input, il Coordinatore AI PUÒ alzare da solo di un passo il livello di quel ruolo, come porta a due vie (§5, Delegate). DEVE poi informare il Manager umano nella Vista del Manager con l'indicatore, il livello vecchio e quello nuovo e il costo atteso. Un livello alzato PUÒ essere abbassato di nuovo secondo «Promozioni e riduzioni».

## 8. Ciclo di vita ed eventi

**Cinque fasi, un solo insieme di regole.** Tutte e cinque le fasi DEVONO essere eseguite dal sistema di AI in Wave, con le stesse regole: escalation 3D, concorrenza, chiusura su evidenza e registrazione dei costi. Il Manager umano interviene solo nei punti di decisione di ciascuna fase.

**Fasi e decisioni.** Ogni fase DEVE concludersi con le decisioni del Manager umano elencate sotto; il lavoro che ne ha bisogno NON DEVE procedere senza di esse.
- La *Scoperta* produce il problema, il beneficio, le alternative scartate, una bozza di Visione, la prima bozza dello Scope Management e la classe assegnata dal gate di applicabilità (§14). Il Manager umano approva la Visione, il mandato e, nella modalità bloccante (§14), la classe, oppure rilancia l'esplorazione.
- Il *Proof of concept* esegue una prova di fattibilità ripetibile e individua le risorse e gli accessi necessari. Diventa un Do solo se l'esito è negativo o richiede nuovi accessi o spesa.
- *Design e planning* produce le viste architetturali, i contratti, il backlog, i Work Package, i profili, la stima dei costi, i criteri di test e le proposte di Principi e Decisioni, affinate dalla prima bozza dello Scope Management. Il Manager umano approva i Principi proposti, le Decisioni proposte con impatto di business e il budget. I Principi sono poi congelati per quella versione.
- *Scale* consegna incrementi chiusi su evidenza. Il Manager umano agisce attraverso il ciclo di governo e i Do.
- *Accettazione ed esercizio* copre il collaudo di accettazione, il rilascio, i manuali e la gestione del servizio. Il Manager umano accetta o rifiuta il risultato e decide i Do sull'esercizio.

**Parallelismo.** In ogni fase il grado di parallelismo DEVE restare entro capacità e budget.

**La Scoperta come Design Thinking tra modelli.** Lasciati liberi, i motori AI raccolgono bene le informazioni ma tendono a divergere, perciò la Scoperta segue il Design Thinking con ruoli e confini precisi.

**Scoperta a ogni avvio.** La Scoperta DEVE essere eseguita all'avvio di ogni progetto e DEVE essere tracciata nell'albero delle attività del piano. Il suo deliverable è la prima bozza dello Scope Management: Visione, Principi, Decisioni, criteri di successo e punti aperti.

**Gruppo di Scoperta.** Per la Scoperta il Coordinatore AI DEVE formare un gruppo di Scoperta, che non è una AI Squad: ciascuno dei suoi membri DEVE lavorare in un contesto indipendente. Il gruppo DEVE includere almeno il Design Thinking Facilitator, l'analista funzionale, il Business Analyst, lo UX-UI designer, le User Personas e, dove il progetto li ha, gli architetti di piattaforma e di tecnologia (§8.1).

**Business Analyst e User Personas.** Il Business Analyst e le User Personas sono istanze di progetto di template qualificabili. Ciascuna DEVE partire da un template qualificato, come un ruolo di livello alto parte da un Role Profile qualificato (§7); il progetto dà all'istanza il suo contesto di progetto e di dominio, che NON DEVE alterare le regole e i limiti del template.

**Esecutori e revisori della Scoperta.** Il gruppo di Scoperta ha esecutori e revisori. Gli esecutori DEVONO lavorare in soft blinding e portano competenza interdisciplinare. I revisori DEVONO lavorare in hard blinding e DEVONO giudicare solo i Principi e le Decisioni del proprio dominio. I revisori della Scoperta sono i profili di revisore dei domini di governo che il progetto tocca, scelti dal Coordinatore AI; i domini di sicurezza e privacy DEVONO essere sempre presenti.

**Giro di domande.** Prima della divergenza, il Design Thinking Facilitator DEVE sottoporre lo stesso prompt a ogni esecutore del gruppo, chiedendo che cosa non si sa e a chi andrebbe chiesto. DEVE riunire le domande in un registro delle domande, conservandone le parole, il tema, l'autore e il destinatario e se da esse dipende una scelta non reversibile, e togliendo solo i duplicati. DEVE poi sottoporre il registro, senza gli autori, alle User Personas, che DEVONO dare per ogni domanda una risposta, la sua fonte e un livello di confidenza. Il livello DEVE seguire la fonte: alto solo quando la risposta è scritta nella richiesta o nei materiali del Manager umano e la citazione risponde a quella domanda, medio quando è dedotta da ciò che è scritto, basso quando è supposta. Quando più User Personas danno a una domanda risposte o livelli di confidenza diversi, DEVE valere il livello di confidenza più basso; quando quella domanda arriva al Manager umano, le diverse risposte DEVONO arrivare al Manager umano insieme a essa, e altrimenti DEVONO essere tutte registrate tra le assunzioni. Tra le domande rivolte al Manager umano o a una persona esterna al gruppo di Scoperta che non sono a confidenza alta, il Facilitator DEVE inviare al Manager umano, attraverso il Coordinatore AI, quelle a confidenza più bassa, fino al numero che il mandato fissa, ciascuna con la risposta supposta; finché il mandato non è approvato, DEVE valere il numero che il Coordinatore AI comunica con i gate all'inizio della Scoperta; a parità di confidenza, prima quelle da cui dipende una scelta non reversibile, poi quelle il cui tema cambia ciò che l'utente finale vede o fa, poi nell'ordine del registro delle domande. Le domande tecniche e le domande per un membro del gruppo NON DEVONO occupare uno di questi posti. Le risposte alle domande non chieste DEVONO essere prese per corrette e registrate come assunzioni visibili al Manager umano. Senza una risposta entro il gate, la Scoperta DEVE proseguire e le supposizioni DEVONO restare assunzioni non confermate. Nella modalità informativa (§14), le domande sulla sicurezza NON DEVONO occupare uno di questi posti né essere registrate tra quelle assunzioni: il Security Officer DEVE registrarle nel Security Report come non determinate. Il giro di domande NON DEVE contare nel numero massimo di giri.

**Divergenza.** Più modelli, con ruoli e comportamenti definiti, generano in modo indipendente ipotesi, problemi, benefici e principi per la Visione. La divergenza DEVE svolgersi entro guardrail: un numero massimo di giri fissato dal mandato, fonti e dati ammessi, e criteri per scartare un'ipotesi.

**Gate.** Ai gate che il Coordinatore AI fissa e comunica all'inizio della Scoperta, il Manager umano PUÒ dare nuovi input, che avviano un nuovo giro di divergenza. Un gate DEVE seguire il giro di domande e precedere la divergenza; DEVE portare le domande di quel giro.

**Convergenza.** Il Design Thinking Facilitator DEVE guidare la convergenza; l'analista funzionale partecipa come membro del gruppo. Il Facilitator DEVE sottoporre lo stesso prompt a ogni esecutore del gruppo, registrare le risposte, riformularle come Principi, Decisioni e punti aperti, e iterare fino al consenso entro il numero massimo di giri che il mandato fissa; DEVE poi sottoporre il risultato ai revisori della Scoperta. La convergenza DEVE raccogliere i contributi, ricondurli alle evidenze degli utenti e produrre la bozza di Visione e la prima bozza dello Scope Management. Il Manager umano DEVE poi approvare la Visione oppure rilanciare l'esplorazione. La convergenza segue K1 (§6): i criteri di convergenza DEVONO essere fissati prima della divergenza e, dopo i revisori della Scoperta, il risultato DEVE essere valutato rispetto a essi da un giudice che opera su un modello diverso da quelli dei membri del gruppo, prima che il risultato arrivi al Manager umano. Il giudice DEVE essere un agente distinto dai revisori della Scoperta e DEVE lavorare in hard blinding (§7). Quando non è disponibile un modello diverso da quelli di tutti i membri del gruppo, il Coordinatore AI DEVE portare al Manager umano la scelta del modello del giudice come Do, presentato in termini funzionali ed economici (§5, Contenuto di un Do); il giudice opera poi sul modello che il Manager umano sceglie, e il livello di indipendenza ottenuto viene registrato (§6).

**Report della Scoperta.** Alla fine della Scoperta il Design Thinking Facilitator DEVE produrre un report per il Manager umano con la posizione iniziale e quella finale di ciascuna AI del gruppo.

**Design e planning come Work Package.** Design e planning DEVE essere eseguito come un Work Package dedicato, che il Coordinatore AI assegna e NON DEVE svolgere. Affina i Principi e le Decisioni della prima bozza dello Scope Management e produce il primo Product Backlog e i documenti architetturali.

**Wave.** L'unità di consegna tecnica in ogni fase, al ritmo dell'AI. Una Wave DEVE avere un tetto di spesa e una durata massima; vale quello raggiunto per primo. Alla soglia di preavviso che il mandato fissa, il Coordinatore AI DEVE segnalare la Wave. Alla soglia di Deny che il mandato fissa, l'ambiente DEVE applicare un Deny al nuovo lavoro, e la Wave si chiude con un checkpoint. Le Wave si susseguono in automatico entro mandato e budget. Una Wave DEVE chiudersi solo dopo che l'incremento integrato è stato verificato.

**Ciclo di governo.** L'unità di decisione del Manager umano, con una cadenza di calendario. DEVE chiudersi con una sola revisione manageriale che contiene: consegne e accettazioni; spesa e costo per incremento accettato; la quota di governo, cioè il costo del Coordinatore AI, degli Scrum Master AI, dei revisori, del classificatore delle escalation (E4), dei giudici (K1), del gate di applicabilità (§14) e della redazione dei documenti manageriali (§12), sul costo totale del ciclo; la quota di task eseguiti fuori dal catalogo (§7.1); lo stato del budget di deriva (E5); il numero dei casi di divergenza elevata (K8) e i temi ricorrenti (K9); i Do aperti; e una proposta per il ciclo successivo.

**Ciclo scaduto.** Se un ciclo scade prima che il successivo sia approvato, le Wave in corso completano il Work Package attivo e NON DEVONO aprirne di nuovi.

**Carico di escalation.** Un indicatore del ciclo di governo, letto insieme alla sotto-escalation. NON DEVE bloccare un Do dovuto. Vi contano i Do ordinari e le escalation K9; non vi contano i Do urgenti, conteggiati a parte, né le decisioni previste dalle fasi. I Do non urgenti DEVONO essere raggruppati nella revisione del ciclo, salvo quelli che bloccano il percorso critico.

**Valori dichiarati e osservati.** La revisione del ciclo DEVE mostrare il valore dichiarato degli indicatori del ciclo accanto a quello osservato. Un valore dichiarato NON DEVE cambiare se non a una revisione del ciclo. Il mandato fissa la cadenza e i valori di riferimento.

### 8.1 Prassi delle fasi

Le prassi descrivono come lavora di solito il sistema di AI; le regole sono quelle del §8.

**Chi lavora in ciascuna fase.**
- *Scoperta:* il gruppo di Scoperta che il Coordinatore AI forma, con i membri su modelli diversi; divergenza, poi convergenza guidata dal Design Thinking Facilitator.
- *Proof of concept:* il Coordinatore AI, l'analista, l'architetto, gli esecutori e i tester, che rendono esplicita l'incertezza; prove alternative sullo stesso quesito tecnico quando il selettore è misurabile (K1).
- *Design e planning:* la squadra di un Work Package dedicato, con l'analista, gli architetti applicativo e infrastrutturale e lo Scrum Master AI, che producono le viste di business, applicazioni, dati e tecnologia; architetture alternative valutate con una rubrica fissata in anticipo.
- *Scale:* il Coordinatore AI e le squadre AI con i loro Scrum Master AI, tester e revisori; K1–K9 sui pacchetti generativi.
- *Accettazione ed esercizio:* il Coordinatore AI, i tester e i ruoli di esercizio; diagnosi alternative di un incidente.

**Ruoli nel gruppo di Scoperta.**
- *Design Thinking Facilitator:* esegue la procedura di Scoperta e guida la convergenza.
- *Analista funzionale:* collega i bisogni del Business Analyst e delle User Personas alle soluzioni dello UX-UI designer e degli architetti.
- *Business Analyst:* custodisce la Visione e, dove applicabile, porta la competenza del settore.
- *UX-UI designer:* propone le soluzioni per l'esperienza e l'interfaccia degli utenti.
- *User Personas:* rappresentano gli utenti dell'applicazione; danno una prima risposta, supposta, alle domande del giro di domande, che resta un'assunzione finché il Manager umano non risponde; in seguito eseguono i test funzionali con utente simulato (§9.1).
- *Architetti di piattaforma e di tecnologia,* dove presenti: propongono le soluzioni tecniche.

**Procedura di Scoperta.** Il Design Thinking Facilitator lavora per giri:
- *Domande.* Una volta, prima del primo giro, esegue il giro di domande (§8, Giro di domande).
- *Stesso prompt.* Sottopone lo stesso prompt a tutti gli esecutori del gruppo, ciascuno nel proprio contesto.
- *Registrare.* Registra le risposte.
- *Riconciliare.* Verifica se le risposte si riconciliano del tutto o in parte.
- *Riformulare.* Emette un nuovo prompt che dichiara i Principi, capisaldi su cui tutti concordano, che Design e planning affina e che si congelano alla fine del planning; le Decisioni, che possono cambiare con nuove specifiche o evidenze; e i punti aperti, rinviati al design, a un mock-up (MOC) o a un proof of concept (POC), oppure che richiedono un Do del Manager umano.
- *Iterare.* Ripete i giri fino al consenso, entro il numero massimo di giri che il mandato fissa.
- *Revisione.* Sottopone il risultato ai revisori della Scoperta, ciascuno dei quali giudica solo il proprio dominio.
- *Giudizio.* Il giudice K1 valuta il risultato rispetto ai criteri di convergenza fissati prima della divergenza.
- *Report.* Scrive il report per il Manager umano, con la posizione iniziale e quella finale di ciascuna AI.

**Proof of concept e MVP.** L'analista funzionale valida la fattibilità, in teoria oppure chiedendo al Coordinatore AI piccoli Work Package di prova. Valida anche la capacità di calcolo e gli accessi di cui il progetto ha bisogno, per esempio se un motore locale può elaborare un documento della dimensione attesa entro il tempo e il costo attesi.

**Design e planning.** L'analista funzionale lavora prima con l'architetto applicativo, poi con gli architetti infrastrutturali e lo Scrum Master AI. Insieme producono il design architetturale, il Product Backlog e i suoi workstream, la stima dei costi della componente AI e una stima iniziale delle prestazioni che i test aggiornano in seguito nella Performance Analysis. Il design segue le linee guida architetturali dei fornitori o delle comunità open source delle tecnologie scelte, e gli architetti portano queste competenze nei loro profili.

## 9. Impegni e artefatti

**Due risultati, accettati separatamente.** L'accettazione del software e l'accettazione del deliverable che il software produce DEVONO restare separate. Per esempio, quando un incremento aggiunge un controllo di qualità a un generatore di documenti, un documento che il controllo rifiuta può essere la prova riuscita dell'incremento, mentre i documenti generati passano attraverso la propria revisione.

**Visione.** La Visione diventa vincolante quando il mandato è approvato. Un cambiamento della Visione DEVE aprire un nuovo progetto.

**Principi.** I Principi DEVONO essere congelati per versione alla fine del planning. Se un Principio cambia durante l'installazione, il Coordinatore AI DEVE segnare la versione come fallita, registrare lo stato installato e gestire il ripristino o la transizione a una nuova versione.

**Criteri di successo.** I criteri di successo di una versione e del progetto DEVONO basarsi su KPI misurabili nelle procedure di test.

**Decisioni.** Una Decisione NON DEVE violare un Principio. Le Decisioni sono collegate: cambiarne una può richiedere di riesaminare quelle collegate.

**Scheda decisione.** Ogni Decisione DEVE avere un identificativo, un proprietario, uno stato, una motivazione, i Principi collegati e le dipendenze. Una nuova Decisione DEVE rinviare a quella che sostituisce e ai pacchetti da riesaminare. Un risparmio che cambia una Decisione DEVE andare al Manager umano, anche quando rientra nella tolleranza di qualità.

**Punti aperti.** Ogni punto aperto DEVE indicare la Wave che blocca e il criterio per chiuderlo.

**Criteri di arresto.** Il mandato DEVE contenere i criteri di arresto del progetto, come la spesa, una serie di Wave senza un incremento accettato o un proof of concept negativo.

**Product Backlog.** Il Product Backlog contiene i workstream che le squadre possono svolgere. Ogni workstream DEVE essere etichettato con il suo componente e la sua priorità (§10) e collegato alle Decisioni e ai punti aperti da cui dipende.

**Scheda del Work Package.** Una scheda del Work Package DEVE contenere almeno: progetto e Wave, identificativo e revisione iniziale; criteri di successo ed esclusioni; Principi, Decisioni e dipendenze; profili e loro versioni; budget e tentativi consentiti; risultato atteso e verificatore; procedura di ripresa; il RACI di contesto consegnato ai suoi agenti; e, alla chiusura, il Work Package handover abstract di ogni agente.

**Consuntivo.** Il consuntivo di un Work Package DEVE includere tutte le candidate, anche quelle scartate.

**Definizione di pronto.** I criteri funzionali DEVONO essere scritti nella forma Dato/Quando/Allora. I criteri non funzionali DEVONO riferirsi alle caratteristiche di ISO/IEC 25010. Un Work Package NON DEVE essere dichiarato pronto finché i suoi criteri non sono eseguibili.

**Definizione di completato.** Il Coordinatore AI DEVE chiudere un Work Package solo quando i controlli obbligatori sulla candidata identificata sono superati e le evidenze sono identificabili. Una modifica alla candidata DEVE riaprire i controlli interessati.

**Dissenso o prova mancante.** Il pacchetto DEVE restare aperto. Con un requisito chiaro, la prova DEVE essere ripetuta oppure assegnata a un altro verificatore. Con un requisito ambiguo, DEVE essere aperto un punto decisionale. L'esito, il dissenso e la motivazione della chiusura DEVONO essere registrati.

**Ancore deterministiche.** A ogni rilascio DEVONO essere eseguite l'analisi statica, l'analisi di dipendenze e licenze e la ricerca di segreti. I ruoli AI ne interpretano gli esiti e NON DEVONO sostituirle.

**Log Tracker.** Il registro generale di tutte le attività, usato dal Coordinatore AI per seguire l'avanzamento e come base del controllo di completezza (§12). Non è pensato per le persone.

**Risk Log.** I rischi di fallimento del progetto e la loro gestione. I rischi di business vanno al Manager umano; il dettaglio resta operativo.

**High Level Architectural View.** Una vista sintetica con un disegno, entro il limite di lunghezza che il mandato fissa, in termini non specialistici e derivata dal documento architetturale: i punti di contatto con le persone; dove stanno i dati e le loro classi di dati; i servizi esterni e i motori AI, distinguendo quelli locali da quelli esterni; i flussi principali e i confini, cioè che cosa esce dall'organizzazione e chi può accedervi. Il Coordinatore AI DEVE aggiornarla ogni volta che una parte nasce, cambia o scompare. Un cambiamento che aggiunge un servizio esterno o sposta dati fuori dall'organizzazione DEVE andare al Manager umano come Do (§5).

**Forma degli artefatti di controllo.** Ogni progetto e ogni Manager umano decidono la forma delle dashboard, delle viste e dei documenti che usano per il controllo, e DEVONO registrare la scelta come decisione di progetto. Il contenuto minimo richiesto da questa Guida e, nella modalità bloccante (§14), dal livello di adozione NON DEVE essere ridotto; nella modalità informativa il contenuto che solo il §14.1 richiede PUÒ essere omesso e DEVE essere elencato nel Security Report, e i documenti che il §12 elenca DEVONO essere tenuti come nella modalità bloccante.

**Vista del Manager.** Lo strumento attraverso cui il Manager umano legge la dashboard di avanzamento, le schede Do e i rilievi indirizzati al Manager umano.

**Scheda di progetto.** La scheda di progetto DEVE identificare: l'applicazione, i suoi utenti, i deliverable, il repository e la revisione; la versione di Eiraman usata, la classe, il livello di adozione e la modalità di classificazione; i componenti Eiraman incorporati nel prodotto e gli eventuali adattamenti; e i criteri di successo.

**Due collegamenti.** Il Coordinatore AI DEVE conservare due collegamenti distinti: tra un Work Package e il rilascio software, e tra una run del prodotto e il deliverable che essa ha generato. Per ogni componente Eiraman adottato DEVE essere registrato dove opera e quale versione è in uso.

### 9.1 Pratiche di test

> **Sezione mantenuta dalla comunità.** Le modifiche sono proposte dai gruppi di lavoro responsabili (Test & Quality; DevSecOps & Tooling; Security, per i test di sicurezza) e accettate dall'Autore tramite RFC senza riscrittura; l'Autore PUÒ restituire una proposta, con motivazione scritta, solo per un conflitto con un'altra parte di questa Guida.

**Livelli di test.** Componente, integrazione, sistema e accettazione. Gli unit test sono test di componente; i test funzionali con script e con utente simulato sono test di integrazione e di sistema; il collaudo di accettazione è il livello di accettazione. I test di sicurezza e di prestazioni sono proporzionati al rischio.

**Pratiche DevSecOps.** Il lavoro segue le pratiche DevSecOps dove si applicano: una storia Git dell'applicazione e delle sue versioni, con messaggi scritti per essere letti anche dalle persone; Security by Design, con analisi statica e, al livello 2, penetration test (§14.1); e test fortemente automatizzati eseguiti da agenti dedicati.

**Tipi di test.**
- Gli *unit test* si eseguono alla fine di ogni Work Package e sono svolti dal tester AI indipendente. Verificano anche i componenti di sicurezza e di prestazioni, e aggiornano la Security Risk Posture e la Performance Analysis.
- *Test funzionali con script:* un agente lancia lo script di test, registra i log e verifica il completamento o il fallimento. L'agente di test NON DEVE correggere di propria iniziativa né la candidata né il proprio script di test: DEVE segnalare ogni errore al Coordinatore AI, che assegna la correzione; per l'agente di test questo limita l'autonomia di Delegate (§5). Correggere lo script di test è un task a sé, assegnato e registrato dal Coordinatore AI; lo stesso agente di test PUÒ riceverlo. Ogni correzione riapre i controlli interessati (§9).
- *Test funzionali con utente simulato:* le User Personas del progetto, come utenti finali simulati, usano l'applicazione come farebbe una persona. Costano di più, perciò si eseguono in ambienti stabili.
- *Collaudo di accettazione:* una persona svolge il compito di business mentre l'AI la assiste, registrando osservazioni e informazioni mancanti. Il Manager umano decide sull'accettazione.

**Chi supervisiona i test.** La persona PUÒ osservare i test funzionali, ma il loro avanzamento NON DEVE dipendere dalla persona. Il collaudo di accettazione è supervisionato dall'AI: la persona esegue e l'AI registra.

## 10. Architettura componibile

**Ordine di costruzione.** Un'applicazione si scompone in componenti legati alle funzioni, sviluppati in modo indipendente nei Work Package. Con l'AI il punto centrale è l'ordine di costruzione: aggiungere pezzi è facile, e senza un catalogo e un ordine il risultato è un patchwork. I componenti DEVONO essere costruiti nella priorità indicata sotto.

**Backbone.** I componenti centrali necessari al core deliverable. Il Backbone ha la priorità più alta. Il primo percorso utilizzabile DEVE attraversarlo in forma minima, insieme al Brain e alle interfacce essenziali. Il Backbone DEVE poi essere completato su tutti i percorsi principali del core deliverable prima che gli altri componenti siano estesi.

**Brain.** La logica dell'applicazione, sempre più spesso fatta di motori AI interni o esterni. I compiti del Brain DEVONO essere catalogati come trusted o untrusted. Il catalogo decide quali compiti si delegano ai motori e quali restano sotto controllo deterministico o richiedono un Do (§11). Il mandato DEVE fissare i criteri con cui un compito del Brain è trusted o untrusted, e il ruolo che li applica.

**Limbs and Senses.** Le interfacce attraverso cui l'applicazione comunica con gli utenti e con altri sistemi. Poggiano su Backbone e Brain. DEVONO essere sviluppate presto in forma essenziale, dentro il primo percorso utilizzabile, e in forma avanzata solo quando i componenti precedenti sono stabili.

**Hairs.** Le funzioni più periferiche, che si possono aggiungere o tagliare in qualsiasi momento, anche per piccoli compiti specifici. Sono ultime in priorità. Prima che una Hair sia tolta, il nucleo DEVE superare i test di regressione.

**Contratto del componente.** Ogni componente DEVE dichiarare il suo contratto, i dati, le dipendenze e la prova di integrazione e, se è periferico, una verifica del comportamento alla sua rimozione. Il primo percorso utilizzabile attraversa Backbone e Brain e include le interfacce essenziali (vedi Backbone).

## 11. Ambiente, esecuzione e sicurezza degli agenti

**Apertura del progetto.** Il Coordinatore AI DEVE risolvere le versioni del metodo e dei profili, verificare il repository e le capacità disponibili, configurare runner e connettori e provare le autorizzazioni necessarie. Un accesso che richiede il titolare dell'account DEVE passare per una richiesta circoscritta a quel titolare. L'ambiente DEVE applicare i vincoli sugli strumenti e conservare i segreti nel deposito credenziali della piattaforma.

**Esecuzioni.** Ogni esecuzione DEVE avere un identificativo, uno stato persistito, la versione degli input, un checkpoint, un budget e un limite di tentativi.

**Ripresa.** Dopo un'interruzione, il Coordinatore AI DEVE riconciliare lo stato con gli effetti già prodotti prima di ripartire. Se il Coordinatore AI non è disponibile, il runtime DEVE conservare il lavoro e impedire nuove operazioni fuori controllo. Al riavvio, il Coordinatore AI DEVE verificare l'ultima consegna, poi riprendere o ripristinare la versione precedente.

**Security Risk Posture.** Ogni progetto DEVE tenere una Security Risk Posture, secondo la Security by Design. Classifica l'applicazione in base a esigenze, contesto e dati trattati, ed elenca i requisiti di sicurezza e di compliance, i dati personali e come sono gestiti, i perimetri di sicurezza, le porte e i servizi aperti e la specifica di sicurezza di ogni componente.

**Sezione Agenti.** La Security Risk Posture DEVE includere una sezione Agenti. Per ogni ruolo elenca gli strumenti ammessi, le destinazioni di rete, i dati leggibili e le azioni irreversibili; le azioni irreversibili DEVONO sempre andare a un Do. I riferimenti riconosciuti per la sicurezza degli agenti, come le indicazioni OWASP sulle applicazioni basate su grandi modelli linguistici e sulle applicazioni agentiche, orientano questa sezione.

**Compiti untrusted.** I compiti del Brain catalogati come untrusted (§10) NON DEVONO essere delegati a un motore senza un controllo deterministico del risultato. Se l'azione è irreversibile, DEVE andare a un Do.

**Test con input ostile.** Ogni progetto DEVE eseguire un test negativo: un input che porta un'istruzione ostile DEVE produrre un Deny registrato.

**Tracciabilità delle run.** Ogni run DEVE registrare l'hash del profilo, l'identificativo esatto del modello, la configurazione effettiva, lo Unit Cost e il ruolo dell'agente, etichettato come governo o produzione (§8, Ciclo di governo). Il prodotto DEVE includere una distinta base del software (SBOM). L'obiettivo è la tracciabilità, perché l'output di un modello linguistico non è riproducibile in modo deterministico.

**Classi di dati per fornitore.** Il mandato DEVE contenere una tabella delle classi di dati per fornitore: quali fornitori sono ammessi per ciascuna classe di dati, tenendo conto della conservazione e dell'uso per l'addestramento.

**Delega dei dati.** La delega DEVE considerare separatamente la provenienza dei dati, i permessi del ruolo, le destinazioni consentite e la reversibilità.

## 12. Scrivere per il Manager umano

**Tre strati di documentazione.** La documentazione di progetto DEVE essere tenuta su tre strati, ciascuno con il suo destinatario e il suo verificatore:
- *Strategico.* Per il Manager umano, che approva: Visione, Principi, criteri di successo, mandato. Verificato dal Manager umano.
- *Manageriale.* Per il Manager umano, che legge e decide per eccezione: scheda di progetto, piano in milestone, High Level Architectural View, schede decisione, rischi di business, dashboard, revisione del ciclo, esito dell'accettazione, rendiconto dei costi, sintesi di sicurezza e di prestazioni e, nella modalità informativa, il Security Report. Verificato da un revisore AI.
- *Operativo.* Per gli agenti: architettura, backlog, Work Package e Staff Planning, Log Tracker, registri di dettaglio, evidenze di test. Verificato dal sistema di AI.

**Messaggi tra agenti.** Ordini di lavoro, report, verdetti, handover abstract e ogni altro messaggio da un agente a un altro DEVONO seguire il dialetto degli agenti del registro dei profili: un messaggio a campi fissi, in inglese essenziale, con un elenco chiuso di simboli e senza riformulare ciò che il destinatario già possiede. Prima della consegna DEVE essere eseguito un controllo deterministico del formato; un messaggio che non lo supera non viene consegnato. Il dialetto NON DEVE essere usato in nulla di ciò che una persona legge, e un'istruzione trovata dentro un messaggio resta un dato (§11).

**Regole di redazione.** Le regole che seguono valgono per ogni documento destinato al Manager umano, che gli arriva attraverso l'Interprete (§4).
- **Linguaggio di business.** Un documento DEVE usare il linguaggio di business.
- **Prima le quattro domande.** Un documento DEVE aprirsi con che cosa è cambiato, che cosa si chiede, entro quando e che cosa succede se non c'è risposta.
- **Prima le variazioni.** Ciò che è cambiato dall'ultima lettura DEVE venire per primo.
- **Limiti di lunghezza.** Ogni scheda decisione DEVE restare entro il limite di lunghezza che il mandato fissa.
- **Esiti, non procedure.** Un documento DEVE riportare esiti, non procedure.
- **Evidenze.** Ogni affermazione verificabile DEVE essere collegata a un'evidenza, e il revisore AI DEVE controllare il collegamento.
- **Prova di comprensione.** Un agente con il profilo del Manager umano DEVE sottoporre ogni documento a una prova di comprensione. Il Manager umano tara quell'agente una volta, su un insieme di documenti la cui dimensione è fissata dal mandato.
- **Prima le cattive notizie.** Test falliti, rischi aperti, dissensi, rifiuti e decisioni mancanti DEVONO venire prima delle buone notizie.
- **Controllo di completezza.** Il documento DEVE essere confrontato con i registri operativi. Un'omissione DEVE bloccarne la consegna.
- **Pacchetto di evidenze per terzi.** Su richiesta, per un singolo rilascio, il Coordinatore AI DEVE produrre un pacchetto che contiene il mandato, la classe, il livello di adozione e la modalità di classificazione, i profili e le versioni, i controlli e gli esiti, le verifiche indipendenti, i rischi accettati e l'accettazione. Al livello 2 il pacchetto DEVE essere pronto a ogni rilascio. Nella modalità informativa il pacchetto DEVE includere il Security Report.
- **Modelli qualificati.** Ogni tipo di documento DEVE avere un modello versionato e qualificato dai manutentori. I modelli sono nel Framework esteso.

**Rendiconto dei costi.** Il rendiconto dei costi DEVE mostrare separatamente i costi di sviluppo e i costi di utilizzo dell'applicazione.

**Security Report.** Nella modalità informativa (§14) ogni rilascio DEVE essere accompagnato da un Security Report. A esso DEVONO applicarsi le regole di redazione, salvo che DEVE aprirsi, al posto delle quattro domande, con una riga fissa che dichiara che il Manager umano risponde di aver proseguito, seguita da ciò che è cambiato dall'ultima lettura, e NON DEVE chiedere nulla. DEVE contenere: la classe, oppure che il caso è fuori perimetro; i rilievi sui dati, ciascuno con il punto in cui è stato trovato; i criteri di esclusione scattati; i motori usati; le protezioni applicate; le protezioni raccomandate e non applicate, tra cui i requisiti non soddisfatti; i limiti dichiarati registrati in base al §13; le azioni che i modelli hanno rifiutato, con il motivo; e ciò che non è stato possibile determinare, comprese le domande sulla sicurezza del giro di domande (§8). DEVE dire dove un rilievo è stato trovato senza riprodurre i dati. DEVE essere aggiornato a ogni Wave e a ogni rilascio.

**Percentuali.** Un avanzamento espresso in percentuale DEVE dichiarare il suo denominatore.

## 13. Role Profile

**Contenuto minimo.** Un Role Profile conforme DEVE contenere almeno:
- scopo, responsabilità, azioni consentite e vietate e contratto di comunicazione;
- fonti normative, ciascuna con un riferimento puntuale alla clausola da cui una regola deriva;
- gli strumenti deterministici obbligatori e come interpretarne gli esiti;
- una suite di qualificazione con casi a risposta nota;
- limiti dichiarati: se un Work Package vi ricade, il progetto esce dal perimetro del metodo; nella modalità informativa del §14 un limite del Security Officer o di un profilo di sicurezza, di privacy o di legale e compliance DEVE invece essere registrato nel Security Report;
- curatore e revisore, e la data e la scadenza della qualificazione.

Ulteriori contenuti, come i motori abilitati, il catalogo dei task per livello di Seniority Digitale (§7.1) e lo Unit Cost per motore, sono specificati nel Framework esteso.

**Pubblicazione.** Prima un modello linguistico DEVE eseguire una pre-valutazione: la suite di qualificazione, la coerenza con le fonti, il formato e la ricerca di istruzioni anomale. Il modello PUÒ respingere un profilo ma NON DEVE approvarlo. Un revisore esperto del dominio pubblica poi il profilo come versione firmata. Le regole di manutenzione, compresi i quattro occhi e i revisori di dominio, sono fissate dalla governance del progetto e dal Framework esteso.

## 14. Applicabilità: classi, livelli e gate

> **Sezione mantenuta dalla comunità.** Questa sezione, con il §14.1 e il §14.2, è proposta dai gruppi di lavoro responsabili (Security, con Privacy e Legal & Compliance; Adoption & Evidence, per le evidenze a sostegno delle soglie) e le modifiche sono accettate dall'Autore tramite RFC senza riscrittura; l'Autore PUÒ restituire una proposta, con motivazione scritta, solo per un conflitto con un'altra parte di questa Guida.

**Modalità di classificazione.** La classificazione di sicurezza di un progetto funziona in una di due modalità. Nella modalità *bloccante* le regole di questa sezione fermano un progetto, come ciascuna di esse dichiara. Nella modalità *informativa* le stesse regole non fermano nulla: il Security Officer le applica per trovare ciò che la modalità bloccante avrebbe fermato o chiesto, e DEVE registrare la classe e ogni rilievo nel Security Report (§12); il Manager umano risponde di aver proseguito. Il Manager umano PUÒ scegliere la modalità all'apertura del progetto, e il mandato DEVE registrare la modalità che si applica. Se non è scelta alcuna modalità, DEVE applicarsi la modalità informativa quando chi adotta usa il metodo per sé, e DEVE applicarsi la modalità bloccante in ogni altro caso. Quando non è scelta alcuna modalità ed è in dubbio se chi adotta usi il metodo per sé, DEVE applicarsi la modalità bloccante; il Coordinatore AI DEVE registrare nel mandato il motivo per cui la modalità si applica. Un'organizzazione PUÒ imporre la modalità bloccante con le proprie regole, che sono un input vincolante del mandato; la modalità che essa impone DEVE applicarsi a ogni progetto aperto, e a ogni nuova versione di un progetto approvata, finché quelle regole sono in vigore. Le regole che raggiungono un progetto già aperto nella modalità informativa NON DEVONO cambiare la modalità della versione in corso: la modalità bloccante che esse impongono DEVE applicarsi solo ai progetti aperti e alle versioni approvate in seguito. La modalità DEVE applicarsi dall'apertura del progetto e NON DEVE cambiare nel suo corso, nemmeno all'approvazione del mandato, salvo che per una nuova versione in base a tali regole; altrimenti una modalità diversa DEVE avere un nuovo progetto. Nella modalità informativa la classificazione NON DEVE fermare né ridurre alcuna azione. Le regole del §14.2 che fermano un progetto o ne limitano i dati o i rilasci, tra cui Discesa automatica ed Esecuzione sopra il livello qualificato, NON DEVONO fermare il progetto né limitarne i dati o i rilasci, salvo che, quando decade un requisito che un'altra regola di questa Guida fissa, l'ambiente DEVE applicare un Deny al lavoro che ne dipende finché il requisito non è ripristinato. Error budget (§14.1) DEVE applicarsi in entrambe le modalità. Un requisito del §14.1, a qualsiasi livello, diverso da Error budget, che nessun'altra regola di questa Guida fissa PUÒ restare non soddisfatto; il Security Report DEVE elencare i requisiti non soddisfatti, fino al livello qualificato o al livello con lo stesso numero della classe del progetto, il più alto dei due, e fino al livello più alto quando il caso è tra quelli fuori perimetro a qualsiasi livello o non rientra in alcuna classe. Salita (§14.2) DEVE applicarsi in entrambe le modalità, e le evidenze di un progetto nella modalità informativa NON DEVONO contare per un livello superiore. In entrambe le modalità un'azione che un modello rifiuta NON DEVE essere eseguita: il Coordinatore AI NON DEVE farla eseguire dallo stesso modello con un'altra richiesta, né da un altro modello, da un'altra candidata o da un altro livello di Seniority Digitale, e quando candidate in concorrenza eseguono lo stesso Work Package, l'output di ogni candidata per quell'azione DEVE essere scartato; nella modalità informativa il rifiuto DEVE essere registrato nel Security Report con il motivo, e nella modalità bloccante nel Log Tracker e nella revisione del ciclo; un rifiuto è un'azione che un modello declina in base alle proprie regole, e NON DEVE contare come un fallimento per carenza di capacità; un'azione che un modello non riesce a completare DEVE seguire il §7.1; il Coordinatore AI DEVE registrare un'azione rifiutata come non eseguita e chiudere il Work Package senza di essa, quando i suoi controlli obbligatori sono superati, oppure ripianificarlo. Quando è in dubbio se un modello declini in base alle proprie regole o non riesca a completare un'azione, il caso DEVE contare come un rifiuto. Quando un'azione rifiutata è un controllo obbligatorio, il Work Package DEVE restare aperto, il controllo NON DEVE essere ripetuto né assegnato a un altro verificatore in base a Dissenso o prova mancante (§9), e il Coordinatore AI DEVE portare la decisione al Manager umano come Do. Le altre regole di questa Guida DEVONO applicarsi in entrambe le modalità.

**Principio.** La competenza specialistica sta nei Role Profile qualificati, non in specialisti presenti in ogni progetto. Nella modalità bloccante il rischio che il Manager umano non può valutare è quindi limitato in partenza; nella modalità informativa è reso noto nel Security Report. Ogni adozione di Eiraman DEVE avere un livello di adozione qualificato e ogni progetto DEVE avere una classe oppure, nella modalità informativa, la registrazione che non rientra in alcuna classe (Fuori perimetro nella modalità informativa). Nella modalità bloccante, un progetto NON DEVE essere eseguito se la sua classe supera il livello qualificato di chi adotta, salvo che per la decisione del Manager umano che il §14.2 consente (Esecuzione sopra il livello qualificato). Nella modalità informativa la classe NON DEVE fermare il progetto, e il Security Officer DEVE registrarla nel Security Report. Chi usa il metodo per sé resta al livello 0. Per salire, chi adotta DEVE soddisfare i requisiti del livello successivo e dimostrarli con evidenze.

**Deliverable.** Le classi valgono anche per i deliverable che un prodotto genera. Per esempio, nella modalità bloccante un'adozione di livello 0 NON DEVE usare un generatore di documenti per produrre documenti destinati a clienti, che sono di classe 2. Nella modalità informativa il Security Officer DEVE registrare nel Security Report la classe dei deliverable.

**Classi di progetto.** A ogni progetto DEVE essere assegnata una delle classi seguenti, salvo che nella modalità informativa un caso che non rientra in alcuna classe DEVE essere registrato come fuori perimetro (Fuori perimetro nella modalità informativa).

| Classe | Utenti | Dati | Esposizione | Esempi |
|---|---|---|---|---|
| 0 | Solo chi adotta | Nessun dato personale di altri | Locale o nessuna | Strumenti personali, generatori di documenti per uso proprio |
| 1 | Colleghi della stessa organizzazione | Dati personali comuni di colleghi | Rete interna o cloud con identità aziendale | Applicazioni di reparto |
| 2 | Clienti, fornitori o un pubblico autenticato | Dati personali comuni di terzi, volumi contenuti | Internet con autenticazione | Portali, servizi self-service, documenti destinati a clienti |

**Fuori perimetro a qualsiasi livello.** Nella modalità bloccante il metodo NON DEVE essere applicato ai progetti che comportano:
- categorie particolari di dati personali o dati relativi a reati;
- dati di minori;
- trattamento di dati personali su larga scala;
- trattamento per cui è obbligatoria una valutazione d'impatto sulla protezione dei dati;
- decisioni automatizzate con effetti giuridici o analogamente significativi sulle persone;
- pagamenti gestiti nel codice proprio del prodotto;
- sistemi di AI che la legge applicabile vieta o classifica ad alto rischio;
- un titolare soggetto agli obblighi di sicurezza delle reti e dei sistemi informativi come soggetto essenziale o importante;
- software distribuito da installare o dispositivi connessi soggetti alla regolamentazione sulla cibersicurezza dei prodotti, finché non esistono requisiti dedicati;
- attività soggette a normativa di settore;
- sicurezza fisica.

Il Framework esteso fa corrispondere queste categorie alla legge di ciascuna giurisdizione, a partire dall'Unione europea.

**Fuori perimetro nella modalità informativa.** Nella modalità informativa i casi elencati sopra NON DEVONO fermare il progetto: il Security Officer DEVE registrare nel Security Report ogni caso che trova. Un caso che non rientra in alcuna classe DEVE essere registrato come fuori perimetro, e la scheda di progetto DEVE dichiararlo al posto della classe.

**Gate di applicabilità.** Il Security Officer, un ruolo AI di compliance con un proprio Role Profile qualificato, DEVE assegnare la classe oppure, nella modalità informativa, registrare che il caso non rientra in alcuna classe, usando una checklist versionata e qualificata dai manutentori. Il Coordinatore AI DEVE invocare il Security Officer e NON DEVE assegnare la classe da sé. Il gate DEVE essere eseguito all'apertura del progetto, a ogni Wave e a ogni cambio di mandato. Nella modalità bloccante, se scatta un criterio di esclusione, o se il caso è in dubbio, il progetto DEVE essere trattato come fuori perimetro e il Manager umano informato; quando il solo dubbio è una domanda all'organizzazione ancora senza risposta, il lavoro su dati di prova che Domande all'organizzazione consente PUÒ proseguire. Nella modalità informativa il gate NON DEVE fermare il progetto: il Security Officer DEVE registrare nel Security Report la classe, i criteri di esclusione scattati e ciò che non ha potuto determinare; quando il perimetro non è cambiato dall'ultima esecuzione, il Security Officer PUÒ registrare il gate ripetuto nel Log Tracker e nel Security Report con un rinvio all'ultima esecuzione.

**Profilo di rischio.** Quando la classe supera il livello qualificato, o scatta un criterio di esclusione, il Security Officer DEVE consegnare un profilo di rischio del progetto: la classe con le risposte alla checklist, le esclusioni toccate, i trattamenti che propone in ordine di preferenza, la classe dopo ciascun trattamento, le sue condizioni, il rischio residuo e ciò che resta impossibile. Una proposta la cui classe dopo il trattamento supera ancora il livello qualificato DEVE dire che non consente al progetto di partire a quel livello; per un progetto di classe 1 in un'adozione al livello 0, senza criteri di esclusione scattati e con la classe non in dubbio, DEVE dire anche che la decisione del §14.2 (Esecuzione sopra il livello qualificato) è disponibile e che cosa richiede oppure, quando il solo dubbio è una domanda all'organizzazione ancora senza risposta, che la decisione è disponibile solo per il lavoro su dati di prova che Domande all'organizzazione consente.

**Trattamenti.** Un trattamento è una forma concreta delle opzioni di Cambio di classe (§14.2) diverse dall'esecuzione per decisione: togliere dati o funzioni dal perimetro; costruire e provare solo su dati di prova o mascherati; tenere i dati reali dentro l'esecuzione locale di chi è già autorizzato a trattarli, senza mai inviarli ad agenti o a servizi esterni. Un trattamento NON DEVE essere presentato come un modo per superare un caso che è fuori perimetro a qualsiasi livello; il solo trattamento di un caso simile DEVE essere togliere dal perimetro il dato o la funzione esclusi, e il perimetro ridotto è un nuovo perimetro che DEVE passare di nuovo il gate.

**Domande all'organizzazione.** Per le domande della checklist la cui risposta spetta all'organizzazione e non al Manager umano, come gli obblighi della normativa sulla sicurezza delle reti e dei sistemi informativi, una valutazione d'impatto sulla protezione dei dati, la normativa di settore o il responsabile della protezione dei dati, il Security Officer DEVE dire chi può rispondere e DEVE preparare la domanda da inoltrare. Una risposta data dal solo Manager umano DEVE essere registrata come non verificata e NON DEVE essere intesa come risoluzione della domanda. Finché l'organizzazione non risponde, il caso DEVE essere trattato come in dubbio (Gate di applicabilità). Nel frattempo, se non scatta alcun criterio di esclusione, il lavoro PUÒ proseguire solo su dati di prova, senza dati reali e senza rilasci, entro la classe che il livello qualificato consente oppure in base alla decisione del §14.2 (Esecuzione sopra il livello qualificato).

**Dialogo con il Manager umano.** Il Manager umano PUÒ interrogare il Security Officer in qualsiasi momento, attraverso il Coordinatore AI. Il Coordinatore AI risponde della forma, in linguaggio di business, e NON DEVE alterare il contenuto. Il profilo di rischio originale DEVE essere allegato senza modifiche nella Vista del Manager.

**Indipendenza del Security Officer.** Il Security Officer propone e NON DEVE agire come revisore. I ruoli di revisore di sicurezza e di revisore di privacy DEVONO restare indipendenti da esso e NON DEVONO essere ricoperti, nello stesso progetto, dal Security Officer o da un agente istanziato dal suo Role Profile. Il Security Officer DOVREBBE operare su un modello diverso da quello del Coordinatore AI, dove ce n'è uno disponibile.

**Security Officer nella modalità informativa.** Nella modalità informativa il Security Officer è silenzioso: NON DEVE avviare uno scambio con il Manager umano né interrogarlo, e NON DEVE scrivere al Manager umano se non nel Security Report e per rispondere alle domande che il Manager umano pone in base a Dialogo con il Manager umano. Il perimetro del progetto NON DEVE essere ridotto a motivo della classificazione. Ciò che il Security Officer non può determinare DEVE essere registrato nel Security Report come non determinato. Il Coordinatore AI PUÒ applicare, per delega, le protezioni proposte dal Security Officer che sono reversibili e non tolgono nulla alla richiesta; DEVONO essere registrate nel Security Report. Profilo di rischio, Trattamenti e Domande all'organizzazione DEVONO applicarsi solo nella modalità bloccante. I rilievi dei revisori di sicurezza, di privacy e di legale e compliance sulla classe, sulla presenza di dati personali e sui criteri di esclusione DEVONO essere registrati nel Security Report e NON DEVONO tenere aperto un Work Package, né fermare o riaprire una fase; gli altri loro rilievi DEVONO seguire il §9, compresi i difetti nel modo in cui il prodotto gestisce i dati personali. Nella Vista del Manager il Security Report corrente DEVE essere allegato al posto del profilo di rischio (Dialogo con il Manager umano).

**Motori locali nella modalità informativa.** I limiti che i fornitori dei motori esterni pongono ai loro modelli non si applicano a un motore che gira in locale. Nella modalità informativa il mandato DEVE dichiarare quali motori locali, se ce ne sono, eseguono gli agenti del progetto o fanno parte del prodotto, così che il Manager umano approvi quell'uso con il mandato; aggiungere un motore locale in seguito è un cambio di mandato e DEVE andare al Manager umano come Do; un motore locale NON DEVE essere usato prima che il Manager umano ne abbia approvato l'uso, con il mandato oppure, prima che il mandato sia approvato, come Do. Il Security Report DEVE nominare i motori usati e, quando uno di essi gira in locale, DEVE dirlo e dire che a esso non si applicano i limiti dei fornitori dei motori esterni.

**Consulenza legale.** La checklist NON DEVE essere usata in sostituzione di una consulenza legale.

### 14.1 Requisiti per livello di adozione

**Requisiti cumulativi.** Ogni livello DEVE soddisfare i propri requisiti e quelli di ogni livello inferiore. I requisiti riguardano il metodo, l'organizzazione e le evidenze. Il Framework esteso dà valori indicativi per le loro soglie e i loro periodi e fa corrispondere i loro riferimenti di legge a ciascuna giurisdizione.

**Livello 0 · Metodo.** Un'adozione per uso personale DEVE usare Role Profile di base qualificati ed eseguire le ancore deterministiche a ogni rilascio (§9). I suoi documenti per il Manager umano DEVONO includere la scheda di progetto con il piano in milestone, le schede decisione, la revisione del ciclo di governo con i rischi di business, la High Level Architectural View, la dashboard di avanzamento e un manuale di installazione e uso.

**Livello 0 · Organizzazione.** Chi adotta DEVE essere titolare del progetto e di ciò che esso produce, e risponde di entrambi (§4), salvo che un progetto eseguito sopra il livello qualificato con un mandato dell'organizzazione (§14.2) appartiene, con ciò che produce, a quell'organizzazione, che risponde di entrambi.

**Livello 0 · Evidenze.** Un'adozione PUÒ partire al livello 0 senza evidenze preliminari.

**Livello 1 · Metodo.** Per salire dal livello 0 all'uso da parte di un team interno, l'adozione DEVE aggiungere:
- profili di sicurezza e di privacy qualificati per la classe 1;
- autenticazione solo tramite l'identità aziendale;
- una prova di backup e ripristino prima del rilascio;
- regole su contenuto e conservazione dei log;
- uno screening di impatto sulla protezione dei dati a ogni cambio di trattamento;
- una procedura di notifica delle violazioni entro il termine della legge applicabile, scritta per il Manager umano;
- per il Manager umano, una sintesi manageriale della Security Risk Posture, una scheda del trattamento per il titolare del trattamento, una Executive Description, il piano in milestone come documento a sé e i rischi di business del Risk Log come registro a sé.

**Livello 1 · Organizzazione.** L'organizzazione titolare DEVE essere identificata. Il Manager umano DEVE agire con un mandato formale da essa conferito (§4). Le politiche IT aziendali DEVONO essere un input vincolante del mandato. Un responsabile della protezione dei dati DEVE essere designato dove l'organizzazione è tenuta ad averne uno.

**Livello 1 · Evidenze.** L'esperienza al livello 0 DEVE mostrare risultati misurati: sotto-escalation entro la soglia, dopo la taratura (E6); rilevazione di una suite di prova deliberatamente vulnerabile almeno alla soglia che i manutentori fissano; nessun rilievo critico aperto al rilascio.

**Livello 2 · Metodo.** Per salire dal livello 1 all'uso da parte di utenti esterni, l'adozione DEVE aggiungere:
- requisiti selezionati e verificati di uno standard riconosciuto di verifica della sicurezza applicativa;
- scansione dinamica a ogni rilascio;
- autenticazione e pagamenti solo tramite fornitori certificati;
- esercizio con obiettivi di livello di servizio, gestione degli incidenti e postmortem senza colpa, che alimentano la retrospettiva;
- una politica di aggiornamento delle dipendenze e di correzione delle vulnerabilità che blocca il rilascio ogni volta che il prodotto è offerto in un'attività commerciale;
- per il Manager umano, una sintesi del penetration test e la Performance Analysis;
- il pacchetto di evidenze per terzi pronto a ogni rilascio (§12).

**Error budget.** In esercizio al livello 2, quando l'error budget è esaurito l'ambiente DEVE applicare un Deny ai rilasci non correttivi.

**Livello 2 · Organizzazione.** Un penetration test esterno, acquistato come servizio, DEVE essere eseguito al primo rilascio e poi periodicamente; il Coordinatore AI ne prepara il perimetro e l'autorizzazione e il Manager umano ne decide il costo. I contratti con i fornitori che trattano dati DEVONO rispettare la normativa sulla protezione dei dati.

**Livello 2 · Evidenze.** L'esercizio al livello 1 DEVE essere durato un periodo definito senza incidenti gravi, e il penetration test del primo rilascio di classe 2 DEVE essere stato superato.

**Documenti di rilascio.** A ogni livello ciascun rilascio DEVE essere accompagnato da un manuale di installazione e uso, più una Executive Description e una Performance Analysis dove il livello le richiede, tutti verificati a quel rilascio. I documenti che ciascun livello richiede sono l'insieme minimo per le regole di redazione del §12.

**Documenti operativi.** A ogni livello lo strato operativo DEVE includere il Product Backlog, le schede dei Work Package, i registri delle run e, per ogni squadra, lo Staff Planning e il Log Tracker.

### 14.2 Passaggi tra livelli e classi

**Salita.** Salire di livello è una porta a una via e DEVE quindi andare al Manager umano come Do. Il Coordinatore AI DEVE presentare un dossier manageriale con i requisiti soddisfatti, le evidenze, i costi ricorrenti e i rischi residui. Un revisore indipendente DEVE verificare le evidenze prima del Do.

**Discesa automatica.** Se un requisito decade, per esempio un profilo sospeso, un penetration test scaduto o un incidente grave aperto, l'ambiente DEVE applicare un Deny. POSSONO essere eseguiti solo rilasci correttivi finché il requisito non è ripristinato o il progetto non torna alla classe consentita.

**Cambio di classe.** Nella modalità bloccante (§14) un cambio di classe DEVE sempre andare al Manager umano come Do e conta nel budget di deriva (E5). Se la nuova classe supera il livello, il Manager umano DEVE scegliere una di quattro opzioni: ridurre il perimetro, affidare il componente critico a un fornitore certificato, togliere quel progetto dal metodo oppure, dove Esecuzione sopra il livello qualificato lo consente, lasciare che il progetto sia eseguito per decisione. Nella modalità informativa un cambio di classe DEVE essere registrato nel Security Report e NON DEVE contare nel budget di deriva (E5) come cambio di classe; la spesa e il tempo del lavoro che esso causa DEVONO contare come ogni altro scostamento dal piano.

**Esecuzione sopra il livello qualificato.** Con una decisione esplicita, il Manager umano PUÒ lasciare che un progetto di classe 1 sia eseguito in un'adozione qualificata al livello 0. Nessun'altra classe e nessun altro livello sono ammessi in questo modo. Ogni progetto DEVE avere la propria decisione. La decisione DEVE essere presa sul profilo di rischio che il Security Officer consegna (§14, Profilo di rischio) e DEVE andare al Manager umano come un Do che dichiara il rischio accettato e come sarà soddisfatto ciascun requisito di questo paragrafo. DEVE essere registrata nella scheda di progetto, con una dichiarazione che il progetto è eseguito sopra il livello qualificato; il pacchetto di evidenze per terzi (§12) DEVE portare quella dichiarazione. Il progetto DEVE soddisfare tutti i requisiti di Metodo del livello 1 (§14.1) prima del suo primo rilascio; un'anteprima data ai colleghi perché la provino non è un rilascio. La decisione esonera solo dalle Evidenze di esperienza al livello 0 che il §14.1 richiede per salire. Tutti i requisiti di Metodo e tutti i requisiti di Organizzazione del livello 1, compreso il mandato formale dell'organizzazione (§4), sono dovuti prima che i dati personali di colleghi siano trattati per la prima volta, e il progetto NON DEVE trattarli fino ad allora; fino ad allora PUÒ essere costruito, provato e mostrato in anteprima solo su dati di prova o mascherati. Se la classe è in dubbio tra la classe 1 e una classe superiore, DEVE essere assunta la classe superiore, anche quando il dubbio dipende da una domanda all'organizzazione ancora senza risposta; l'eccezione indicata sotto per il lavoro su dati di prova non si applica a questo caso. Un caso che il gate di applicabilità tratta come fuori perimetro (§14), perché scatta un criterio di esclusione o perché il caso è in dubbio, o che esce dal perimetro del metodo in base al §13, NON DEVE essere ammesso per decisione, salvo che, finché il solo dubbio è una domanda all'organizzazione ancora senza risposta (§14, Domande all'organizzazione), la decisione PUÒ essere presa per il lavoro su dati di prova che quel paragrafo consente, e per nient'altro. Quando l'organizzazione risponde, il gate DEVE essere eseguito di nuovo, e l'esecuzione oltre quel lavoro DEVE avere una nuova decisione in base a questo paragrafo. Se un requisito del livello 1 che questo paragrafo rende dovuto non è soddisfatto quando è dovuto, o decade in seguito, la classe consentita del progetto è quella del livello qualificato finché il requisito non è soddisfatto, e si applica Discesa automatica. A ogni revisione del ciclo il Coordinatore AI DEVE riportare che il progetto è eseguito sopra il livello qualificato, e DEVE proporre la salita quando le evidenze esistono; l'esperienza raccolta su un progetto simile conta come esperienza al livello 0 per la salita. La decisione non qualifica chi adotta per il livello 1: la salita segue Salita.

## 15. Conformità, applicazione parziale e ritorno al metodo

**Conformità.** Lo strumento che mette in pratica il metodo ne è un'implementazione. DEVE rispettare le regole normative e NON DEVE aggiungere regole proprie e presentarle come Eiraman. Un'applicazione è conforme solo se rispetta tutte le regole normative di questa Guida.

**Applicazione parziale.** Un prodotto che incorpora solo parti del metodo DEVE pubblicare una dichiarazione di conformità parziale, che elenca le regole applicate e quelle non applicate. NON DEVE presentarsi come conforme a Eiraman senza questa qualificazione.

**Componenti incorporabili.** Ogni componente Eiraman che può essere incorporato in un prodotto DEVE dichiarare il suo contratto, le prove di regressione, la versione e le regole che implementa.

**Ritorno al metodo.** I progetti fanno maturare il metodo in tre passi.
- **Osservazione.** La retrospettiva DEVE collegare un caso riproducibile, la regola applicata, l'esito e il costo. Il Coordinatore AI DEVE individuare se la causa sta nei dati, nell'applicazione, nell'ambiente o nel metodo.
- **Proposta.** Una correzione specifica resta nel backlog dell'applicazione. Una regola o un componente riusabile DEVE essere accompagnato da un contratto, una prova, i suoi limiti e il suo impatto sui progetti esistenti, e DEVE essere proposto al metodo come Request for Comments (RFC). Una modifica ai Principi o alle Decisioni di un progetto DEVE seguire le approvazioni del §5.
- **Adozione.** Una modifica approvata DEVE essere versionata, con note di compatibilità, una prova di regressione e l'elenco dei progetti che la adottano. Il progetto che l'ha motivata DEVE conservare un riferimento alla modifica. Un altro progetto PUÒ adottare il solo componente pertinente.

**Misurare il metodo.** Ogni regola del metodo è un'ipotesi finché una misura non la sostiene. Questo paragrafo vincola chi mantiene il metodo, l'Autore per questa Guida e i Manutentori (§4) per il Framework esteso e, con essi, i Role Profile e gli Strumenti; non pone alcun obbligo a carico di chi adotta. Ogni versione di questa Guida, con il Framework esteso, i Role Profile e gli Strumenti rilasciati con essa, DEVE essere misurata su un banco di prova rispetto a una baseline dichiarata; un rilascio di uno di essi che non cambia la Guida è coperto dalla campagna della versione del metodo che lo include. Una versione PUÒ essere rilasciata prima che la sua campagna di misura sia completata, e DEVE allora dichiararsi «non misurata» nel proprio stato. La baseline è la configurazione più semplice senza il metodo: due agenti, uno a una Seniority Digitale (§7) adatta alla progettazione e uno a una Seniority Digitale inferiore adatta all'implementazione, senza Coordinatore AI, senza revisore e con una sola candidata; il Framework esteso indica i livelli e i modelli. La baseline e le configurazioni confrontate con essa DEVONO ricevere la stessa richiesta, gli stessi file e strumenti, lo stesso Manager umano simulato, cioè un agente che interpreta il Manager umano, e gli stessi limiti di tempo e di costo; ogni run DEVE essere isolata dalle altre, e una run oltre i limiti conta come fallita. La baseline DEVE essere eseguita di nuovo a ogni cambio di modello, e un confronto DEVE essere fatto solo tra run con gli stessi modelli. Il collaudo al banco DEVE prendere la consegna così com'è: i collaudatori seguono alla lettera le istruzioni consegnate e non suppliscono con la propria capacità a ciò che manca, e DEVONO registrare come Fault, cioè ogni caso in cui la consegna non fa ciò che le sue istruzioni dicono o ciò che è stato chiesto, tutto ciò che non funziona. I collaudatori DEVONO essere indipendenti da chi ha sviluppato la consegna e NON DOVREBBERO usare modelli più capaci di quelli sotto misura. Seniority del verificatore (§6) non si applica a loro. Le richieste, i brief del Manager umano simulato e i risultati attesi dei test DEVONO essere scritti da qualcuno diverso da chi mantiene il metodo, e DEVONO essere congelati prima della campagna; gli agenti misurati NON DEVONO vedere i brief né i risultati attesi. Un indicatore giudicato da un modello DEVE seguire K1 (§6). Il collaudo al banco misura il metodo; è distinto dal collaudo di accettazione del §9.1, in cui una persona svolge il compito di business di un progetto e il Manager umano decide sull'accettazione, e nessuno dei due sostituisce l'altro. Le ipotesi di una campagna, ciascuna con il suo indicatore primario, il suo margine e il suo numero di ripetizioni, DEVONO essere registrate prima della campagna e NON DEVONO cambiare dopo di essa; ogni risultato DEVE essere conservato e contato, comprese le run sfavorevoli, fallite e interrotte. Quando una prova che toglie una sola regola esclude, con le ripetizioni dichiarate prima della campagna, un beneficio superiore al margine dichiarato, chi coordina il lavoro sul metodo DEVE proporre al Manager umano di ridurre quella regola a Indicazione o di toglierla. Quando una campagna completata dimostra, entro il margine dichiarato, che per una classe di progetto la baseline ottiene lo stesso risultato a un costo minore, l'Autore DEVE dichiararlo in questa Guida e indicare la baseline per quella classe; la conclusione vale solo per le classi che il banco rappresenta. Un esito «non dimostrato» non basta né per l'una né per l'altra cosa. Il Framework esteso dà come Indicazioni gli indicatori, che cosa conta come stesso risultato, la misura del costo di riallineamento, le applicazioni di prova, il numero di ripetizioni, i limiti e i modelli della baseline.

**Modificare il metodo.** Questa Guida DEVE cambiare solo attraverso una RFC, decisa dall'Autore con motivazione scritta. Le sezioni mantenute dalla comunità sono proposte dai loro gruppi di lavoro e accettate dall'Autore tramite RFC senza riscrittura; l'Autore PUÒ restituire una proposta, con motivazione scritta, solo quando è in conflitto con un'altra parte di questa Guida. Il Framework esteso, i Role Profile e gli Strumenti sono governati dalla comunità secondo la governance del progetto. Una decisione della comunità che cambierebbe il testo di questa Guida DEVE avere anche una RFC della Guida accettata.

## 16. Nota finale

**Storia delle versioni.** La versione 1.0 sostituisce la specifica italiana 0.3, che resta la fonte storica ed è conservata, non normativa, in `history/`. La versione 1.0 è la prima in inglese canonico con una licenza aperta; separa questa Guida dal Framework esteso e apre una parte della Guida alla manutenzione della comunità. La versione 0.3 ha ripristinato le AI Squad, il Design Thinking tra modelli e l'architettura componibile, e ha aggiunto la Seniority Digitale. La versione 0.2 ha rivisto responsabilità, livelli, escalation, concorrenza e conformità. La storia completa è in `HISTORY.md`.

**Ringraziamenti.** Eiraman attinge a pratiche consolidate di management e di ingegneria. La Scrum Guide è opera di Ken Schwaber e Jeff Sutherland. TOGAF® è un marchio registrato di The Open Group. Le fonti delle regole di questa Guida sono elencate nel corpo di conoscenze del Framework esteso.
