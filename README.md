# GEOFIN — Track Record Pubblico

Snapshot giornalieri del modello di allocazione sistematica GEOFIN
(Correlation Engine). Trasparenza completa: ogni file mostra regime,
stress score, e l'allocazione intera (pesi per asset) generata quel
giorno per 3 profili di rischio (CONSERVATIVO, MODERATO, CRESCITA),
oltre ai segnali di paper trading.

## Perché esiste

Un backtest, per quanto rigoroso, non prova che un modello funzioni
fuori campione in tempo reale. Questo repo esiste per costruire un
track record verificabile da chiunque, con timestamp che non
controlliamo a posteriori (i commit git), prima di qualunque offerta
commerciale del segnale.

## Cosa NON è

Non è consulenza finanziaria personalizzata. È la pubblicazione, a
scopo di trasparenza e ricerca, dell'output di un modello sistematico.
Nessuna garanzia di performance futura — i risultati passati (backtest
o live) non sono indicativi di risultati futuri. Non è un invito a
comprare o vendere alcun asset.

## Nota metodologica importante

Il modello attuale (allocazione continua basata su stress score, non
più classificazione discreta a 3 regimi) è entrato in produzione il
**2026-09-19**. Snapshot precedenti a questa data, se mai pubblicati,
riflettono una versione diversa del modello e non sono confrontabili
con quelli successivi.

## Nota di trasparenza — interruzione 21/9–1/10/2026

Un bug nella pubblicazione automatica (scriveva su un path locale che
non esiste nell'ambiente di produzione reale) ha impedito la
pubblicazione giornaliera dal 21 settembre al 1 ottobre 2026. I dati di
quei giorni sono reali — recuperati il 2 ottobre dal database di
produzione, che li aveva salvati correttamente il giorno stesso — ma
**non sono stati pubblicati in tempo reale**. I commit relativi a
quelle date porteranno quindi il timestamp del 2 ottobre, non del
giorno a cui si riferiscono: per quei giorni specifici manca la
proprietà di "timestamp non falsificabile a posteriori" che è il
motivo stesso per cui questo repo esiste. Il bug è stato corretto
(pubblicazione ora via API GitHub, senza dipendenze dall'ambiente di
esecuzione) — da 2 ottobre 2026 in poi la pubblicazione giornaliera in
tempo reale è di nuovo garantita.

## Struttura

- `records/YYYY-MM-DD.md` — snapshot leggibile
- `records/YYYY-MM-DD.json` — stesso contenuto, machine-readable

## Codice

Il codice del modello resta privato. Questo repo pubblica solo gli
output giornalieri, non la logica che li genera.
