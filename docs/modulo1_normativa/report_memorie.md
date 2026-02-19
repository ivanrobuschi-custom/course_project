# Report Tecnico: Gestione Memorie RT V11

L'aggiornamento normativo V11 introduce modifiche sostanziali alla gestione delle memorie del Registratore Telematico, con particolare focus sulla reportistica avanzata, la conformità dei tracciati di esportazione XML e la proattività del dispositivo nella segnalazione dello stato delle memorie.

## 1. Memoria di Riepilogo (Fiscale)

La Memoria di Riepilogo è stata potenziata per offrire una maggiore granularità nella consultazione dei dati storici e degli eventi tecnici.

### 1.1 Reportistica Avanzata (L93)
È stato introdotto il report **L93**, progettato per ottimizzare le operazioni di manutenzione e verifica.
*   **Funzionalità:** Permette di filtrare gli interventi tecnici memorizzati per tipologia o di generare un elenco completo.
*   **Accesso da tastiera:** Procedura shortcut `L93`.
*   **Accesso da Protocollo:** Comando Custom `5013`.
*   **Contenuto:** Include ora anche la messaggistica RT proveniente dal server dell'Agenzia delle Entrate (AdE).

### 1.2 Esportazione XML (MDF)
Le routine di esportazione della Memoria di Riepilogo sono state aggiornate secondo i nuovi schemi XSD ministeriali.
*   **Supporto:** L'esportazione avviene esclusivamente su SD Card esterna.
*   **Modalità di Esportazione:**
    *   Integrale (tutta la memoria).
    *   Per data (intervallo temporale).
    *   Per numero di chiusura (Z).
*   **Accesso da tastiera:** `P699` -> `Esercente` -> `Report` -> `Report MRIEP in XML`.
*   **Comando Protocollo:** `6431`.

## 2. Memoria di Dettaglio (Giornale di Fondo Elettronico - DGFE)

La gestione del Giornale di Fondo è stata allineata alle nuove necessità di estrazione dati per scopi di controllo.

### 2.1 Esportazione XML (EJ)
L'esportazione dei dati analitici segue i nuovi standard di sicurezza e formattazione.
*   **Modalità di Esportazione:**
    *   Integrale.
    *   Per data.
*   **Accesso da tastiera:** `P699` -> `Esercente` -> `Report` -> `Report MDETT in XML`.
*   **Comando Protocollo:** `6432`.

## 3. Monitoraggio Capacità e Segnalazioni

Per prevenire blocchi operativi improvvisi, il sistema implementa un monitoraggio attivo della capacità residua di entrambe le memorie.

### 3.1 Soglia di Attenzione (90%)
Al raggiungimento del **90%** della capacità di una delle due memorie, il dispositivo attiva una procedura di avviso:
1.  **Stampa Automatica:** Emissione di un talloncino di avviso non fiscale.
2.  **Stato di Attesa:** Il dispositivo blocca le operazioni fino alla conferma di lettura.
3.  **Conferma Operatore:** Può essere effettuata tramite:
    *   Tasti fisici: `TOTALE`, `AV CARTA`, o tasto `FEED`.
    *   Protocollo: Comando `2010`.

## 4. Sintesi Comandi e Shortcut

| Funzione | Tasto/Shortcut | Comando Protocollo |
| :--- | :--- | :--- |
| Report Interventi Tecnici | `L93` | `5013` |
| Conferma Avviso 90% | `TOTALE` / `FEED` | `2010` |
| Esportazione XML Memoria Fiscale | Menu `P699` | `6431` |
| Esportazione XML Giornale di Fondo | Menu `P699` | `6432` |

---
**Note Operative:** Tutte le operazioni di esportazione XML richiedono la presenza di una SD Card formattata correttamente e con spazio sufficiente. I file generati seguono la nomenclatura standard prevista dalle specifiche tecniche AdE.
