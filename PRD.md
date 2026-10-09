# PRD Template in modifica

# PRD di ScuolaChill · Team DevRoadsters

---

## Informazioni sul documento

|  |  |
| --- | --- |
| **Prodotto** | ScuolaChill |
| **Team** | DevRoadsters |
| **Autori** | Antonio Mihut - Mattia Artico |
| **Versione** | 1.0 |
| **Data** | 09/10/2026 |
| **Stato** | *Bozza*  |

### Storico delle versioni

| Versione | Data | Autore | Cosa è cambiato e perché |
| --- | --- | --- | --- |
| 0.1 | 25/09/2026 | Mattia Artico e Antonio Mihut | Prima stesura (resta da vedere).  |
| 0.2 | 26/09/2026 | Mattia Artico e Antonio Mihut | Definizione dei destinatari e del contesto d'uso |
| 0.3 | 29/09/2026 | Mattia Artico e Antonio Mihut | Definizione della panoramica e dei casi d'uso |
| 0.4 | 30/06/2026 | Mattia Artico | Definizione dei requisiti funzionali |
| 1.0 | 09/10/2026 | Mattia Artico e Antonio Mihut | Rimozione della rilevazione presenze: in ambito ITS è gestita a livello regionale. Aggiunta della gestione comunicazioni. Aggiunta dei requisiti non funzionali, requisiti impliciti, assunzioni, vincoli, dipendenze e stime di carico. Sistemazione di inesattezze nel documento. |

---

# Prima parte · Il cosa

## Scopo e perimetro

### Perché esiste ScuolaChill

**Dal lato business.** 

Fornisce un set di strumenti utilizzabili da una scuola, ovvero dirigente, docenti e studenti, per svolgere le molteplici attività didattiche di un corso di **Istituto Tecnologico Superiore**: gestire le classi, il materiale didattico, il percorso didattico (con verifiche e voti).

**Dal lato tecnico.**

Dal punto di vista architetturale e funzionale, il sistema copre l'intero ciclo di vita della didattica digitale: dalla gestione anagrafica e dei permessi basati sui ruoli (dirigenti, docenti, studenti) fino alla gestione dei materiali tramite schede con titolo, descrizione e link esterno. Inoltre, integra moduli dedicati al tracciamento dei percorsi di valutazione (verifiche e registrazioni dei voti).

### Cosa è incluso

- Gestione di classi
- Gestione di docenti
- Gestione di studenti
- Gestione di orario
- Gestione di attività nel calendario scolastico: attività didattiche, gite ed escursioni
- Gestione di eventi extra
- Gestione di voti e pagelle
- Autenticazione mail-password
- Comunicazioni interne

### Cosa non è incluso

- Strumenti di e-learning (come quiz interattivi)
- Tracciamento e gestione delle presenze
- Gestione di tirocini curriculari
- Gestione contabilità/pagamenti
- Gestione inventario
- Reportistica ed esportazione avanzata

---

## Stakeholder

| Stakeholder | Cosa fa | Cosa gli interessa | Come lo/li coinvolgete |
| --- | --- | --- | --- |
| Direttore | Configura la scuola, crea docenti e studenti, organizza le classi e consulta la situazione generale | Avere una visione completa e aggiornata della scuola, ridurre il lavoro amministrativo e garantire la correttezza dei dati | Validazione dei requisiti, revisione dei prototipi e collaudo delle funzioni principali |
| Docente | Gestiscono il materiale didattico, creano verifiche, assegnano voti e consultano le classi | Caricare i link ai materiali, gestire le verifiche senza errori e inserire i voti in modo semplice e sicuro | Osservazione delle attività quotidiane, test dei flussi e raccolta di feedback |
| Studente | Consultano materiali, svolgono verifiche e controllano i propri voti | Usare il sistema facilmente anche da smartphone, non perdere il lavoro e vedere sempre informazioni aggiornate | Usabilità e collaudo sul campo |
| Docente del corso | Valida il PRD e verifica che le scelte progettuali rispettino la traccia e gli obiettivi didattici | Chiarezza dei requisiti, correttezza dell'architettura e completezza della documentazione | Presentazione del PRD, revisioni periodiche, domande di chiarimento e approvazione delle modifiche |
| Collaudatore del primo anno | Usano ScuolaChill come utenti reali durante le prove di collaudo | Completare le attività senza aiuto, capire subito cosa fare e non perdere dati durante le verifiche | Sessioni di collaudo osservate, raccolta degli errori |
| Team di sviluppo | Progetta, implementa, testa e mantiene il sistema | Requisiti chiari, scelte tecniche sostenibili, sicurezza e facilità di manutenzione | Riunioni di analisi, revisione del codice, test automatici e aggiornamento dello storico delle decisioni |

