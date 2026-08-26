# CLIMAORO App
**L'interfaccia mobile nativa per la gestione diretta e centralizzata del riscaldamento.**

---

## Links

- **Sito web:** [https://UVAVIVA.github.io/CLIMAORO/](https://UVAVIVA.github.io/CLIMAORO/)
- **Progetto principale:** [https://github.com/UVAVIVA/CLIMAORO](https://github.com/UVAVIVA/CLIMAORO)

---

## La Visione

Nelle prime versioni di CLIMAORO, l'unico modo per interagire con il sistema era rappresentato dalle dashboard di Home Assistant. Sebbene complete, le schermate risultavano affollate, complesse da navigare da smartphone e prive dell'immediata reattività richiesta nell'uso quotidiano.

Il riscaldamento incide per il 60-70% sui consumi energetici di un'abitazione: merita un'interfaccia dedicata, essenziale ed efficace.

**CLIMAORO App** nasce con un obiettivo preciso: eliminare la dipendenza da server centrali o interfacce generiche per offrire un controllo immediato direttamente da telefono. L'applicazione dialoga via Wi-Fi locale direttamente con i termostati ESPHome e con il motore C, garantendo un'esperienza rapida, pulita e sempre disponibile.

---

## Foto

[![App 1](images/00b52f18-fcd2-4f22-bc78-fc6dbafb9023.jpg)](images/00b52f18-fcd2-4f22-bc78-fc6dbafb9023.jpg)
[![App 2](images/48d5ad94-720a-4e18-af88-9c372f740eee.jpg)](images/48d5ad94-720a-4e18-af88-9c372f740eee.jpg)
[![App 3](images/91745b8e-12b7-4d81-99e9-c87701b7c1f8.jpg)](images/91745b8e-12b7-4d81-99e9-c87701b7c1f8.jpg)
[![App 4](images/a965ce88-6679-4776-bdce-42e957b538df.jpg)](images/a965ce88-6679-4776-bdce-42e957b538df.jpg)

---

## Struttura dell'Applicazione

L'esperienza utente è organizzata in sezioni focalizzate e prive di distrazioni:

| Schermata | Descrizione |
| --- | --- |
| **Dashboard Generale** | Panoramica sintetica di tutti i termostati di casa: temperatura corrente, umidità relativa, stato operativo (accesso/spento) e stato di connettività in tempo reale. |
| **Controllo Singolo Termostato** | Gestione puntuale della singola stanza: cambio setpoint, accensione/spegnimento e selezione modalità HVAC (*Caldo*, *Fresco*, *Automatico*, *Deumidificazione*, *Ventilazione*). |
| **Pannello ClimaOro** | Il centro di controllo dell'algoritmo: gestione appartamenti, aggregazione stanze in gruppi, definizione dei pesi e matrice oraria settimanale (*Comfort*, *Eco*, *Autonomo*), oltre al selettore Master. |
| **Automazioni & Notifiche** | Configurazione di regole condizionali locali (es. attivazione al di sotto di soglie critiche) e ricezione di notifiche push sugli eventi di sistema. |

---

## Scelte Tecnologiche

- **Flutter Framework**: Codice sorgente unificato per un'esperienza d'uso fluida, nativa e performante su dispositivi mobili.
- **Comunicazione REST / HTTP Diretta**: L'applicazione sfrutta i web server nativi dei singoli ESPHome e le API REST del motore C. Nessun protocollo esotico o middleware intermedio.
- **Operatività Standalone**: Se il motore centralizzato non è configurato o temporaneamente irraggiungibile, l'app continua a interagire direttamente con i singoli termostati senza bloccare l'impianto.

---

## Installazione e Avvio

### Da APK (consigliato)

1. Scarica l'APK più recente dalla cartella `releases/`
2. Installa sul telefono Android (attiva "Fonti sconosciute" se necessario)
3. All'avvio, l'app chiede l'IP del motore (se configurato)

### Da sorgente

```bash
flutter pub get
flutter build apk --release
```

L'APK sarà in `build/app/outputs/flutter-apk/app-release.apk`.

### Prima Configurazione

Al primo avvio viene richiesto l'indirizzo IP del motore CLIMAORO. Il parametro può essere inserito subito o configurato successivamente all'interno del menu *Impostazioni*.

---

## Licenza e Responsabilità

**CLIMAORO © 2026 by UVAVIVA** · Licenza: **MIT con Condizione di Attribuzione**

**Termini**
- ✅ Attribuzione richiesta (nel codice e sui dispositivi commerciali)
- ✅ Uso commerciale permesso (con attribuzione)
- ✅ Modifiche e derivati permessi
- ✅ Uso, copia, distribuzione e vendita permessi

**Disclaimer**
Questo progetto è fornito **così com'è**, a scopo educativo e sperimentale.
- ⚠️ Non certificato per uso produttivo
- ⚠️ Nessuna garanzia di alcun tipo
- ⚠️ L'utente si assume ogni rischio relativo all'uso del software e al rispetto delle normative locali

**Sviluppato da:** [UVAVIVA](https://github.com/UVAVIVA)

---

**Costruito con passione, dal nulla.**
