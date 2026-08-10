# Performance percepita, loading e attese

## 19. Skeleton screen: dettagli che fanno la differenza


- Uno spinner comunica "aspetta", uno skeleton comunica "sta arrivando" — riduce l'ansia.
- Lo shimmer deve muoversi nella **direzione di lettura** (sinistra→destra), il contrario sembra "sbagliato".
- Non usare rettangoli generici: fai combaciare la forma dello skeleton al contenuto reale (cerchio per avatar, righe corte per nomi).
- Livello successivo: **optimistic UI** — mostra subito il risultato dell'azione e fai rollback solo in caso di errore server.


## 24. Come scegliere il giusto loading state


- **Skeleton**: quando conosci la forma del contenuto e l'attesa supera 300ms.
- **Spinner**: attese brevi (<3s) quando non conosci la durata.
- **Progress bar**: quando conosci la percentuale (upload, installazioni oltre i 3s).
- **Optimistic UI**: per azioni che riescono nel 99% dei casi (like, save) — mostra subito, fai rollback se fallisce.
- Sotto i 300ms non mostrare nulla: un flash di loading si legge come un bug.


## 52. Quando validare un campo form (il timing conta più della regola)


- Validare solo al submit costringe l'utente a scoprire 10 errori insieme, tutti in rosso.
- Validare a ogni keystroke punisce l'utente a metà parola (es. email "invalida" alla prima lettera).
- **Validazione on-blur** (quando l'utente lascia il campo) è il compromesso giusto.
- Dopo un primo errore, passa a validazione live su quel campo per confermare la correzione in tempo reale.
- Un check verde è feedback tanto quanto un errore rosso — non limitarti a segnalare solo ciò che è sbagliato.


## 53. UX writing: le parole contano quanto il layout


- "Submit" non dice nulla; "Crea il mio account gratuito" comunica il beneficio.
- Un errore utile propone la soluzione ("questa email è già in uso, vuoi accedere?") invece di limitarsi a segnalare il problema.
- Un empty state è l'occasione migliore per insegnare la prima azione da fare.
- Il placeholder non è un label: sparisce appena l'utente digita, lasciandolo senza contesto.
- Scrivi come una persona, non come un server ("operazione fallita" non lo dice mai nessuno nella vita reale).


## 54. Optimistic UI: quando fingere che sia già fatto


- Sotto i 400ms un'azione viene percepita come istantanea; oltre, uno spinner sembra un malfunzionamento anche se tutto va bene.
- Aggiorna subito l'interfaccia e sincronizza in background, con rollback in caso di errore.
- Funziona bene per azioni reversibili al 99% (like, save, bookmark).
- **Mai** applicarlo a pagamenti, trasferimenti o azioni non reversibili — lì va mostrato lo stato reale, anche se è "attendi".


## 62. Checklist per un audit UX rapido di interfacce generate da AI


- Le interfacce generate automaticamente spesso replicano 1:1 lo schema del database (12 colonne, delete accanto a edit) invece di pensare all'utente.
- Chiediti sempre: chi userà questa pagina, e qual è l'errore peggiore che potrebbe commettere?
- Le azioni distruttive vanno protette (conferma con digitazione), la ricerca dovrebbe spesso essere l'azione primaria.
- Specifica ogni stato (loading, empty, error, success, offline, partial) prima di scrivere codice, non dopo.
- Su un'interfaccia già live, un audit sistematico dovrebbe restituire una lista di fix ordinata per severità, non consigli generici.


## 63. Auto-save: uno stato affidabile, non solo un'icona


- Usa un debounce (es. pausa di 800ms nella digitazione) prima di salvare, non ad ogni keystroke.
- Comunica lo stato con una pillola testuale (digitando/salvataggio/salvato/offline/errore) — l'utente si fida di questo indicatore più della feature stessa.
- In offline, accoda le modifiche localmente con un badge che ne mostra il conteggio, e scarica la coda in ordine alla riconnessione.
- Con più tab aperte sullo stesso documento, non sovrascrivere in silenzio: fai merge o avvisa esplicitamente.
- Se l'utente prova a chiudere con modifiche non salvate, blocca la chiusura con un avviso del browser.


## 72. Skeleton vs contenuto reale: evitare il layout shift


- Le dimensioni dello skeleton devono combaciare esattamente con quelle del contenuto finale (altezza riga, larghezza immagine) o si genera un salto visivo (CLS).
- Riserva sempre lo spazio per immagini/iframe con `aspect-ratio`, mai lasciare che il layout "salti" quando l'asset carica.
- I font web devono avere un fallback con metriche simili (`font-display: swap` + font di sistema) per non spostare il testo al caricamento.
- Banner e notifiche dinamiche vanno inseriti con animazione di altezza, non con un semplice "pop" che spinge il contenuto sotto.


## 82. Liste lunghe: virtualizzazione e performance percepita


- Oltre qualche centinaio di elementi, renderizza solo le righe visibili nel viewport (windowing) — il DOM con migliaia di nodi rallenta scroll e interazione.
- Mantieni un buffer di righe sopra/sotto la viewport (overscan) per evitare flash bianchi durante lo scroll veloce.
- Se le righe hanno altezza variabile, misura e memorizza le altezze reali invece di stimarle: una stima sbagliata fa "saltare" la scrollbar.
- Preserva la posizione di scroll quando nuovi elementi vengono aggiunti in cima (es. chat, feed), altrimenti l'utente perde il punto di lettura.
- Il fetch dei dati va paginato in parallelo alla virtualizzazione: non caricare mai tutto il dataset solo per renderizzarne una parte.


## 85. Micro-copy per attese lunghe: non lasciare l'utente al buio


- Oltre i 5-10 secondi, sostituisci uno spinner generico con messaggi di stato che avanzano ("stiamo preparando i tuoi dati…", "quasi fatto…").
- Se la durata è nota (es. elaborazione file), mostra un tempo stimato invece di un'attesa indefinita — anche se approssimativo, riduce l'ansia.
- Varia il messaggio se l'attesa si prolunga oltre l'atteso ("sta richiedendo più del previsto, resta con noi") invece di ripetere lo stesso testo.
- Offri sempre un'via d'uscita esplicita per attese molto lunghe (annulla, continua in background e notifica al termine).
- Il linguaggio dei messaggi di attesa deve restare umano e rassicurante, mai tecnico ("elaborazione in corso" batte "processing job #4471").

