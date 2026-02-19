# Portale Documentazione Tecnica - Corsi Custom S.p.A.

## Descrizione
Repository ufficiale per la gestione, il versionamento e la pubblicazione dei corsi tecnici presales dedicati ai dispositivi telematici Custom S.p.A. e alle relative integrazioni software (XML via POST Web Service, protocollo Custom). 
L'infrastruttura adotta il paradigma *Docs-as-Code*, garantendo un ambiente scalabile e facilmente manutenibile.

## Indice dei Corsi
* **Corso Tecnico Custom Edge RT (Firmware V11.1)**: [🔗 Clicca qui per navigare il portale live](https://github.com/ivanrobuschi-custom/course_project/)
  * Normativa, aggiornamenti firmware, architettura hardware, setup di rete, troubleshooting e gestione disallineamenti server.
* *(In pianificazione)* Integrazione KeepUp Smart
* *(In pianificazione)* Developer Portal API & XML

## Architettura Tecnica
Il progetto è compilato tramite lo Static Site Generator **MkDocs** accoppiato al framework **Material for MkDocs**. 
Tutti i sorgenti sono redatti in formato Markdown (`.md`), permettendo un aggiornamento rapido dei log di errore, dei payload XML e degli script Node.js/Python di interfacciamento.

### Struttura del File System
* `docs/`: Root della documentazione esposta. Contiene tutti i file Markdown strutturati per modulo.
* `docs/resources/`: Directory pubblica contenente gli allegati scaricabili dai dealer (es. manuali PDF e specifiche tecniche).
* `mkdocs.yml`: File di configurazione per il routing di navigazione, i metadati e i plugin del sito.

*(Nota: Le cartelle contenenti appunti interni o file non epurati sono escluse dal versionamento tramite `.gitignore` e non sono presenti in questo repository).*

## Istruzioni di Sviluppo e Deploy

### 1. Esecuzione Locale (Test)
Per testare i file Markdown o le modifiche alla struttura di navigazione prima di renderle pubbliche, avviare il server locale:
```bash
mkdocs serve