---

## Destinatari e contesto d'uso

### La scuola che avete immaginato

Un **Istituto Tecnologico Superiore (ITS) diffuso sul territorio regionale**, strutturato su **circa 10 sedi operative** che accolgono tra i 1.000 e i 1.100 studenti suddivisi in 25–30 classi. Le attività didattiche si articolano dal lunedì al venerdì in blocchi intensivi (8:00–13:00 e 14:00–18:00) tra lezioni teoriche e sessioni pratiche di laboratorio, con docenti professionisti spesso condivisi tra più sedi.

|  | Valore |
| --- | --- |
| Numero di studenti | 1000-1100 |
| Numero di docenti | 50 |
| Numero di classi | 25-30 |
| Orario scolastico | 8:00 – 13:00, 14:00-18:00, dal lunedì al venerdì |
| Connettività | Previsto un traffico medio di 10 Mbps, con picchi fino a 100 Mbps: limite cautelativo desiderabile di 200 Mbps. Previsto un collegamento misto sia da telefono che da PC. |

### Gli archetipi

Arricchisci gli archetipi della traccia.

| ID | Archetipo | Contesto d'uso | Competenze digitali | Dispositivo principale | Frequenza d'uso |
| --- | --- | --- | --- | --- | --- |
| ARC-001 | Direttore | Coordina l'ITS e monitora studenti, docenti, classi, orario e attività tra le varie sedi | Medio-alte | PC portatile o fisso | Quotidiana |
| ARC-002 | Docente | Gestisce materiali, verifiche, voti e calendario delle proprie classi | Da medie ad alte | PC portatile o fisso; smartphone per consultazioni rapide | Quotidiana |
| ARC-003 | Studente | Consulta materiali e orario, svolge verifiche e controlla voti e attività | Medie | Smartphone; PC del laboratorio quando necessario | Quotidiana, con picchi durante le verifiche |

---

## Panoramica e casi d'uso

### ScuolaChill in poche righe

**ScuolaChill è un programma pensato per rendere più semplice la gestione quotidiana di un ITS generico, che conta una decina di sedi.**

L’idea è avere un unico posto dove poter organizzare e controllare tutte le informazioni importanti della scuola: studenti, classi, docenti, lezioni, attività e comunicazioni.

Invece di avere informazioni sparse tra diversi strumenti o documenti, ScuolaChill permette di avere tutto organizzato e facilmente consultabile, anche considerando le diverse sedi dell’ITS.

Il nostro obiettivo è **ridurre il lavoro manuale, evitare confusione e rendere più veloce la gestione della scuola**, sia per chi lavora nell’amministrazione sia per chi si occupa della didattica.

In poche parole, **ScuolaChill vuole diventare un punto di riferimento unico per la gestione dell’ITS**, semplice da usare e costruito sulle esigenze reali dell’istituto.

### User flow e scenari

#### 👔 DIRETTORE

#### DIR-01 · Gestire classi e sedi

- **User flow:**
    1. Il Direttore accede all'area Classi.
    2. Visualizza l'elenco delle classi per sede e corso.
    3. Crea una nuova classe o ne modifica una esistente.
    4. Associa studenti e docenti alla classe.
    5. Salva le modifiche.
- **Scenario principale:** Il Direttore deve organizzare una nuova classe per un corso ITS. Crea la classe, assegna il corso e la sede e associa gli studenti e i docenti. La nuova classe diventa quindi disponibile nel gestionale.
- **Scenari alternativi:**
    - Classe duplicata → notifica di duplicazione.
    - Mancano campi obbligatori → salvataggio bloccato.
    - Uno studente è già assegnato a un'altra classe → viene mostrato un avviso.

#### DIR-02 · Gestire docenti e studenti

- **User flow:**
    1. Il Direttore accede alla sezione Utenti (Docenti o Studenti).
    2. Cerca un utente o seleziona la creazione di un nuovo profilo.
    3. Inserisce o aggiorna i dati anagrafici e scolastici.
    4. Associa l'utente al corso o alla classe di pertinenza.
    5. Salva i dati.

