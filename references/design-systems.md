# Design system, layout e token

## 5. Perché una card sembra "cheap" (e come risolverlo)


- Aumenta il **padding** interno (es. da 8px a 28px) per un look più intenzionale.
- Dai **spazio proprio** a ogni elemento (avatar, testo, immagine, azioni).
- Alza il **line-height** del testo (es. da 1.1 a 1.6) per farlo "respirare".
- Lo spacing, non il colore o il font, è spesso il vero responsabile della percezione di qualità.


## 11. Le basi di un design system (colore, tipografia, spacing)


- **Colore**: parti da un hue, usa monocromatico (variazioni di luminosità), complementare (contrasto) o analogo (armonia).
- **Tipografia**: usa una scala modulare a rapporto fisso (display/heading/body/caption) invece di size casuali.
- **Spacing**: definisci un'unità base (es. 8px) e usane sempre i multipli.
- Colore + tipografia + spacing = atomi che compongono bottoni (molecole) e card (organismi).


## 14. FigmaMake — da mockup statico a prototipo interattivo (tool)


- I mockup statici non trasmettono l'esperienza reale agli stakeholder.
- Con prompt testuali si generano animazioni/interazioni mantenendo il design system esistente.
- Utile per passare da PRD a prototipo funzionante in pochi minuti, senza codice.


## 16. I 3 tipi di white space


- **Micro white space**: padding interno a un bottone.
- **Macro white space**: margini tra sezioni.
- **Active white space**: spazi ampi intenzionali per guidare l'occhio verso ciò che conta.
- Raddoppiare padding/gap (es. 16→32px, 8→16px) può far percepire una card come "premium" a parità di contenuto.


## 18. Il grid system non è "12 colonne uguali"


- Il grid è un **sistema di rapporti** (es. 4+8, 6+6, 3+9), non solo colonne fisse.
- Ai breakpoint il grid si riconfigura (12 → 6 → 4 → 1), non sparisce.
- Il gutter è una scelta di design: 8px sembra tecnico, 24px bilanciato, 40px editoriale/lussuoso.
- Rompere il grid intenzionalmente (hero full-bleed, pull quote) crea contrasto, non caos.


## 21. I 5 pilastri di un design system che funziona


- **Sistema colore semantico**: nomina i colori per scopo (background, brand, success, error), non per valore hex.
- **Type scale**: dimensioni/pesi/line-height intenzionali per ogni livello (display/heading/body/small).
- **Spacing coerente**: unità base fissa (es. 4px) e multipli per ogni margin/padding/gap.
- **Componenti con tutti gli stati**: default, hover, active, focus, disabled — non solo l'happy path.
- **Motion con scopo**: easing e durata coerenti (ease-out per entrate, ease-in per uscite, max 300ms).


## 67. Estrarre e riusare i design token in modo coerente (case study tool)


- Interfacce generate una alla volta tendono a divergere (colori/stili diversi ad ogni schermata) se non condividono un file di sistema unico.
- Prima di inventare nuovi valori, leggi cosa esiste già (config Tailwind, variabili CSS, componenti più riusati) — spesso il sistema è già lì.
- Ogni token estratto dovrebbe avere una motivazione esplicita registrata, non essere "inventato silenziosamente".
- Le estensioni al sistema sono permesse, ma vanno documentate con la ragione — è così che nascono le derive di stile.
- Forzare "una decisione per asse" (tipo, colore, spazio, finish) previene un risultato coerente ma poco distintivo.

