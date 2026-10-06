# PRD di ScuolaChill · Team DevRoadsters

## Informazioni sul documento

|  |  |
| --- | --- |
| **Prodotto** | ScuolaChill |
| **Team** | DevRoadsters |
| **Autori** | Antonio Mihut - Mattia Artico |
| **Versione** | 1.0 |
| **Data** | 25/09/2026 |
| **Stato** | *Bozza*  |

### Storico delle versioni

| Versione | Data | Autore | Cosa è cambiato e perché |
| --- | --- | --- | --- |
| 1.0 | 25/09/2026 | Mattia Artico e Antonio Mihut | Prima stesura (resta da vedere).  |
| 1.1 | 26/09/2026 | Mattia Artico e Antonio Mihut | Definizione dei destinatari e del contesto d'uso |
| 1.2 | 29/09/2026 | Mattia Artico e Antonio Mihut | Definizione della panoramica e dei casi d'uso |
| 1.3 | 30/06/2026 | Mattia Artico | Definizione dei requisiti funzionali |
|  |  |  |  |

---

# Prima parte · Il cosa

## Scopo e perimetro

### Perché esiste ScuolaChill

**Dal lato business.** Fornisce un set di strumenti utilizzabili da una scuola, ovvero dirigente, docenti e studenti, per svolgere le molteplici attività didattiche di un corso di **Istituto Tecnologico Superiore**: gestire le classi, il materiale didattico, il percorso didattico (con verifiche e voti).

**Dal lato tecnico.** *Cosa copre il sistema, in grandi linee. Due o tre frasi. (???)*

### Cosa è incluso

- Gestione di classi
- Gestione di docenti
- Gestione di studenti
- Gestione di orario
- Gestione di attività nel calendario scolastico: attività didattiche, gite ed escursioni
- Gestione di eventi extra
- Gestione manuale di presenze
- Gestione di voti e pagelle
- Autenticazione mail-password

### Cosa non è incluso

- Strumenti di e-learning (come quiz interattivi)
- Controllo presenze tramite badge
- Comunicazioni interne e con le famiglie
- Gestione di tirocini curriculari
- Gestione contabilità/pagamenti
- Gestione inventario
- Reportistica ed esportazione avanzata

---

## Stakeholder

| Stakeholder | Cosa fa | Cosa gli interessa | Come lo/li coinvolgete |
| --- | --- | --- | --- |
| Direttore | Configura la scuola, crea docenti e studenti, organizza le classi e consulta la situazione generale | Avere una visione completa e aggiornata della scuola, ridurre il lavoro amministrativo e garantire la correttezza dei dati | Validazione dei requisiti, revisione dei prototipi e collaudo delle funzioni principali |
| Docente | Gestiscono il materiale didattico, creano verifiche, assegnano voti e consultano le classi | Caricare rapidamente i materiali, gestire le verifiche senza errori e inserire i voti in modo semplice e sicuro | Osservazione delle attività quotidiane, test dei flussi e raccolta di feedback |
| Studente | Consultano materiali, svolgono verifiche e controllano i propri voti | Usare il sistema facilmente anche da smartphone, non perdere il lavoro e vedere sempre informazioni aggiornate | Usabilità e collaudo sul campo |
| Docente del corso | Valida il PRD e verifica che le scelte progettuali rispettino la traccia e gli obiettivi didattici | Chiarezza dei requisiti, correttezza dell'architettura e completezza della documentazione | Presentazione del PRD, revisioni periodiche, domande di chiarimento e approvazione delle milestone |
| Collaudatore del primo anno | Usano ScuolaChill come utenti reali durante le prove di collaudo | Completare le attività senza aiuto, capire subito cosa fare e non perdere dati durante le verifiche | Sessioni di collaudo osservate, raccolta degli errori |
| Team di sviluppo | Progetta, implementa, testa e mantiene il sistema | Requisiti chiari, scelte tecniche sostenibili, sicurezza e facilità di manutenzione | Riunioni di analisi, revisione del codice, test automatici e aggiornamento dello storico delle decisioni |