- **Scenario principale:** Il Direttore deve pianificare un'uscita didattica per una classe. Inserisce data, orario, destinazione e classe coinvolta: l'attività viene registrata e compare nei calendari scolastici di docenti e studenti.
- **Scenari alternativi:**
    - Utente già registrato → notifica di possibile duplicato.
    - Dati obbligatori mancanti → salvataggio bloccato.
    - L'utente viene associato alla classe sbagliata → il Direttore può correggere l'associazione.

#### DIR-03 · Gestire orario e calendario didattico

- **User flow:**
    1. Il Direttore apre la sezione Calendario.
    2. Seleziona una data e crea una nuova attività didattica, gita o escursione.
    3. Definisce sede, classe coinvolta e orario.
    4. Salva l'attività a calendario.
- **Scenari alternativi:**
    - L'attività viene annullata → può essere modificata o rimossa dal calendario.
    - Conflitto di orario o aula già occupata → segnalazione di sovrapposizione.
    - Informazioni mancanti → salvataggio bloccato.

#### DIR-04 · Gestire eventi extra

- **User flow:**
    1. Il Direttore accede alla sezione Eventi.
    2. Seleziona l'inserimento di un nuovo evento.
    3. Inserisce titolo, data, orario e classi o persone interessate.
    4. Salva l'evento.
- **Scenario principale:** L'ITS organizza un incontro seminariale con un'azienda partner. Il Direttore crea l'evento e inserisce i dettagli organizzativi: l'incontro compare automaticamente nel calendario degli studenti e docenti coinvolti.
- **Scenari alternativi:**
    - Data o orario non validi → errore a schermo.
    - Modifica o annullamento dell'evento → aggiornamento della voce a calendario.

#### DIR-05 · Consolidare e approvare le pagelle

- **User flow:**
    1. Il Direttore apre la sezione Pagelle.
    2. Seleziona la classe e il periodo di riferimento.
    3. Verifica i risultati e le valutazioni finali per ciascuno studente.
    4. Conferma la pagella.
    5. La pagella definitiva viene resa visibile allo studente.
- **Scenario principale:** Al termine del periodo formativo, il Direttore controlla le valutazioni riepilogative caricate per ciascuna classe. Dopo aver verificato la completezza dei voti, valida e pubblica le pagelle per gli studenti.
- **Scenari alternativi:**
    - Valutazioni parziali o mancanti → blocco del consolidamento della pagella.
    - Correzione necessaria prima dell'approvazione → modifica del voto da parte dell'utente autorizzato.

#### DIR-06 · Inviare comunicazioni interne

- **User flow:**
    1. Il Direttore apre la sezione Comunicazioni.
    2. Crea un nuovo avviso e inserisce titolo e testo.
    3. Sceglie i destinatari: tutta la scuola oppure una o più classi.
    4. Pubblica l’avviso.
    5. L’avviso diventa visibile agli utenti destinatari.
- **Scenario principale:** Il Direttore deve comunicare una variazione organizzativa a due classi. Seleziona le classi, pubblica l’avviso e gli studenti destinatari lo trovano nella sezione Comunicazioni.
- **Scenari alternativi:**
    - Titolo, testo o destinatari mancanti → pubblicazione bloccata e campi da completare indicati.

#### 👨‍🏫 DOCENTE

#### DOC-01 · Consultare il proprio orario

- **User flow:**
    1. Il Docente accede alla sezione Orario o Calendario.
    2. Visualizza la pianificazione delle proprie lezioni.
    3. Seleziona una lezione specifica.
    4. Consulta materia, classe, aula, sede e orario.
- **Scenario principale:** Il docente Marco accede a ScuolaChill la mattina prima di iniziare la giornata. Controlla il calendario, verifica di avere lezione alle 9:00 e sa con precisione in quale aula e sede recarsi.
- **Scenari alternativi:**
    - Modifica di orario o aula → aggiornamento automatico della vista.
    - Una lezione viene annullata → compare come annullata a calendario.
    - Assenza di lezioni nella giornata → visualizzazione del calendario libero.

#### DOC-02 · Pianificare attività didattiche e date verifiche

- **User flow:**
    1. Il Docente apre la sezione Calendario della propria classe.
    2. Crea una nuova attività didattica o fissa una data per una verifica in aula.
    3. Inserisce titolo, materia, data e descrizione degli argomenti.
    4. Salva l'attività a calendario.
- **Scenario principale:** Il docente Luca stabilisce la data di una prova scritta in aula. Inserisce l'attività sul calendario con l'elenco degli argomenti trattati, consentendo agli studenti di prendere nota della scadenza e organizzare lo studio.
- **Scenari alternativi:**
    - Sovrapposizione con un'altra verifica o evento → avviso di data già impegnata.
    - Dati obbligatori mancanti → salvataggio bloccato.

