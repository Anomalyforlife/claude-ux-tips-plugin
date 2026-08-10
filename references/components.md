# Componenti UI (form, nav, data, overlay)

## 15. Il principio di prossimità (Gestalt)


- Elementi vicini vengono percepiti come collegati, quelli lontani come separati — il cervello lo fa automaticamente.
- Raggruppa elementi per **funzione** (es. navigazione, azioni, impostazioni), non per equidistanza.
- Nei form, raggruppa i campi per contesto (dati personali, indirizzo, pagamento) invece di allinearli tutti uguali.
- Un buon raggruppamento spaziale elimina la necessità di divider grafici.


## 22. Empty state: la prima impressione sprecata


- Uno schermo vuoto senza illustrazione comunica "qualcosa è rotto" — anche una piccola illustrazione cambia tutto.
- Scrivi il copy in tono umano, non come un log di errore.
- Offri sempre un'**azione primaria chiara**, non solo un "aggiorna".
- Distingui i 4 tipi di "vuoto": primo utilizzo, nessun risultato, errore, filtro senza match — ognuno merita un design diverso.
- L'empty state è un'occasione di onboarding, non solo un fallback.


## 23. Le regole dei toast notification


- **Posizione**: desktop in basso a destra, mobile in alto — mai al centro (blocca l'interazione).
- **Timing**: info 4s, warning 7s, errori restano finché l'utente non li chiude — un timer fisso per tutti è un bug.
- **Stacking**: massimo 3 visibili, i nuovi spingono i vecchi con physics "a molla".
- **Sempre dismissibili**: bottone di chiusura o swipe — altrimenti è un modal travestito.
- **Color coding**: icona + bordo colorato, non solo lo sfondo (il 6% degli utenti non distingue solo il colore).


## 25. Le 5 regole di un dropdown ben fatto


- Trigger chiaro: freccia, hover state, target minimo 44px.
- **Flip automatico** verso l'alto se non c'è spazio sotto — mai tagliare l'ultimo elemento.
- Navigazione da tastiera obbligatoria: frecce, invio, escape.
- Oltre 10 elementi aggiungi la ricerca; oltre 100, virtualizza la lista.
- Anima l'apertura sotto i 150ms — abbastanza veloce da sembrare istantanea.


## 26. Le regole di un tooltip che non infastidisce


- Attendi 300ms prima di mostrarlo — i tooltip istantanei generano solo rumore.
- Usa sempre una freccia che colleghi il tooltip al suo trigger.
- Fai il flip vicino ai bordi dello schermo per non tagliarlo.
- Deve essere chiudibile in più modi: mouse fuori, escape, focus out, tap esterno.
- Massimo 300px di larghezza, una frase — è un suggerimento, non documentazione.


## 27. I 6 stati di un campo form (la maggior parte delle app ne implementa solo 2)


- **Default**: label sempre visibile fuori dal campo, mai solo nel placeholder.
- **Focus**: ring con contrasto minimo 3:1 (il classico glow blu spesso fallisce l'accessibilità).
- **Error**: colore + icona + messaggio — un bordo rosso da solo è invisibile al 12% degli utenti con daltonismo.
- **Success**: check verde dentro il campo, non un toast separato.
- **Disabled**: sfondo in scala di grigi (non solo opacity 50%) + cursor not-allowed.
- **Loading**: spinner interno, campo disabilitato — previene il bug del doppio submit.


## 28. Come scegliere il pattern di navigazione giusto


- **Tab bar**: solo mobile, massimo 3-5 destinazioni principali.
- **Sidebar**: solo desktop, per contenuti gerarchici o più di 5 sezioni.
- **Hamburger**: solo per contenuti secondari — il 40% degli utenti clicca meno i menu nascosti.
- **Command palette (Cmd+K)**: per power user, non come navigazione primaria per nuovi utenti.
- **Breadcrumb**: solo se la gerarchia supera 2 livelli.


## 29. 5 fix per error state che non frustrano l'utente


- Distingui il tipo di errore (validazione, rete, server, permessi) — ognuno merita un pattern visivo diverso.
- Offri sempre una via d'uscita: retry, refresh, contatto.
- La superficie dipende dalla gravità: inline per errori recuperabili, toast per transitori, modal solo quando serve bloccare tutto.
- Usa un linguaggio umano ("connessione persa, riconnessione in corso") invece di messaggi tecnici.
- La validazione inline previene l'80% degli errori prima che accadano.


## 34. Search come sistema (5 componenti)


- Il placeholder deve descrivere concretamente cosa si può cercare (es. "cerca per nome, SKU o brand").
- Mostra le **ricerche recenti** al focus dell'input invece di un campo vuoto.
- L'autocomplete deve ordinare i risultati per rilevanza/click, non alfabeticamente.
- Naviga i risultati da tastiera (frecce, invio, escape).
- In caso di zero risultati, suggerisci alternative invece di un vicolo cieco.


## 35. Date range picker: dai 6 click a 1


- Offri preset per il 90% dei casi (oggi, ieri, ultimi 7/30 giorni, ultimo trimestre).
- Mostra un'anteprima del range mentre l'utente passa il mouse, prima del secondo click.
- Mostra due mesi affiancati per i range che attraversano mesi diversi.
- Su mobile usa un bottom sheet fullscreen, non un popover — calendario scrollabile verticalmente.


## 36. Sistema di tab senza salti visivi


- La linea sottostante il tab attivo deve **scorrere**, mai teletrasportarsi.
- Con più di 8 tab, non andare a capo: scroll orizzontale con edge fade per indicare altro contenuto.
- Naviga da tastiera (frecce, home, end).
- Su mobile: segmented control sotto i 5 tab, bottom sheet sopra — mai solo ridimensionare la versione desktop.


## 37. Multi-step form: come dividere un form lungo


- Il cervello elabora bene 3 campi alla volta; 12 in fila causano fatica cognitiva/abbandono.
- Mostra sempre un indicatore di progresso (barra, dots, step label).
- Raggruppa i campi per **contesto** (dati personali, spedizione, pagamento), non per conteggio casuale.
- Valida ogni step subito, non solo alla fine — un errore allo step 1 non deve emergere allo step 4.
- Salva lo stato ad ogni step: perdere il form una volta significa perdere l'utente per sempre.


## 38. Quale superficie usare per ogni tipo di notifica


- **Toast**: eventi minori, si auto-chiude in 4s (aggiungi undo per azioni distruttive).
- **Banner**: informazioni persistenti, resta finché l'utente non lo chiude.
- **Modal**: solo quando serve una decisione obbligata prima di continuare — spesso abusato.
- **Badge**: notifica passiva, resta finché non viene consultata.
- Usa la superficie in base alla **gravità del contenuto**, non per abitudine.


## 39. Anatomia di un toggle switch credibile


- Le proporzioni contano: larghezza del rail = 2× diametro del knob.
- Anima più proprietà insieme (colore rail, posizione knob, ombra, testo) in ~250ms ease-out, non uno scatto secco.
- Deve funzionare da tastiera (barra spaziatrice) con focus ring visibile e annuncio screen reader.
- In caso di richiesta server: mostra subito il flip, spinner nel knob, rollback se il server rifiuta.


## 40. UX del drag-and-drop in board tipo kanban


- Dai 3 segnali chiari quando un elemento viene "afferrato": cambio cursore, sollevamento visivo, fade dello sfondo.
- Le drop zone devono comunicare per prime: linea di inserimento su colonna, highlight su zona.
- Scegli lo snap in base al layout: colonne strutturate → snap; canvas libero (Figma) → free.
- Dopo un drop indesiderato, mostra un toast con **undo** — 5 secondi per annullare evita il panico dell'utente.


## 41. Come progettare uno star rating onesto


- Il riempimento delle stelle deve reagire già all'hover, non solo al click.
- Preview (hover) e selezione (click) vanno tenute come due livelli separati per evitare flicker.
- Non arrotondare un 4.4 a 5 stelle piene: mostra la frazione reale con una stella parzialmente riempita.
- Anima il riempimento con un piccolo stagger (~30ms) tra una stella e l'altra invece di un pop simultaneo.
- Affianca alle stelle un anello continuo che riassume il valore medio a colpo d'occhio.


## 43. Slider: dettagli che sembrano piccoli ma non lo sono


- Estendi l'area cliccabile ben oltre la linea sottile — l'intera riga deve rispondere al drag.
- Riempi visivamente tutta la parte a sinistra del thumb per comunicare il valore prima ancora di leggerlo.
- Se i valori sono discreti (volume, rating, prezzo), fai lo snap agli step invece di un continuo impreciso.
- Mostra il valore esatto sopra il thumb durante il drag, poi fallo sparire.
- Supporta anche l'input da tastiera (frecce, home/end).


## 44. Formattazione live di un campo numero carta di credito


- Raggruppa le cifre a blocchi di 4 mentre l'utente digita, non alla fine.
- Riconosci il brand dalla prima cifra e mostra subito il logo (Visa, Mastercard...).
- Mantieni la posizione del cursore corretta quando vengono inseriti spazi automatici.
- Non segnalare errore alla prima cifra digitata — valida on blur, non on keystroke.
- Ripulisci automaticamente numeri incollati con trattini/spazi invece di rifiutarli.


## 45. Filtri a chip: un sistema, non un elenco di bottoni


- Ogni chip ha 3 stati (idle, active, disabled) — se "active" somiglia troppo a "idle" il filtro sembra rotto.
- Aggiorna il conteggio dei risultati immediatamente ad ogni tap, mai in silenzio.
- Offri sempre un bottone "clear all" quando ci sono filtri stack.
- Su mobile, scorri i chip orizzontalmente con edge fade invece di andare a capo.
- Tieni i filtri attivi "pinnati" in alto per far capire perché la lista si è ristretta.


## 46. Input OTP/codice a più caselle


- Supporta il paste di un codice completo: distribuiscilo automaticamente su tutte le caselle.
- Passa automaticamente alla casella successiva a ogni digit, torna indietro con backspace su casella vuota.
- Tratta i box come un unico valore internamente, non come stati separati.
- Su mobile forza la tastiera numerica e sfrutta l'autofill del codice via SMS.
- Codice errato: shake, reset, focus sulla prima casella — feedback mai silenzioso.


## 47. Command palette (Cmd+K): come farla sentire istantanea


- Usa fuzzy matching (es. "STG" trova "Settings") con evidenziazione delle lettere trovate.
- Raggruppa i risultati (recenti, azioni, pagine) invece di un elenco piatto.
- Naviga interamente da tastiera: frecce, invio, escape.
- Se vuota, mostra comandi recenti invece di uno schermo bianco.
- I comandi che richiedono dati asincroni devono mostrare un loader inline, senza bloccare l'intera palette.


## 48. Paginazione: perché "offset" si rompe e "cursor" no


- La paginazione per offset (skip N) si rompe se i dati cambiano — righe duplicate o saltate.
- Usa la paginazione a **cursore** (dopo questo ID) per una lista stabile anche con dati che cambiano.
- Scegli il pattern giusto: numerata per saltare a una pagina, "load more" per controllo manuale, infinite scroll per i feed.
- Con molte pagine, tronca i link (1 ... 499 500 501 ... 1000), mantenendo sempre raggiungibili prima e ultima.
- Salva la posizione di scroll quando si torna da un dettaglio, e la pagina nell'URL per renderla condivisibile.


## 49. File upload: comunicare stato in modo onesto


- Una drop zone deve reagire visibilmente al drag-over (bordo, glow, cambio testo) prima del rilascio.
- Mostra percentuale e tempo stimato, non solo uno spinner generico.
- Se l'upload fallisce al 90%, offri un retry inline che riparte dal file già caricato, mai da zero.
- Mostra thumbnail, tipo e dimensione del file come prova visiva di cosa è stato ricevuto.
- Con upload multipli, ogni file ha il proprio progresso e retry — un fallimento non deve bloccare gli altri.


## 50. Password strength: coach, non giudice


- La forza reale è data dalla lunghezza/entropia, non dal solo numero di simboli richiesti.
- Mostra la checklist dei requisiti **mentre** l'utente digita, con spunte live, non dopo il submit.
- Usa una barra di forza che cresce gradualmente invece di un giudizio binario.
- Non bloccare il paste della password e offri il toggle "mostra password".
- Offri la generazione automatica di una password forte con un tap.


## 51. Color picker moderno: OKLCH invece di HEX


- OKLCH (luminosità, croma, hue) è più leggibile per un umano rispetto all'esadecimale.
- Salva swatch recenti e palette per accesso rapido.
- Verifica il **contrasto in tempo reale** al momento della scelta, non in fase di review successiva.
- Mostra la trasparenza su una scacchiera, non solo su sfondo bianco, per non ingannare sull'effettivo alpha.
- Da un solo hue genera automaticamente l'intera scala di tint/shade per il design system.


## 56. Undo invece di conferma: un pattern più umano


- Un "sei sicuro?" penalizza tutti per l'errore di uno; l'**undo** dà una seconda possibilità senza frizione.
- Tratta la cancellazione come uno stato (soft delete, 30 giorni in trash), non come un evento irreversibile.
- Riserva la conferma esplicita solo alle azioni davvero irreversibili (es. GitHub richiede di digitare il nome del repo).
- Uno stack di undo (come Cmd+Z di Figma) è più potente di un singolo toast.
- Anche un piccolo delay prima dell'invio (es. Gmail, 10s) può prevenire errori costosi.


## 58. Context menu: un sistema, non un elenco casuale


- Il menu deve misurare lo spazio disponibile e fare flip/mirror per restare sempre dentro il viewport.
- Raggruppa le azioni per intento con divider (es. rinomina/duplica insieme, elimina isolato in rosso in fondo).
- Per i sottomenu, mantieni aperto il menu finché il cursore resta dentro un'area triangolare virtuale ("hover intent").
- Supporta navigazione da tastiera: frecce, lettera per saltare a un'azione, escape per chiudere un livello alla volta.
- Su mobile, il long-press apre lo stesso set di azioni in un bottom sheet.


## 59. Azioni distruttive: hold-to-delete invece di "sei sicuro?"


- Un anello di caricamento durante una pressione prolungata (~300ms) sostituisce efficacemente un dialogo di conferma.
- Nomina l'azione nel bottone stesso ("Elimina progetto"), non un generico "sì/no".
- Non posizionare mai un bottone distruttivo dove la memoria muscolare clicca automaticamente.
- Usa il rosso solo per la distruzione: abusarlo (es. su "logout") lo svaluta e rende "delete" meno percepito come pericoloso.
- Un cooldown (es. 14 giorni prima della cancellazione reale) è un'ultima linea di difesa.


## 60. UX del multiplayer in tempo reale (cursori condivisi)


- Interpola la posizione dei cursori remoti per farli scorrere fluidamente invece di "teletrasportarsi" tra gli aggiornamenti del server.
- Assegna un colore stabile a ogni utente (hash dell'ID) per renderlo riconoscibile a colpo d'occhio.
- Mostra gli avatar dei presenti prima ancora che qualcuno parli/agisca.
- Blocca visivamente un elemento in editing da un altro utente per prevenire conflitti (due persone che modificano la stessa shape).
- Cliccare l'avatar di un collaboratore e seguirne il viewport sostituisce efficacemente uno screen share.


## 61. Inline editing: quando un testo diventa un input


- Segnala che un testo è editabile con hover sottile (matita, leggero tint), non lasciarlo indistinguibile.
- Lo swap tra testo statico e input deve mantenere identici font, size e padding — un solo pixel di scarto rompe l'illusione.
- Invio conferma, escape annulla — definisci anche cosa fa il blur (salva o scarta) e sii coerente in tutta l'app.
- Aggiorna l'interfaccia otticamente subito (optimistic), fai rollback mostrando il motivo se il server rifiuta.
- Più editing inline dai, più alto è il rischio di errori accidentali: calibra in base al costo di un errore.


## 64. Settings page: organizzarla come un sistema


- Adatta l'interazione al "raggio di impatto": i toggle si applicano subito, i campi identitari richiedono save/cancel espliciti.
- Raggruppa per task, non per lista piatta — nascondi le opzioni avanzate dietro un click extra.
- Aggiungi una ricerca interna: i power user cercano invece di scrollare tra decine di opzioni.
- Segnala visivamente ogni impostazione modificata rispetto al default, con un modo rapido per resettarla.
- Le azioni distruttive vanno isolate in fondo, con conferma tramite digitazione del nome.


## 69. Disabled button: quando nasconde più problemi di quanti ne risolve


- Un bottone disabled esce dal tab order: screen reader e navigazione da tastiera lo saltano senza spiegazioni.
- Un tooltip su un elemento disabled spesso non si attiva mai, perché gli eventi puntatore sono disattivati.
- Meglio tenere il bottone sempre attivo: al click, valida e illumina i campi mancanti, spostando il focus sul primo.
- Distingui sempre "disabled" da "loading": durante una richiesta il bottone deve restare focus-abile e mostrare uno spinner, non sparire nel grigio.


## 70. Checkbox multipli: gestire correttamente la selezione di massa


- Il checkbox dell'header ha 3 stati (checked, empty, partial) — eliminare lo stato "partial" fa perdere all'utente il controllo di cosa ha selezionato.
- "Seleziona tutto" spesso seleziona solo le righe visibili: dichiara esplicitamente il numero totale ("seleziona tutte le 247 righe corrispondenti"), aggiornato in base ai filtri attivi.
- Shift-click per selezionare un range è un comportamento atteso su desktop.
- La selezione va mantenuta nello state dell'app, non nelle righe visibili — altrimenti si perde cambiando pagina.
- Per eliminazioni massive, mostra il conteggio nel bottone d'azione invece di un modal di conferma, e offri undo per alcuni secondi dopo.


## 71. Tabelle dati: oltre righe e colonne


- Fissa (`sticky`) header e prima colonna quando la tabella scorre, così l'utente non perde mai il contesto.
- Allinea i numeri a destra e il testo a sinistra — l'occhio confronta cifre più velocemente in colonna.
- Lo zebra striping aiuta solo con righe dense (>8): su poche righe è rumore visivo inutile.
- Il resize delle colonne va salvato per utente, altrimenti si ripete la stessa configurazione ad ogni sessione.
- Ordinamento e filtro vanno nell'URL (query params), così la vista è condivisibile e sopravvive al refresh.


## 76. Breadcrumb e gerarchia: comunicare "dove sono" senza ambiguità


- L'ultimo elemento (pagina corrente) non deve essere cliccabile — è già ovvio dov'è l'utente.
- Su schermi stretti, tronca i livelli centrali con un "…" espandibile invece di andare a capo o rimpicciolire il font.
- Ogni livello deve riflettere la gerarchia reale di navigazione, non l'URL tecnico (slug, ID).
- Abbina sempre il breadcrumb a un titolo di pagina chiaro: il breadcrumb da solo non basta per orientarsi.


## 78. Rich text editor: le decisioni che nessuno nota finché non sono sbagliate


- La toolbar deve mostrare lo stato attivo (bold premuto se il cursore è su testo bold), non restare statica.
- Incollare da Word/Google Docs deve ripulire markup superfluo (font, spazi, span vuoti), non portarlo pari pari nel documento.
- Le scorciatoie da tastiera standard (Cmd+B, Cmd+I) devono funzionare sempre, anche se la toolbar è nascosta.
- Il conteggio caratteri/parole va aggiornato in tempo reale ma con debounce, per non ricalcolare ad ogni keystroke su testi lunghi.

