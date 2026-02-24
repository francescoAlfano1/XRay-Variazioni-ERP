# XRay Variazioni – Integrazione Macchina Raggi X con ERP Business Cube

Sistema di integrazione automatica tra una **macchina conta pezzi a raggi X** e il gestionale ERP **Business Cube**.

## 🛠️ Tecnologie
- VB.NET
- Procedure I/E (Import/Export) di Business Cube
- Windows Task Scheduler
- `.bat` + `.bub` per schedulazione

## 📋 Descrizione
La macchina genera durante la giornata file CSV con variazioni di quantità per codici articolo. Il sistema aggrega automaticamente tutte le variazioni giornaliere per articolo, aggiorna le esistenze nel gestionale tramite bolle di movimentazione interna, archivia i file elaborati e invia una e-mail con allegato CSV di riepilogo. L'intero flusso è schedulato e non richiede alcun intervento manuale.

Il progetto è stato preceduto da un **preventivo tecnico formale**, dimostrando capacità di gestione completa del ciclo di vita di un'integrazione professionale.

## ✅ Flusso operativo
1. **Initialize:** legge e valida i CSV, aggrega le variazioni per articolo, interroga il DB per le esistenze pre-importazione, genera `XRay.csv`
2. **Import I/E:** Business Cube importa il file e crea le bolle di movimentazione
3. **Terminate:** arricchisce il file con disponibilità post-importazione, ricrea il file vuoto per il ciclo successivo, pulisce i file obsoleti
4. **Alert:** individua il file del giorno precedente e lo allega all'e-mail di notifica

## ✅ Funzionalità principali
- Aggregazione variazioni giornaliere per codice articolo da CSV multipli
- Validazione struttura file: header, colonne, variazione nulla, USERNAME valorizzato
- Interrogazione database ERP per esistenze pre e post importazione
- Calcolo disponibilità netta
- Generazione bolla di movimentazione interna tramite profilo I/E personalizzato
- Archiviazione automatica con struttura a cartelle per data
- Pulizia ricorsiva automatica file e cartelle più vecchi di 7 giorni
- Invio e-mail automatico con allegato CSV riepilogativo

## 💡 Punti di forza
- Progetto nato da preventivo tecnico formale
- Integrazione completa hardware → file system → ERP → e-mail
- Gestione robusta di tutti i casi anomali
- Zero intervento manuale nel flusso operativo quotidiano

## 🏢 Contesto d'uso
Ambito manifatturiero / magazzino — integrazione macchinario industriale di controllo qualità con ERP Business Cube.

> **Nota:** Business Cube è un gestionale ERP diffuso in ambito manifatturiero italiano.
