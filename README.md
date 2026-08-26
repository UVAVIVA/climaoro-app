# CLIMAORO App

App Flutter per la gestione della climatizzazione centralizzata CLIMAORO.

## Storia

CLIMAORO nasce come sistema di climatizzazione centralizzata per apartamenti multiproprieta'. Inizialmente l'interfaccia era integrata in Home Assistant. Questa app Flutter la sostituisce completamente, offrendo un'esperienza nativa su Android.

L'app si collega direttamente ai termostati ESPHome (via HTTP) e al motore decisionale ESP32-S3 (via API REST), senza bisogno di Home Assistant.

## Funzionalita'

### Schermata Principale
- Lista di tutti i termostati con temperatura, umidita', modalita' e stato
- Indicatore online/offline per ciascun dispositivo
- Aggiunta/rimozione dispositivi

### Termostato
- Controllo modalita' (OFF / HEAT / COOL / AUTO / DRY / FAN_ONLY)
- Controllo ventola (ON/OFF, modalita' auto)
- Impostazione target temperature (high/low)
- Lettura sensori in tempo reale

### Collettore
- Gestione valvole multiple
- Stato valvole on/off

### ClimaOro (Centralizzato)
- Gestione appartamenti, gruppi e stanze
- Calendario 7x24 (COMFORT / ECO / AUTONOMO)
- Pesi stanze e soglia gruppi
- Delta accensione/spegnimento per comfort/eco
- Toggle master (attiva/disattiva il motore)

### Automazioni
- Regole basate su temperatura, ora, giorno
- Azioni: accendi/spegni, cambia modalita', imposta temperatura
- Notifiche push

### Configurazione Motore
- IP del motore ESP32-S3 (configurabile a runtime)
- Stato motore (master on/off, uptime, SNTP sync)
- Endpoint `/api/config/reset` per emergenze

## Installazione

### Da APK (consigliato)

1. Scarica l'APK piu' recente dalla cartella `releases/`
2. Installa sul telefono Android (attiva "Fonti sconosciute" se necessario)
3. All'avvio, l'app chiede l'IP del motore (se configurato)

### Da sorgente

```bash
flutter pub get
flutter build apk --release
```

L'APK sara' in `build/app/outputs/flutter-apk/app-release.apk`.

## Configurazione

### IP Motore
L'IP del motore si configura dalla schermata "Configurazione" nell'app. Non e' necessario ricompilare.

### Dispositivi
I dispositivi (termostati) si aggiungono/rimuovono dall'app. L'elenco nel motore e' separato (hardcoded nel firmware `devices.c`).

## Architettura

```
App Flutter (questa)
       │
       ├── HTTP ──> Termostati ESPHome (diretto)
       │
       └── HTTP ──> Motore ESP32-S3 (API REST)
                      │
                      └── HTTP ──> Termostati ESPHome (ciclo 60s)
```

L'app puo' controllare i termostati direttamente (quando il motore e' offline) o tramite il motore (quando e' attivo).

## Prerequisiti

- Flutter SDK ^3.13.1
- Android SDK
- Termostati ESPHome funzionanti nella stessa rete
- (Opzionale) Motore ESP32-S3 con questo firmware

## Dipendenze principali

- `http` - Client HTTP per comunicazione con termostati e motore
- `shared_preferences` - Persistenza locale (IP motore, dispositivi)
- `flutter_local_notifications` - Notifiche push per automazioni

## Licenza

MIT con Condizione di Attribuzione - vedi `LICENSE` e `ATTRIBUZIONE.md`.

## Autore

UVAVIVA - https://github.com/UVAVIVA
