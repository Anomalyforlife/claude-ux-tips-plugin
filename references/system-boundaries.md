# Client/server boundary, offline e onboarding

## 3. I dark pattern più comuni (da evitare)


- **Confirm shaming**: opzioni "no" scritte per far sentire in colpa.
- **Hidden costs**: prezzo basso iniziale, costi extra nascosti al checkout.
- **Roach motel**: iscrizione in un click, disiscrizione volutamente complessa.


## 65. Cosa succede davvero quando l'utente clicca "acquista"


- Il browser valida il form localmente prima di inviare qualsiasi richiesta di rete — feedback istantaneo è compito del frontend.
- Il backend rivalida **sempre** tutto: l'input del client non è mai attendibile.
- Stock, prezzo e pagamento vengono verificati lato server; la scrittura sul database avviene in un'unica transazione atomica (o commit tutto o nulla).
- La UI si ridisegna sui dati reali restituiti dal server, non su una previsione.
- Solo le azioni "leggere" (like, rename) possono permettersi l'optimistic UI — un pagamento deve sempre mostrare lo spinner reale.


## 80. Onboarding: il primo minuto decide tutto


- Fai raggiungere il primo "aha moment" nel minor numero di step possibile, rimandando la configurazione avanzata a dopo.
- Un tour con troppi tooltip in sequenza viene chiuso senza essere letto: preferisci 1-2 hint contestuali al momento giusto.
- Chiedi solo i dati strettamente necessari per iniziare; il resto del profilo si completa progressivamente (progressive disclosure).
- Mostra dati/contenuti di esempio (seed data) invece di uno stato vuoto totale, così l'utente capisce subito cosa fare.


## 83. Offline-first: continuare a funzionare senza rete


- Distingui sempre "offline" da "richiesta lenta": un banner esplicito ("sei offline") evita che l'utente scambi la disconnessione per un bug.
- Le azioni fatte offline vanno accodate localmente e sincronizzate alla riconnessione, non semplicemente perse o bloccate.
- Mostra chiaramente quali dati sono già disponibili in cache (e potenzialmente non aggiornati) rispetto a quelli mancanti.
- In caso di conflitto tra modifiche offline e dati aggiornati sul server, chiedi all'utente come risolvere invece di sovrascrivere in silenzio.
- Un service worker con cache-first per gli asset statici mantiene l'app utilizzabile anche a connessione instabile.