#### DOC-03 · Registrare le valutazioni (Registro voti)

- **User flow:**
    1. Il Docente apre la sezione Valutazioni della classe interessata.
    2. Seleziona la verifica o l'attività didattica svolta.
    3. Inserisce il voto per i singoli studenti esaminati.
    4. Controlla il riepilogo dei voti assegnati.
    5. Conferma il salvataggio dei risultati nel registro valutazioni.
- **Scenario principale:** Dopo aver corretto le prove svolte dagli studenti, il docente registra i voti nel registro continuativo. I dati inseriti rimangono visibili allo studente e formeranno la base per la pagella finale.
- **Scenari alternativi:**
    - Inserimento di un voto fuori scala consentita → segnalazione di errore.
    - Studente privo di voto → avviso di dato non pervenuto.

#### DOC-04 · Consultare le classi assegnate

- **User flow:**
    1. Il Docente apre la sezione Le mie classi.
    2. Seleziona una classe specifica.
    3. Visualizza l'elenco degli studenti iscritti.
    4. Consulta le attività pianificate e lo storico delle valutazioni.
- **Scenario principale:** Il docente Marco deve preparare una sequenza didattica. Accede alla scheda della propria classe per rivedere l'elenco degli allievi, le scadenze pianificate e i risultati ottenuti fino a quel momento.
- **Scenari alternativi:**
    - Classe non ancora assegnata → messaggio informativo.
    - Aggiornamento dell'elenco studenti → sincronizzazione automatica dei nominativi.

#### DOC-05 · Pubblicare materiali didattici

- **User flow:**
    1. Il Docente apre la sezione Materiali didattici.
    2. Crea una nuova scheda e inserisce titolo, descrizione e link esterno.
    3. Associa la scheda a una o più classi assegnate.
    4. Salva la scheda, che diventa consultabile agli studenti delle classi selezionate.
- **Scenario principale:** Il Docente vuole condividere un articolo online con una classe. Crea la scheda con titolo, descrizione e link, la associa alla classe e gli studenti la possono consultare.
- **Scenari alternativi:**
    - Titolo, descrizione o link mancanti o non validi → salvataggio bloccato e campo da correggere indicato.
    - Nessuna classe selezionata → salvataggio bloccato.

#### 🎓 STUDENTE

#### STU-01 · Consultare orario e calendario

- **User flow:**
    1. Lo Studente apre la sezione Orario o Calendario.
    2. Visualizza le lezioni della giornata e delle date successive.
    3. Seleziona una lezione o attività.
    4. Consulta materia, docente, sede, aula e orario.
    5. Consulta le date programmate per verifiche in aula, uscite ed eventi extra.
- **Scenario principale:** Antonio consulta ScuolaChill la sera prima delle lezioni per conoscere l'orario del giorno dopo, la sede dove recarsi, il materiale necessario e le date delle prossime verifiche in programma.
- **Scenari alternativi:**
    - Variazione di aula o orario → calendario aggiornato con le nuove informazioni.
    - Giornata priva di lezioni → indicazione di giornata libera.

#### STU-02 · Consultare il registro valutazioni

- **User flow:**
    1. Lo Studente apre la sezione Valutazioni.
    2. Visualizza i voti conseguiti nelle diverse materie.
    3. Seleziona una materia per consultare il dettaglio delle singole verifiche svolte.
- **Scenario principale:** Dopo una verifica in aula, Antonio entra nella propria area personale per visualizzare il voto inserito dal docente e controllare la media dei risultati ottenuti nella materia.
- **Scenari alternativi:**
    - Voto non ancora pubblicato dal docente → voce indicata come in attesa di esito.
    - Nessuna valutazione registrata → messaggio informativo.

#### STU-03 · Consultare la pagella

- **User flow:**
    1. Lo Studente accede alla sezione Pagella.
    2. Seleziona il periodo concluso.
    3. Visualizza i voti finali per ciascuna materia e l'esito approvato dalla direzione.
- **Scenario principale:** A conclusione del semestre didattico, Antonio consulta la propria pagella definitiva validata dal Direttore, verificando il superamento di tutte le materie del periodo.
- **Scenari alternativi:**
    - Pagella non ancora consolidata o confermata → indicazione di documento in lavorazione.
    - Errore temporaneo di connessione o caricamento → messaggio di errore e possibilità di riprovare.

#### STU-04 · Consultare i materiali didattici

