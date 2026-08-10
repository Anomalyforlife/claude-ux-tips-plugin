# Accessibilità, touch e mobile

## 55. Focus state e accessibilità da tastiera


- `outline: none` senza sostituto è un problema di accessibilità, non solo estetico.
- Un ring visibile (2px, offset, contrasto adeguato su ogni sfondo) è necessario per chi naviga da tastiera.
- Usa `:focus-visible` per mostrare il ring solo a chi naviga da tastiera, non ai click del mouse.
- L'ordine del focus deve seguire il DOM, non il layout visivo — occhio ai riordini via CSS.
- I modali devono intrappolare il focus al loro interno e restituirlo al trigger alla chiusura.
- Uno skip-link invisibile ma raggiungibile da tastiera permette di saltare la navigazione.


## 57. Swipe gesture su mobile: comunicare con il feedback tattile


- Uno swipe ha due soglie: una breve rivela i bottoni, una più lunga oltrepassa il punto di "commit".
- Durante il gesto la riga deve resistere come un elastico; al punto di commit l'icona "scatta" e la resistenza sparisce.
- Associa una direzione a un significato coerente (destra = azione sicura, sinistra = distruttiva) — non invertirle mai.
- I gesture sono invisibili ai nuovi utenti: mostra un "peek" (anteprima parziale) al primo utilizzo per insegnarli.
- Anche uno swipe rapido che elimina subito deve offrire un breve undo.


## 68. Hover su dispositivi touch: un bug comune


- I browser mobile "simulano" l'hover al primo tap, e le azioni restano visibili finché l'utente non tocca altrove.
- Verifica il tipo di dispositivo con media query (`hover` e `pointer: coarse`), non con lo user-agent sniffing.
- Su mobile sposta le azioni nascoste dietro hover dentro la card stessa, in uno swipe o in un bottom sheet.
- L'hover dovrebbe rivelare informazioni extra, mai contenere l'unica via per un'azione primaria.
- I target di tocco devono avere almeno 44px, anche se l'icona visiva è più piccola — allarga l'hit-area, non l'icona.


## 73. Bottom sheet mobile: un modal che rispetta il pollice


- Deve poter essere trascinato per chiuderlo (drag-to-dismiss), non solo tramite una X in alto, spesso fuori portata del pollice.
- Usa snap point multipli (peek, metà schermo, fullscreen) invece di un'unica altezza fissa.
- Un piccolo "grabber" orizzontale in cima comunica visivamente che è trascinabile.
- Il contenuto sotto deve restare visibile e leggermente scurito (dimming), mai completamente nascosto, per mantenere il contesto.
- Se il contenuto supera l'altezza disponibile, solo l'area interna scrolla — l'header con le azioni resta fisso.


## 74. Contrasto e leggibilità: oltre il rapporto minimo WCAG


- Il rapporto 4.5:1 è un minimo, non un obiettivo: per testo lungo punta più in alto per ridurre l'affaticamento visivo.
- Il testo su immagini richiede un overlay (gradiente scuro) o un contrasto verificato punto per punto, non un valore fisso.
- La dimensione del font influisce sul contrasto percepito: testo grande (18px+ bold) tollera un rapporto minimo più basso (3:1).
- Non affidarti solo al colore per distinguere stati (link, errori): aggiungi sempre un secondo segnale (sottolineatura, icona, peso).


## 75. Reduced motion: animazioni che rispettano le preferenze dell'utente


- Rispetta sempre `prefers-reduced-motion: reduce` — disattiva parallax, autoplay e transizioni grandi, non solo rallentarle.
- Sostituisci le animazioni di posizione con semplici fade quando l'utente ha richiesto motion ridotto.
- Le animazioni essenziali per capire un cambio di stato (es. drag-and-drop) vanno mantenute ma accorciate, non rimosse del tutto.
- Testa sempre con la preferenza attivata nel sistema operativo, non solo leggendo il codice.


## 79. Notifiche push e permessi: il timing è tutto


- Non chiedere il permesso di notifica al primo avvio: l'utente rifiuta perché non ha ancora capito il valore.
- Chiedi il permesso subito dopo un'azione che dimostra il beneficio (es. dopo aver impostato un reminder).
- Se il permesso viene negato, non richiederlo di nuovo subito — spiega dove riattivarlo dalle impostazioni quando serve davvero.
- Segmenta le notifiche per tipo (utente può disattivare il marketing ma tenere quelle di sicurezza).