---

## Destinatari e contesto d'uso

### La scuola che avete immaginato

*Descrivi la scuola per cui progettate. Che tipo di istituto è, dove si trova, come si organizza la giornata. Questi dati tornano nella stima del carico, quindi scegli numeri che poi userai davvero.*

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

**ScuolaChill è un programma pensato per rendere più semplice la gestione quotidiana dell’ITS Digital Academy Mario Volpato, che conta 13 sedi.**

L’idea è avere un unico posto dove poter organizzare e controllare tutte le informazioni importanti della scuola: studenti, classi, docenti, lezioni, presenze, attività e comunicazioni.

Invece di avere informazioni sparse tra diversi strumenti o documenti, ScuolaChill permette di avere tutto organizzato e facilmente consultabile, anche considerando le diverse sedi dell’ITS.

Il nostro obiettivo è **ridurre il lavoro manuale, evitare confusione e rendere più veloce la gestione della scuola**, sia per chi lavora nell’amministrazione sia per chi si occupa della didattica.

In poche parole, **ScuolaChill vuole diventare un punto di riferimento unico per la gestione dell’ITS**, semplice da usare e costruito sulle esigenze reali della scuola.

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

#### DIR-05 · Monitorare presenze e andamento frequenza

- **User flow:**
    1. Il Direttore apre la sezione Presenze.
    2. Seleziona sede, corso o classe.
    3. Visualizza il prospetto delle presenze, delle assenze e dei ritardi degli studenti.
    4. Seleziona un singolo studente per verificarne il monte ore e l'andamento.
- **Scenario principale:** Il Direttore vuole controllare l'andamento della frequenza di una classe ITS. Accede alla sezione e verifica la situazione delle presenze, individuando tempestivamente chi rischia di non raggiungere il limite minimo di ore stabilito.
- **Scenari alternativi:**
    - Lezione non ancora verbalizzata dal docente → avviso di presenze non inserite.
    - Periodo privo di dati → messaggio informativo.

#### DIR-06 · Consolidare e approvare le pagelle

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

#### DOC-02 · Registrare le presenze (Appello manuale)

- **User flow:**
    1. Il Docente apre la lezione del giorno su ScuolaChill.
    2. Visualizza l'elenco degli studenti della classe.
    3. Registra lo stato di ciascuno studente tra presente, assente o ritardo.
    4. Conferma l'elenco.
    5. Il sistema registra e archivia i dati di frequenza.
- **Scenario principale:** La docente Giulia inizia la lezione in aula ed effettua l'appello tramite il gestionale. Registra chi è presente, le assenze e l'orario di arrivo di chi è in ritardo, confermando poi il registro di giornata.
- **Scenari alternativi:**
    - Ingresso posticipato di uno studente → aggiornamento del registro con inserimento del ritardo.
    - Errore di digitazione → modifica della voce prima della chiusura definitiva del registro.

#### DOC-03 · Pianificare attività didattiche e date verifiche

- **User flow:**
    1. Il Docente apre la sezione Calendario della propria classe.
    2. Crea una nuova attività didattica o fissa una data per una verifica in aula.
    3. Inserisce titolo, materia, data e descrizione degli argomenti.
    4. Salva l'attività a calendario.
- **Scenario principale:** Il docente Luca stabilisce la data di una prova scritta in aula. Inserisce l'attività sul calendario con l'elenco degli argomenti trattati, consentendo agli studenti di prendere nota della scadenza e organizzare lo studio.
- **Scenari alternativi:**
    - Sovrapposizione con un'altra verifica o evento → avviso di data già impegnata.
    - Dati obbligatori mancanti → salvataggio bloccato.

#### DOC-04 · Registrare le valutazioni (Registro voti)

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

#### DOC-05 · Consultare le classi assegnate