- **User flow:**
    1. Lo Studente apre la sezione Materiali didattici.
    2. Visualizza le schede associate alla propria classe.
    3. Apre la scheda per leggere titolo e descrizione.
    4. Seleziona il link per raggiungere la risorsa esterna.
- **Scenario principale:** Lo Studente cerca il materiale assegnato dal Docente, apre la scheda e segue il link all’articolo indicato.
- **Scenari alternativi:**
    - Nessun materiale associato alla classe → messaggio informativo.

#### STU-05 · Consultare le comunicazioni interne

- **User flow:**
    1. Lo Studente apre la sezione Comunicazioni.
    2. Visualizza gli avvisi destinati a tutta la scuola o alla propria classe.
    3. Seleziona un avviso e ne legge il contenuto.
- **Scenario principale:** Il Direttore pubblica un avviso per la classe dello Studente. Lo Studente lo trova nella sezione Comunicazioni e legge le informazioni.
- **Scenari alternativi:**
    - Nessun avviso disponibile per lo Studente → messaggio informativo.
    - Avviso destinato a un’altra classe → non compare nell’elenco dello Studente.

---

## Requisiti funzionali

### Le user story della traccia

| ID | Storia | AC aggiunti dal team | Note |
| --- | --- | --- | --- |
| DIR-01 | Gestire classi e sedi | Dato che il Direttore sta creando una classe, quando inserisce una combinazione sede-corso già esistente, allora il sistema impedisce il salvataggio e segnala il duplicato. | - |
| DIR-02 | Gestire docenti e studenti | Dato che un utente possiede già l’indirizzo email inserito, quando il Direttore prova a registrarlo nuovamente, allora il sistema segnala il duplicato. | - |
| DIR-03 | Gestire orario e calendario didattico | Dato che il Direttore crea un’attività nel calendario, quando data, orario o classe non sono validi, allora il sistema blocca il salvataggio e indica il campo da correggere. | - |
| DIR-04 | Gestire eventi extra | Dato che il Direttore crea un evento per più classi, quando lo salva, allora l’evento compare nei calendari di tutti gli utenti interessati. | - |
| DIR-05 | Consolidare e approvare le pagelle | Dato che una o più valutazioni obbligatorie sono mancanti, quando il Direttore prova a consolidare la pagella, allora il sistema blocca l’operazione e mostra quali dati mancano. | - |
| DIR-06 | Inviare comunicazioni interne | Dato che il Direttore ha inserito titolo, testo e destinatari, quando pubblica l’avviso, allora questo è visibile a tutta la scuola o alle classi selezionate. | - |
| DOC-01 | Consultare il proprio orario | Dato che il docente ha lezioni assegnate, quando apre il calendario, allora visualizza solo le lezioni pertinenti al proprio profilo. | - |
| DOC-02 | Pianificare attività didattiche e date verifiche | Dato che il docente sta creando una verifica, quando non inserisce titolo, materia o data, allora il sistema blocca il salvataggio. | - |
| DOC-03 | Registrare le valutazioni (Registro voti) | Dato che il docente inserisce un voto, quando il valore è al di fuori della scala stabilita dal team, allora il sistema rifiuta il valore e mostra l’intervallo consentito. | - |
| DOC-04 | Consultare le classi assegnate | Dato che il docente è assegnato a più classi, quando apre “Le mie classi”, allora visualizza tutte e soltanto le classi a lui assegnate. | - |
| DOC-05 | Pubblicare materiali didattici | Dato che il Docente inserisce titolo, descrizione, link valido e classi destinatarie, quando salva la scheda, allora questa è visibile agli studenti delle classi selezionate e consente di aprire il link esterno. | ScuolaChill salva la scheda e il link, non il file esterno. |
| STU-01 | Consultare orario e calendario | Dato che lo studente accede al calendario, quando seleziona una lezione, allora visualizza almeno materia, docente, sede, aula e orario. | - |
| STU-02 | Consultare il registro valutazioni | Dato che un voto non è stato ancora pubblicato, quando lo studente consulta la materia, allora visualizza lo stato “in attesa di pubblicazione” senza vedere il voto. | - |
| STU-03 | Consultare la pagella | Dato che la pagella non è stata ancora approvata, quando lo studente accede alla sezione, allora visualizza lo stato “in lavorazione” e non una pagella definitiva. | - |
| STU-04 | Consultare i materiali didattici | Dato che una scheda è associata alla classe dello Studente, quando apre la sezione Materiali, allora può consultare la scheda e seguire il link alla risorsa esterna. | Lo Studente vede solo i materiali delle proprie classi. |
| STU-05 | Consultare le comunicazioni interne | Dato che un avviso è destinato a tutta la scuola o alla classe dello Studente, quando apre Comunicazioni, allora può visualizzarlo; gli avvisi di altre classi non compaiono. | - |

