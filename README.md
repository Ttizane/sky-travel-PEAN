# ✈️ SkyTravel - Sistema di Prenotazione Voli

Sistema completo di prenotazione voli online sviluppato con stack PEAN (PostgreSQL, Express, Angular, Node.js).

## 📋 Descrizione

SkyTravel è un'applicazione web full-stack per la gestione e prenotazione di voli aerei. Il sistema permette agli utenti di cercare voli, prenotare biglietti, gestire profili passeggeri e effettuare pagamenti online. Include funzionalità amministrative per la gestione di compagnie aeree, aeroporti, aerei e voli.

## 🚀 Funzionalità Principali

### Per gli Utenti
- 🔍 **Ricerca Voli**: Ricerca di voli per origine, destinazione e data
- 🎫 **Prenotazione Biglietti**: Sistema completo di booking con selezione posti
- 👤 **Gestione Profilo**: Creazione e modifica profilo passeggero
- 💳 **Pagamenti Online**: Integrazione con Stripe per pagamenti sicuri
- 📧 **Autenticazione**: Sistema di login/registrazione con JWT

### Per gli Amministratori
- 🏢 **Gestione Compagnie**: CRUD completo per compagnie aeree
- ✈️ **Gestione Flotta**: Amministrazione aerei e modelli
- 🗺️ **Gestione Aeroporti**: Configurazione aeroporti e tratte
- 📅 **Gestione Voli**: Creazione e scheduling voli
- 📊 **Statistiche**: Dashboard con analytics

### Per le Compagnie Aeree
- ✈️ **Gestione Flotta Propria**: Amministrazione dei propri aerei
- 📋 **Gestione Voli**: Creazione e modifica dei propri voli
- 📊 **Report Prenotazioni**: Visualizzazione prenotazioni

## 🛠️ Tecnologie Utilizzate

### Frontend
- **Angular 18+** - Framework SPA
- **TypeScript** - Linguaggio principale
- **CSS3** - Styling

### Backend
- **Node.js** - Runtime JavaScript
- **Express.js** - Framework web
- **TypeScript** - Linguaggio principale
- **JWT** - Autenticazione
- **Multer** - Upload file

### Database
- **PostgreSQL** - Database relazionale
- **Supabase** - Hosting database

### Pagamenti
- **Stripe** - Gateway pagamenti

### DevOps
- **Docker** - Containerizzazione
- **Docker Compose** - Orchestrazione container

## 🚀 Installazione e Avvio

### Prerequisiti
- Node.js 18+
- npm o yarn
- PostgreSQL (o account Supabase)
- Docker e Docker Compose (opzionale)

### Configurazione

1. **Clona il repository**
```bash
git clone https://github.com/Ttizane/sky-travel-PEAN.git
cd sky-travel-PEAN
```

2. **Configura le variabili d'ambiente**
```bash
# Backend
cd backend
cp .env.example .env
# Modifica .env con le tue credenziali
```

3. **Configura il database**
- Crea un database PostgreSQL
- Esegui gli script in `db/init/` in ordine numerico

### Avvio con Docker (Consigliato)

```bash
# Dalla root del progetto
docker-compose up --build
```

L'applicazione sarà disponibile su:
- **Frontend**: http://localhost:4200
- **Backend**: http://localhost:3000

### Avvio Manuale

**Backend:**
```bash
cd server
npm install
npm run dev
```

**Frontend:**
```bash
cd client
npm install
npm start
```

## 🔐 Credenziali di Default

Dopo l'inizializzazione del database:

**Admin:**
- Email: `admin@esempio.it`
- Password: `admin`

## 📊 Database

Il database include:
- Tabelle per utenti, passeggeri, compagnie aeree
- Tabelle per aerei, modelli, aeroporti
- Tabelle per tratte, voli, biglietti
- Trigger per gestione automatica timestamp
- Job schedulati per aggiornamento stato voli

Vedi i diagrammi in `db/` per la struttura completa.

## 🔧 Script Disponibili

### Backend
```bash
npm run dev          # Avvia in modalità sviluppo
npm run build        # Build per produzione
npm start            # Avvia versione production
```

### Frontend
```bash
npm start            # Avvia dev server (porta 4200)
npm run build        # Build per produzione
npm test             # Esegui test
```

## 🌐 Esempi API Endpoints

### Autenticazione
- `POST /api/auth/register` - Registrazione utente
- `POST /api/auth/login` - Login
- `POST /api/auth/refresh` - Refresh token

### Voli e Prenotazioni
- `GET /api/soluzioni` - Ricerca voli
- `POST /api/booking` - Crea prenotazione
- `GET /api/booking/:id` - Dettagli prenotazione

### Checkout
- `POST /api/checkout/create-payment-intent` - Crea intent pagamento
- `POST /api/checkout/confirm` - Conferma prenotazione

### Admin (richiede ruolo admin)
- `GET /api/admin/*` - Vari endpoint amministrativi

Vedi la documentazione completa in `Documentation.pdf`.

## 🤝 Contributi

Progetto sviluppato per il corso di Tecnologie e Applicazioni Web.

## 👥 Autori

- Zanetti Riccardo - [Ttizane](https://github.com/Ttizane)
- Pasqual Francesco Giovanni - [sabscarpenter](https://github.com/sabscarpenter)

**Nota**: Questo è un progetto didattico. Non utilizzare in produzione senza appropriate misure di sicurezza aggiuntive.