- **User flow:**
    1. Il Docente apre la sezione Le mie classi.
    2. Seleziona una classe specifica.
    3. Visualizza l'elenco degli studenti iscritti.
    4. Consulta le attività pianificate e lo storico delle valutazioni.
- **Scenario principale:** Il docente Marco deve preparare una sequenza didattica. Accede alla scheda della propria classe per rivedere l'elenco degli allievi, le scadenze pianificate e i risultati ottenuti fino a quel momento.
- **Scenari alternativi:**
    - Classe non ancora assegnata → messaggio informativo.
    - Aggiornamento dell'elenco studenti → sincronizzazione automatica dei nominativi.

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

#### STU-02 · Controllare le proprie presenze

- **User flow:**
    1. Lo Studente accede alla sezione Presenze.
    2. Visualizza l'elenco delle lezioni frequentate.
    3. Controlla il computo complessivo di assenze, ritardi e monte ore.
    4. Filtra i dati per periodo didattico.
- **Scenario principale:** Antonio vuole verificare il proprio monte ore per accertarsi di mantenere la soglia minima di frequenza richiesta dal biennio ITS. Consulta la sezione e visualizza quante ore di assenza ha maturato.
- **Scenari alternativi:**
    - Lezione recente non ancora verbalizzata dal docente → stato indicato come non registrato.
    - Assenza di registrazioni nel periodo selezionato → messaggio di dati non disponibili.

#### STU-03 · Consultare il registro valutazioni

- **User flow:**
    1. Lo Studente apre la sezione Valutazioni.
    2. Visualizza i voti conseguiti nelle diverse materie.
    3. Seleziona una materia per consultare il dettaglio delle singole verifiche svolte.
- **Scenario principale:** Dopo una verifica in aula, Antonio entra nella propria area personale per visualizzare il voto inserito dal docente e controllare la media dei risultati ottenuti nella materia.
- **Scenari alternativi:**
    - Voto non ancora pubblicato dal docente → voce indicata come in attesa di esito.
    - Nessuna valutazione registrata → messaggio informativo.

#### STU-04 · Consultare la pagella

- **User flow:**
    1. Lo Studente accede alla sezione Pagella.
    2. Seleziona il periodo concluso.
    3. Visualizza i voti finali per ciascuna materia e l'esito approvato dalla direzione.
- **Scenario principale:** A conclusione del semestre didattico, Antonio consulta la propria pagella definitiva validata dal Direttore, verificando il superamento di tutte le materie del periodo.
- **Scenari alternativi:**
    - Pagella non ancora consolidata o confermata → indicazione di documento in lavorazione.
    - Errore temporaneo di connessione o caricamento → messaggio di errore e possibilità di riprovare.

---

## Requisiti funzionali

### Le user story della traccia

| ID | Storia | AC aggiunti dal team | Note |
| --- | --- | --- | --- |
| DIR-01 | Gestire classi e sedi | *…* | *…* |
| DIR-02 | Gestire docenti e studenti | *…* | *…* |
| DIR-03 | Gestire orario e calendario didattico | *…* | *…* |
| DIR-04 | Gestire eventi extra | *…* | *…* |
| DIR-05 | Monitorare presenze e andamento frequenza | *…* | *…* |
| DIR-06 | Consolidare e approvare le pagelle | *…* | *…* |
| DOC-01 | Consultare il proprio orario | *…* | *…* |
| DOC-02 | Registrare le presenze (Appello manuale) | *…* | *…* |
| DOC-03 | Pianificare attività didattiche e date verifiche | *…* | *…* |
| DOC-04 | Registrare le valutazioni (Registro voti) | *…* | *…* |
| DOC-05 | Consultare le classi assegnate | *…* | *…* |
| STU-01 | Consultare orario e calendario | *…* | *…* |
| STU-02 | Controllare le proprie presenze | *…* | *…* |
| STU-03 | Consultare il registro valutazioni | *…* | *…* |
| STU-04 | Consultare la pagella | *…* | *…* |