### Le decisioni lasciate aperte dalla traccia

**FR-VAL-01 · Scala dei voti** (collegato a DOC-03)

Scelta: ammettere voti da 1 a 10 con incrementi di 0,5; non ammettere i segni “+” e “−”. Il sistema rifiuta valori fuori intervallo o non conformi all’incremento.

Motivazione: una scala numerica così fatta sembra plausibile nel contesto formativo; è semplice da inserire, confrontare e validare.

**FR-CLS-01 · Trasferimento fra classi** (collegato a DIR-02)

Scelta: il Direttore può trasferire uno studente indicando la data di decorrenza. I voti già registrati restano associati alla classe e al periodo in cui sono stati conseguiti; i voti successivi fanno riferimento alla nuova classe. Il trasferimento non cancella né sposta voti pregressi.

Motivazione: preservare lo storico e distinguere chiaramente i risultati ottenuti prima e dopo il trasferimento.

**FR-VER-01 · Modifica di una “scheda” verifica svolta** (collegato a DOC-02)

Scelta: dopo il completamento, il docente non può modificare le informazioni della verifica; il Direttore può correggere i dati descrittivi in caso di errore, lasciando traccia della modifica. I voti registrati possono essere eccezionalmente alterati, con motivazione specificata.

Motivazione: mantenere affidabile lo storico senza impedire la correzione di errori amministrativi.

**FR-EXT-01 · Mancato invio dell’email di attivazione** (collegato a DIR-02)

Proposta: se il servizio email non è disponibile, il profilo viene salvato con invito in attesa e l’invio può essere riprovato o reinviato dal Direttore. L’utente non accede finché non completa l’attivazione.

Motivazione: un disservizio email non deve causare la perdita delle informazioni di profilo già inserite.

---

## Requisiti non funzionali

Ogni requisito ha una soglia, una condizione e un modo per verificarlo. Ed è collegato ad almeno una user story.

