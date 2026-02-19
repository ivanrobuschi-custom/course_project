# Specifiche Tecniche RT V11.1

L'aggiornamento normativo alla versione 11.1 delle Specifiche Tecniche per Registratori Telematici (RT) introduce nuove funzionalità e ottimizzazioni per garantire la piena conformità e migliorare l'efficienza operativa dei dispositivi. Questo documento riassume le principali implementazioni tecniche introdotte con il nuovo firmware.

### Reportistica Avanzata (L93 e C.5013)
È stata implementata una nuova funzione di reportistica per la memoria di riepilogo, accessibile tramite la procedura **L93** da tastiera. Questa funzionalità permette di filtrare gli interventi tecnici per codice specifico o di generare un report cumulativo. La medesima funzionalità è disponibile tramite protocollo di comunicazione Custom utilizzando il comando **5013**.

### Segnalazione Esaurimento Memorie
Il sistema ora notifica attivamente l'operatore al raggiungimento del **90% della capacità** della memoria di dettaglio (giornale di fondo) e della memoria di riepilogo (fiscale).
*   Alla soglia del 90%, viene stampato un avviso non fiscale.
*   Il dispositivo attende una conferma di lettura da parte dell'operatore, che può essere fornita tramite i tasti **TOTALE**, **AV CARTA**, il pulsante di **FEED** (ove presente) o via protocollo con il comando **2010**.

### Avviso di Chiusura Fiscale Obbligatoria
Per prevenire la mancata chiusura fiscale entro la mezzanotte, sono stati introdotti due livelli di avviso:
*   **Warning (dalle 23:30):** Per ogni documento commerciale emesso, il display visualizza un messaggio che invita l'operatore a eseguire la chiusura fiscale.
*   **Blocco (dalle 23:58):** Il registratore emette un documento gestionale con un messaggio bloccante e inibisce tutte le operazioni di vendita. L'unica operazione consentita è l'azzeramento fiscale. In caso di documento commerciale aperto, questo viene automaticamente annullato.
Il protocollo di comunicazione è stato esteso con il comando **1530** per permettere al software di cassa di intercettare lo stato di `warning` o `blocco`.

### Esportazione XML delle Memorie Fiscali e di Dettaglio
Le routine per l'esportazione dei dati in formato XML sono state aggiornate per aderire ai nuovi tracciati record ministeriali.
*   L'esportazione del Giornale di Fondo Elettronico (EJ) e della Memoria Fiscale (DFU/MDF) avviene su supporto SD esterno.
*   Le funzioni sono accessibili da tastiera nel menu **P699 > Esercente > Report**.
*   Da protocollo, sono stati introdotti i comandi **6431** (per Memoria Fiscale) e **6432** (per Giornale di Fondo).

### Integrazione Messaggistica RT
È stato integrato un sistema per la ricezione di messaggi provenienti dall'Agenzia delle Entrate.
*   Il dispositivo interroga il server dell'AdE a intervalli regolari (1 ora + un intervallo random fino a 2 ore).
*   I messaggi ricevuti vengono memorizzati, stampati su un documento non fiscale con richiesta di conferma lettura, e inclusi nel report di chiusura fiscale giornaliera.
*   I messaggi persistono fino a un intervento tecnico di cancellazione e sono consultabili nei report della memoria di riepilogo.
*   È possibile forzare il controllo di nuovi messaggi tramite lo shortcut **1602**.

### Attivazione "Fuori Servizio" tramite Shortcut
È stata introdotta la possibilità di impostare il Registratore Telematico nello stato "Fuori Servizio" per periodo di inattività direttamente da tastiera, utilizzando la combinazione **CODICE 1600 + chiave**.

## Risorse e Download
[Scarica Specifiche Tecniche RT V11.1 (.pdf)](../resources/Specifiche_Tecniche_RT_V11.1_24-01-26.pdf)
