# Wizard Open Data Comuni

Procedura guidata statica, in una singola pagina HTML, per aiutare un Comune a pubblicare i primi CSV open data in modo pulito e già predisposto per l'arricchimento semantico.

## Cosa fa

1. **Tema** — l'utente sceglie l'argomento (anagrafe, sicurezza stradale, trasparenza, salute, mobilità, turismo, infrastrutture...)
2. **Dataset** — vede una lista di dataset proposti per quel tema, scelti perché non duplicano dati già disponibili su Cruscotto Italia o su registri regionali
3. **Modello** — visualizza i campi del CSV (nome, tipo, obbligatorietà, proprietà ontologica di riferimento) e scarica un file `.csv` già compilato con 4-5 righe di esempio
4. **Verifica** — link diretto a [SIMBA](https://chatbot.dati.gov.it/chatbot/) per validare il file compilato

## Perché questi dataset

Ogni dataset proposto è stato selezionato incrociando:
- il corpus di CSV reali pubblicati da Comuni italiani su portali CKAN (Lecce, Matera, Comuni dei Messapi)
- gli schemi CSV maturi del progetto [comune-metrics](https://github.com/piersoft/comune-metrics)
- le ontologie ufficiali AGID pubblicate su [dati-semantic-assets](https://github.com/italia/dati-semantic-assets)

Sono esclusi i temi già coperti da fonti nazionali/regionali (bilancio via SIOPE, numerazione civica via ANNCSU, bandi via ANAC, PNRR via ReGiS, ecc.): l'obiettivo non è la quantità di dataset pubblicati, ma dati di qualità che aggiungono davvero informazione.

## Uso

Nessuna installazione. Basta aprire `wizard-opendata-comuni.html` in un browser, oppure pubblicarlo così com'è su GitHub Pages.

Tutti i dati (temi, dataset, campi, esempi) sono incorporati nel file: funziona anche offline.

## Struttura del file

Un solo file HTML autosufficiente:
- CSS con variabili per il tema visivo
- un oggetto `DATASETS` con tutti i dataset, i campi e le righe di esempio
- logica di navigazione tra i 4 passi e generazione del CSV al volo (`Blob` + download)

## Validazione

I CSV scaricati sono già pensati per superare i controlli del validatore [CSV-to-RDF](https://piersoft.github.io/CSV-to-RDF/validatore-csv-pa.html) (colonna identificatore univoco, formato date ISO 8601, encoding UTF-8) e per essere poi arricchiti semanticamente su SIMBA.

## Licenza

CC BY 4.0 — dati e testi liberamente riutilizzabili citando la fonte.