| ID | Famiglia | Requisito | Soglia e condizione | Come si verifica | Storie collegate |
| --- | --- | --- | --- | --- | --- |
| NFR-01 | Prestazioni | Tempo di risposta nella consultazione dell'orario/calendario | Risposta delle chiamate API di lettura in meno di $2,0\text{ s}$ per il 95% delle richieste. | Misurazione dei tempi di risposta tramite la scheda *Network* di *DevTools* o *Postman*. | STU-01, DOC-01 |
| NFR-02 | Sicurezza | *Controllo degli accessi basato sui ruoli (RBAC)* | Blocco totale dell'accesso a rotte riservate se l'utente non possiede il ruolo adatto (es. uno studente non può invocare API di voto). | Invio di richieste API protette utilizzando i token di ruoli diversi e verifica delle risposte `401 Unauthorized` o `403 Forbidden`. | DIR-01, DIR-02, DOC-03, STU-02 |
| NFR-03 | Usabilità | Semplicità e chiarezza dell'interfaccia | Esecuzione delle operazioni quotidiane (consultazione orario, inserimento voto) entro un massimo di 3-4 click. | Sessioni di prova pratica e collaudo guidato con utenti studenti e docenti. | STU-01, STU-02, DOC-01, DOC-03 |
| NFR-04 | Disponibilità | Persistenza garantita dei voti *(Requisito Implicito* | Nessuna perdita di voti confermati dal sistema; salvataggio tramite transazioni atomiche sul database. | **Test di inserimento, ricaricamento pagina e verifica diretta dell'avvenuta scrittura sulla tabella DB.** | DOC-03, STU-02, DIR-05 |
| NFR-05 | Ambientale | Efficienza energetica lato client | Dimensione contenuta dell'applicazione frontend e assenza di chiamate di *polling* continuo e infruttuoso verso il server. | Analisi del traffico di rete generato a pagina ferma tramite la scheda *Network* del browser. | STU-01, DOC-01 |
| NFR-06 | Supporto (Trasversale) | Documentazione delle API (OpenAPI) | 100% delle rotte esposte dal backend documentate con specifica OpenAPI 3.0 e consultabili graficamente via Swagger UI. | Navigazione della rotta `/api-docs` (o equivalente) e verifica della presenza di rotte, parametri e modelli di risposta. | DIR-01, DOC-02, STU-01 |
| NFR-07 | Interazione | Responsive design e compatibilità multi-dispositivo | Layout adatta per la fruizione sia su schermi mobile (smartphone, a partire da $320\text{px}$) che su schermi desktop (PC di laboratorio). | Ridimensionamento della finestra del browser e test di navigazione tramite l'emulatore dispositivi di *DevTools*. | STU-01, STU-02, DOC-01 |
| NFR-08 | Conformità | Rispetto della privacy e tutela dei dati (GDPR) | Conservazione dei dati personali e delle valutazioni su database allocato in datacenter all'interno dell'Unione Europea. | Controllo della regione geografica selezionata nelle impostazioni del provider Cloud (es. `eu-west`). | DIR-02, STU-03 |
| NFR-9 | Scalabilità | Sostegno della crescita della popolazione scolastica | L'architettura deve supportare fino a 1.100 utenti registrati e picchi di 450 utenti contemporanei senza richiedere modifiche al codice. | Simulazione di chiamate API simultanee mediante script o test manuali paralleli su più schede/client. | DIR-01, DOC-01, STU-01 |
| NFR-10 | **Supporto** *(Trasversale)* | Documentazione delle API (OpenAPI) | 100% delle rotte esposte dal backend documentate con specifica OpenAPI 3.0 e consultabili graficamente via Swagger UI. | Navigazione della rotta `/api-docs` (o equivalente) e verifica della presenza di rotte, parametri e modelli di risposta. | DIR-01, DOC-02, STU-01 |
| NFR-11 | **Supporto** *(Trasversale)* | Gestione uniforme degli errori | Tutte le risposte di errore dell'API devono restituire una struttura JSON standardizzata contenente codice di stato e messaggio chiaro. | Invio di richieste errate/incomplete (es. payload mancante) e verifica della struttura JSON restituita (`code`, `message`). | DIR-01, DOC-03, STU-02 |
| NFR-12 | **Supporto** *(Trasversale)* | Separazione degli ambienti (Dev e Prod) | Completa separazione tra ambiente di sviluppo locale e ambiente Cloud di test/produzione (database, credenziali e variabili d'ambiente distinti). | *Code review* dei file di configurazione (`.env.example`, `.env.local`, `.env.production`). | DIR-02, DOC-03 |
| NFR-13 | Prestazioni | Tempo di registrazione valutazioni | Salvataggio ed esito della registrazione voto in meno di $2,0\text{ s}$. | Ispezione dei tempi di chiamata durante l'invio della form di valutazione nei test. | DOC-03, STU-02 |
| NFR-14 | **Prestazioni** *(Trasversale)* | Paginazione delle risorse ampie | Tutte le API che restituiscono elenchi ampi (studenti, voti) devono restituire i dati paginati (default 20-50 elementi per pagina). | Verifica dei parametri di query `page` e `limit` e della risposta JSON nell'interfaccia *Swagger UI*. | DIR-01, DOC-04, STU-02 |
| NFR-15 | Disponibilità | Stabilità e continuità del servizio | Assenza di crash del server o blocchi dell'applicazione durante la finestra di lezione (08:00 – 18:00). | Monitoraggio dei log del server di backend durante la fase di test e la dimostrazione del progetto. | DIR-03, DOC-01, STU-01 |

### Requisiti impliciti

| Chi avete intervistato | Cosa ha detto | Requisito che ne avete ricavato |
| --- | --- | --- |
| A.M. | *"I voti devono restare salvati anche se chiudo l'app."* | [NFR-04] |
| G.F. | *"Devo poter ritrovare i voti delle verifiche passate."* | [STU-02] |
| S.C. | *"L'app non deve mostrare i miei voti agli altri studenti."* | [NFR-02] |
| E.P. | *"Uno studente non deve poter modificare i voti."* | [NFR-02] |
| D.B. | *"Le comunicazioni non devono arrivare alla classe sbagliata."* | [STU-05] |

---

## Assunzioni, vincoli e dipendenze

### Assunzioni

| ID | Assunzione | Cosa succede se è falsa |
| --- | --- | --- |
| ASS-01 | L'ITS mantiene una struttura stabile di circa 1.000 studenti, 50 docenti e 30 classi distribuite su circa 10 sedi territoriali | Se il numero raddoppiasse, il dimensionamento dello stack scelto andrebbe rivisto |
| ASS-02 | Gli utenti dispongono di una connessione internet stabile (almeno 4G su smartphone o rete fissa) per l'accesso all'applicazione web | Gli utenti faticano a connettersi all’applicazione o sarebbe addirittura impossibile connettersi |

### Vincoli

| ID | Vincolo | Da dove viene |
| --- | --- | --- |
| VIN-01 | Il budget cloud iniziale è vincolato all'utilizzo dei crediti studenteschi messi a disposizione dal piano promozionale del Cloud Provider | Dalla scelta di provider con piani a pagamento |
| VIN-02 | Esclusione totale dal perimetro di funzionalità del tracciamento delle presenze e dei tirocini | Sono gestiti dai sistemi informativi regionali dell'ITS |

### Dipendenze

| ID | Dipendenza | Serve entro | Chi se ne occupa |
| --- | --- | --- | --- |
| DIP-01 | Disponibilità di un servizio SMTP affidabile per l'invio delle credenziali di attivazione | Prima del collaudo | Mattia Artico e Antonio Mihut |

---

# Seconda parte · Il come

## Stima del carico

### Utenti concorrenti

| Situazione | Utenti concorrenti | Da dove viene il numero |
| --- | --- | --- |
| Uso normale durante la giornata | ~80 - 100 utenti concorrenti attivi contemporaneamente | Stima progettuale |
| Picco delle 9:00 | ~350 - 400 utenti concorrenti  | Studenti che verificano le notifiche, docenti che aprono registri o caricano materiali |
| Fine periodo didattico |  ~150 - 200 utenti concorrenti | Prevalenza di docenti e direzione su inserimento voti e validazione |

### Profilo di carico

| Operazione | Frequente? | Pesante? | Critica? | Note |
| --- | --- | --- | --- | --- |
| Login | Ogni mattina/sessione | No | Sì | Blocca l'accesso se fallisce |
| Apertura verifica | Dipende dal periodo | Per query aggregate | Sì | - |
| Consegna verifica | Dipende dal periodo | Sì | Sì | - |
| Dashboard del Direttore | Sì | Sì | No | - |
| Caricamento materiale | Sì | No | No | Solo link esterni |

---

## Scelte tecnologiche

| Area | Scelta | Alternativa considerata | Perché avete scelto così |
| --- | --- | --- | --- |
| Backend | Express.js | FastAPI/Django | Express unifica JavaScript tra client e server, riducendo il carico cognitivo e accelerando lo sviluppo; è snello e gestisce in modo efficiente le richieste asincrone concorrenti. Python avrebbe imposto un cambio di contesto continuo tra due linguaggi, la gestione di ambienti virtuali, tempi di integrazione più lunghi. |
| Frontend | React con Vite | Angular | React è già noto nel team e ideale per dashboard SPA a ruoli protetti; Vite assicura compilazione istantanea e build statiche leggere. Angular richiede concetti complessi (RxJS, Dependency Injection) rischiosi per le scadenze. |
| Database | SupaBase/PostgreSQL | MongoDB | I dati scolastici sono strettamente relazionali; PostgreSQL garantisce integrità referenziale, vincoli di unicità e consistenza ACID, prevenendo voti orfani o sovrapposizioni d'orario. MongoDB richiederebbe verifiche manuali nel codice rischiando incoerenze. |
| Provider cloud | Microsoft Azure | Render + Supabase + Vercel | È nel programma ITS e offre con piano studenti 100$ di credito a costo zero senza carta di credito, con datacenter in Italia. I PaaS gratuiti causano frammentazione e latenze da *cold start*. |
| Servizi cloud | Microsoft Azure | Macchina Virtuale unica (con Docker Compose) | Azure è un’architettura PaaS gestita: isola i carichi, include SSL automatico, backup del DB e scarica il backend salvando slide e PDF direttamente su Blob Storage. Una VPS Linux richiederebbe gestione manuale di Nginx, certificati SSL, OS e backup, sottraendo tempo allo sviluppo del CRM. |
| Regione (cloud) | Italia | Tutte le altre | Assicura latenza minima per utenti in Italia e piena conformità GDPR/AGID sulla sovranità dei dati scolastici sul territorio nazionale.  |
| Servizio esterno | Resend (Email transazionali via API) | Azure Communication Services / Server SMTP autonomo (Nodemailer con Gmail) | Servizio dedicato per credenziali e notifiche con piano free (100 email/giorno), API REST immediata in Node.js ed elevata affidabilità di recapito. Server SMTP o account personali finiscono nello spam; Azure Communication Services richiede una lunga configurazione DNS e verifica dominio. |

---
