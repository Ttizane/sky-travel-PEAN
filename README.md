# ✈️ SkyTravel

Sistema completo di prenotazione voli online sviluppato con stack PEAN (PostgreSQL, Express, Angular, Node.js).

## Descrizione

SkyTravel è un’applicazione web a tre livelli — client, server e database — progettata come Single Page Application (SPA) per la gestione e prenotazione di voli aerei. Si tratta di una piattaforma moderna, dotata di sistemi di autenticazione sicuri e di un’interfaccia grafica d’avanguardia, progettata per offrire un’esperienza utente fluida e intuitiva. Il sistema permette agli utenti di cercare voli, prenotare biglietti, gestire profili passeggeri ed effettuare pagamenti online. Include inoltre funzionalità amministrative avanzate per la gestione di compagnie aeree, aeroporti, aerei e voli.

### Panoramica delle funzionalità e dei ruoli utente

All’interno dei file di documentazione sono presenti immagini e diagrammi che mostrano l’intera applicazione in esecuzione, oltre al **workflow progettato per ogni tipologia di utente**. Queste risorse consentono di comprendere visivamente la struttura del sistema e le interazioni principali tra le varie componenti.

#### Utenti passeggeri
I passeggeri possono **creare un profilo personale**, successivamente **visualizzarlo e modificarlo**. 
Gli utenti possono **ricercare voli** e visualizzare **itinerari completi** in base a parametri specifici di **partenza, arrivo e date**.  
Una volta trovato un volo, è possibile **prenotare biglietti**, selezionando i **posti** desiderati per ogni tratta.  
Il sistema consente inoltre di **effettuare pagamenti online** e di **consultare i biglietti acquistati**.  

#### Compagnie aeree
Le compagnie aeree vengono **create dall’amministratore** e **abilitate tramite invito**.  
Dopo il primo accesso, la compagnia completa i propri dati e può in seguito **visualizzare e modificare il proprio profilo**.  
Ogni compagnia può:
- **Gestire la propria flotta aerea**, aggiungendo o rimuovendo modelli e singoli aerei.  
- **Definire e gestire le tratte aeree** di interesse.  
- **Pianificare e gestire i voli** associati alla propria flotta.  
- **Visualizzare statistiche dettagliate** sull’andamento della compagnia, come prestazioni dei voli, utilizzo della flotta e numero di passeggeri.

#### Amministratore
L’amministratore ha **accesso completo al sistema** e può gestire ogni tipologia di utente.  
In particolare, può:
- **Visualizzare e modificare** i profili dei passeggeri e delle compagnie aeree.  
- **Creare nuove compagnie aeree** e inviare **inviti di registrazione** per consentire loro di accedere al sistema.  

L’amministratore rappresenta quindi il punto di controllo principale per la gestione e il mantenimento della piattaforma.

## Tecnologie Utilizzate

### Frontend
- **Angular 18+** – Framework SPA per la gestione del client e del routing
- **TypeScript** – Linguaggio per la logica dei componenti
- **HTML5** – Struttura e markup delle pagine
- **CSS3** – Utilizzato per i ritocchi finali e la personalizzazione dello stile
- **Tailwind CSS** – Framework per la gestione degli stili
- **DaisyUI** – Libreria di componenti UI basata su Tailwind per un design moderno e coerente

### Backend
- **Node.js** – Runtime JavaScript lato server
- **Express.js** – Framework web
- **TypeScript** – Linguaggio per la logica backend
- **JWT (JSON Web Token)** – Sistema di autenticazione e gestione delle sessioni
- **Multer** – Middleware per l’upload di file
- **bcrypt** – Libreria per la cifratura e la gestione sicura delle password

### Database
- **PostgreSQL** – Database relazionale per la gestione dei dati  
- **Supabase** – Servizio di hosting e amministrazione del database PostgreSQL, utilizzato per la distribuzione online; in alternativa, il database può essere eseguito direttamente in locale tramite **Docker**

### Pagamenti
- **Stripe** – Gateway per la gestione dei pagamenti online

### DevOps
- **Docker** – Containerizzazione dell’applicazione  
- **Docker Compose** – Orchestrazione e gestione dei container  
- **Git** – Sistema di versionamento del codice sorgente  
- **GitHub** – Piattaforma per l’hosting del repository e la collaborazione tra sviluppatori  
- **Visual Studio Code** – Ambiente di sviluppo utilizzato per la scrittura, il debugging e la gestione del progetto

## Aspetti di Interesse e Caratteristiche Distintive

Uno degli elementi che consideriamo di maggior valore all’interno del progetto *SkyTravel* è il **sistema di autenticazione**, realizzato con un approccio moderno, sicuro e altamente personalizzato.

Il sistema di autenticazione è basato su una **combinazione di token di accesso e token di refresh**:  
- i **token di accesso** vengono salvati nel **LocalStorage** del browser e gestiti dal client per l’autenticazione immediata;  
- i **token di refresh** sono invece memorizzati all’interno di **cookie HTTP-only**, protetti con attributi **SameSite** e **path specifici**, per ridurre drasticamente i rischi legati a vulnerabilità come **XSS** e **CSRF**.  

Questo meccanismo è ulteriormente potenziato dall’utilizzo di una **tabella delle sessioni** nel database, che funge da **whitelist** e consente di gestire e verificare in modo centralizzato le sessioni attive.  
Tutti i token vengono **firmati con JWT**, utilizzando una chiave di firma **rigenerata casualmente a ogni riavvio del server**, garantendo un livello di sicurezza aggiuntivo.

L’integrazione con il frontend è stata realizzata tramite **interceptor** e **guardie di rotta (Route Guards)** in Angular, che permettono di collegare perfettamente il lato client con la logica di autenticazione del server, mantenendo prestazioni elevate e massima protezione.

Durante lo sviluppo abbiamo anche valutato un’**alternativa sperimentale**, basata su un **token unico “spezzato”**, in cui la parte principale del token verrebbe salvata nel LocalStorage e la **firma associata** in un cookie separato: una soluzione concepita per aumentare ulteriormente la resistenza ad attacchi **XSS parziali** o **CSRF**, anche se la nostra implementazione attuale già minimizza tali rischi.

Per ulteriori approfondimenti sulla **sicurezza dell’applicazione web**, sulla **gestione delle sessioni** e sul **sistema di autenticazione**, è possibile consultare **uno qualsiasi dei file di documentazione** presenti nel repository.

## Documentazione del Progetto

Per chi fosse interessato ad approfondire gli aspetti tecnici dell’applicazione, sono disponibili **file di documentazione dedicati** che illustrano nel dettaglio la progettazione e l’implementazione delle diverse componenti del sistema.

In particolare, è possibile consultare:
- l’**architettura completa del sistema**, che illustra l’interazione tra client, server e database;  
- la **progettazione del database**;
- la **parte frontend Angular**, con la documentazione delle **Route Guards**, degli **interceptor** e del **sistema di routing** per la gestione delle componenti;  
- la **documentazione delle API**;  
- il **sistema di autenticazione**;

Per chi invece desidera **avviare il progetto in locale**, è sufficiente seguire le istruzioni contenute nel file **“AVVIO.txt”**, che descrive passo per passo la configurazione dell’ambiente e l’esecuzione dei vari servizi.

## Autori

- Zanetti Riccardo - [Ttizane](https://github.com/Ttizane)
- Pasqual Francesco Giovanni - [sabscarpenter](https://github.com/sabscarpenter)

**Nota**: Questo è un progetto didattico. Non utilizzare in produzione senza appropriate misure di sicurezza aggiuntive.
