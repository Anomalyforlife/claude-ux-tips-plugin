# Dark mode, internazionalizzazione, immagini responsive

## 66. Overflow e truncation del testo: casi limite da gestire


- Un flex child non si restringe sotto la dimensione del proprio testo di default: serve `min-width: 0` per farlo funzionare.
- Per nomi file o email, tronca **nel mezzo** invece che alla fine, per preservare estensione/dominio (l'informazione più utile).
- Usa `font-variant-numeric: tabular-nums` per numeri che cambiano spesso, evitando che il layout "balli" ad ogni aggiornamento.
- Applica `overflow-wrap: anywhere` per URL lunghi che altrimenti farebbero esplodere il contenitore (il browser non spezza mai una parola).


## 77. Dark mode: non è solo invertire i colori


- Il nero puro (#000) su schermi OLED crea un contrasto eccessivo che affatica: usa grigi molto scuri (es. #121212).
- Le ombre non funzionano in dark mode: sostituiscile con bordi sottili o variazioni di luminosità per comunicare elevazione.
- I colori saturi "vibrano" su sfondo scuro: desatura leggermente i colori semantici (successo, errore) rispetto alla versione light.
- Immagini e illustrazioni spesso necessitano una variante dedicata, non solo un filtro di inversione automatico.


## 81. Internazionalizzazione e layout RTL


- Non hardcodare mai `left`/`right` in CSS: usa proprietà logiche (`margin-inline-start`, `padding-inline-end`) per un flip automatico in arabo/ebraico.
- Le icone direzionali (frecce back/next, chevron) vanno specchiate in RTL, ma icone di significato universale (play, check) restano invariate.
- Il testo tradotto può occupare fino al 30-40% di spazio in più (tedesco, finlandese): non fissare larghezze rigide su bottoni ed etichette.
- Date, numeri e valute vanno formattati con le API locale-aware del browser (`Intl.DateTimeFormat`, `Intl.NumberFormat`), mai concatenati a mano.
- Testa sempre con una lingua "estrema" (tedesco per lunghezza, arabo per direzione) invece di solo inglese/italiano.


## 84. Responsive images: la grandezza giusta per ogni schermo


- Usa `srcset` e `sizes` per servire la risoluzione adatta al dispositivo, invece di scaricare sempre l'immagine più pesante.
- Formati moderni (WebP, AVIF) con fallback JPEG/PNG riducono peso senza perdita percepibile di qualità.
- Applica sempre `width`/`height` (o `aspect-ratio`) espliciti per riservare lo spazio e prevenire layout shift al caricamento.
- Il lazy loading (`loading="lazy"`) va applicato solo alle immagini fuori dal viewport iniziale — quelle above-the-fold vanno caricate subito.
- Per foto con soggetto non centrato, usa `object-position` mirato invece del default center, così il crop responsive non taglia la parte importante.

