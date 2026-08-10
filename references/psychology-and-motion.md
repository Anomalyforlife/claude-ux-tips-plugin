# Psicologia UI, micro-interazioni e motion

## 1. Micro-interazioni che rendono viva un'interfaccia


- Usa **easing "ease-out"**, non lineare: il movimento lineare sembra robotico.
- Dai sempre **feedback immediato** al tap: il silenzio genera ansia nell'utente.
- Applica il principio dell'**anticipazione** (squash-and-stretch, da Disney 1937): un piccolo "caricamento" prima dell'azione principale la rende più naturale.


## 2. Far percepire un'app più veloce (senza cambiarne la velocità reale)


- **Skeleton screens**: mostra il layout prima del contenuto, non uno schermo vuoto.
- **Optimistic UI**: mostra subito il risultato dell'azione senza aspettare la risposta del server.
- **Progress bar psicologica**: falla partire veloce e rallentare alla fine — l'utente ricorda l'inizio rapido.


## 4. Psicologia del colore nell'UI


- **Simultaneous contrast**: lo stesso grigio appare diverso a seconda dello sfondo — il contesto conta più del valore assoluto.
- **Pop-out effect**: rendi grigio tutto tranne un elemento per guidare l'occhio (non colorare tutto).
- **Color temperature**: rosso = urgenza, blu = fiducia, verde = successo — usa il colore come comunicazione, non decorazione.


## 6. I meccanismi psicologici che rendono le app "addictive"


- **Variable rewards**: contenuti imprevedibili nel feed tengono l'utente a scorrere (effetto slot machine).
- **Effetto Zeigarnik**: le attività incomplete (progress bar, storie non viste) restano in memoria finché non vengono completate.
- **Loss aversion**: perdere uno streak fa più male di quanto piaccia guadagnarlo — usato per trattenere l'utente.
- **Reciprocità sociale**: un like ricevuto spinge a ricambiare, aprendo l'app più a lungo del previsto.


## 7. Come le app eliminano ogni "punto di uscita"


- **Pull-to-refresh**: stesso gesto/incertezza di una leva slot machine.
- **Infinite scroll**: elimina la decisione "continuo o mi fermo?" tipica di un bottone "next".
- **Autoplay**: rimuove la pausa naturale dopo un video, prevenendo il momento di uscita.


## 8. Ogni proprietà CSS è una decisione psicologica (case study bottone Stripe)


- Colore di sfondo = tono emotivo (es. viola = fiducia).
- Border-radius arrotondato = percezione di amichevolezza.
- Box-shadow morbido = percezione premium/floating.
- Micro-hover (scale up leggero) = comunica interattività.


## 9. Perché preferiamo angoli arrotondati a quelli spigolosi


- Gli **angoli acuti** attivano l'amigdala (associazione evolutiva a pericolo: spine, artigli).
- Gli **angoli arrotondati** comunicano sicurezza e "si può toccare senza farsi male".
- Da qui l'evoluzione storica di bottoni/card verso forme sempre più morbide nei prodotti digitali.


## 10. 3 trucchi psicologici per pricing card che convertono


- **Anchoring**: mostra prima il prezzo alto barrato, il prezzo scontato sembra un affare.
- **Social proof**: badge "più popolare" rimuove il dubbio decisionale.
- **Loss aversion**: scrivi "risparmia il 40%" invece di "paga di meno" — si teme di più perdere che godere di guadagnare.


## 12. Correzioni ottiche che i designer applicano "a occhio"


- I trianglo/play button vanno spostati verso il **centroide visivo**, non il bounding box geometrico.
- Un cerchio deve essere ~13% più grande di un quadrato per sembrare della stessa dimensione (il cervello legge area, non pixel).
- Nei corner radius annidati: `raggio interno = raggio esterno - gap`, altrimenti gli angoli sembrano "schiacciati".
- Testo bianco su sfondo scuro appare più "pesante" (illusione da irradiazione) — riduci leggermente il font-weight in dark mode.


## 13. Legge di Fitts applicata al design mobile


- Il tempo per raggiungere un target dipende da **distanza** e **dimensione**.
- Metti le azioni primarie **a portata di pollice**, non in alto se l'app è mobile.
- Un solo spostamento del CTA primario può far salire il tap rate del 12% al 34% (esempio citato).
- Menu contestuali, FAB, edit inline: tutti riducono la distanza al target quasi a zero.


## 17. Come creare profondità credibile con le ombre


- Combina 3 livelli: **contact shadow** stretta alla base, **elevation glow** morbido dietro, leggero shift prospettico.
- Colora il glow con il colore brand (es. viola su app viola, blu su fintech) invece di usare grigio neutro.
- L'ombra va trattata come parte del design system, non come ripensamento finale.


## 20. Applicare la sezione aurea (1.618) al design


- Scala lo spacing moltiplicando per 1.618 (8 → 13 → 21 → 34...) per un ritmo naturale invece di padding casuale.
- Dividi il layout 61.8% / 38.2% (contenuto sulla parte grande, azioni sulla piccola).
- Applica lo stesso rapporto alla scala tipografica (body 16 → subheading 26 → heading 42 → display 68).
- Usato da Apple, Stripe, Linear e Airbnb nei loro layout.


## 30. Le durate giuste per ogni tipo di animazione


- **Entrate**: 200-300ms (più veloce sembra rotto, più lento pesante).
- **Uscite**: 150-200ms, più rapide delle entrate.
- **Feedback** (hover, press, toggle): sotto i 100ms.
- **Attention** (errori, notifiche): 500-800ms con bounce.
- **Stagger su liste**: 50ms per elemento è il punto ottimale.


## 31. L'effetto posizione seriale applicato a nav e landing page


- Le persone ricordano meglio il **primo** e l'**ultimo** elemento di una sequenza (memoria a forma di U).
- Nella nav: logo/brand all'inizio, CTA di conversione alla fine — gli elementi centrali vengono dimenticati.
- Nelle landing page: value prop più forte in apertura, prova sociale più forte in chiusura.
- Non nascondere contenuti chiave al centro della sequenza — è la "zona morta" della memoria.


## 32. L'effetto Zeigarnik nell'onboarding


- I task incompleti restano in memoria attiva più a lungo di quelli completati.
- Una checklist di onboarding con 1-2 item non completati spinge l'utente a tornare per finirla.
- Un progress al 100% viene dimenticato, uno all'80% "tallona" l'utente.
- Funziona solo su task che l'utente vuole davvero completare — su contenuti irrilevanti (es. email marketing) genera solo frizione.


## 33. La regola picco-fine (peak-end rule)


- Il cervello ricorda un'esperienza in base al **momento di picco** e alla **fine**, non alla media.
- Un flusso di durata identica viene ricordato molto meglio se termina con un momento di delight (es. animazione di successo) invece di fermarsi e basta.
- Progetta picchi intenzionali (aha moment, conferma positiva) — un delight batte cinque interazioni neutre.
- Attenzione: se un flusso quasi perfetto finisce con un errore, l'utente ricorderà solo quello.


## 42. Le regole per non mentire con un grafico


- I bar chart devono **sempre** partire da zero — troncare l'asse esagera le differenze.
- Usa bar chart per confronti, linee per l'andamento nel tempo; evita le torte oltre le 5 fette (l'occhio non sa confrontare angoli).
- Il colore deve codificare informazione (categorico/sequenziale/divergente), non decorare.
- Elimina rumore visivo: griglie pesanti, barre 3D, ombre — ogni pixel dovrebbe essere dato (data-ink ratio di Tufte).
- Etichetta le linee direttamente invece di usare una legenda separata.

