---
name: ux-tips
description: Raccolta di 85 tip pratici di UX/UI (micro-interazioni, componenti, accessibilità, mobile, performance percepita, dark mode, i18n) organizzati per argomento. Usa questa skill quando progetti, revisioni o generi interfacce utente e vuoi applicare pattern e dettagli UX consolidati invece di improvvisare.
license: MIT
metadata:
  author: user
  version: "2.0.0"
  date: 2026-08-10
  abstract: Guida di riferimento con 85 tip UX/UI, divisi in 7 file tematici sotto references/ per evitare di caricare tutto il contenuto in una volta. Ogni tip è un elenco puntato conciso con la regola pratica e il perché.
---

# UX/UI Tips

Raccolta di riferimento con 85 tip UX/UI concreti, divisi in file tematici sotto `references/` così puoi leggere solo la parte pertinente al task corrente.

## Quando usare questa skill

- Stai progettando o revisionando un componente UI (form, tabella, modal, toast, dropdown, ecc.).
- Stai facendo un audit UX di un'interfaccia esistente (anche generata da AI).
- Vuoi giustificare una scelta di design con un principio consolidato (psicologia, accessibilità, performance percepita).
- Stai scrivendo codice frontend e vuoi evitare errori comuni (layout shift, focus trap, contrasto, RTL, ecc.).

## Come usarla

Non leggere tutti i file: scegli quello (o quelli) pertinenti al task in base alla tabella sotto, poi cita la sezione (es. "vedi §55 focus state") invece di riscrivere il contenuto a memoria.

| File | Argomento | Sezioni |
|---|---|---|
| `references/psychology-and-motion.md` | Psicologia UI, micro-interazioni, motion, animazioni | §1,2,4,6-10,12,13,17,20,30-33,42 |
| `references/design-systems.md` | Design system, layout, grid, token | §5,11,14,16,18,21,67 |
| `references/components.md` | Componenti (form, nav, data, overlay, drag&drop...) | §15,22,23,25-29,34-41,43-51,56,58-61,64,69-71,76,78 |
| `references/accessibility-and-mobile.md` | Accessibilità, touch, mobile, notifiche push | §55,57,68,73-75,79 |
| `references/performance-and-loading.md` | Performance percepita, loading, attese, liste lunghe | §19,24,52-54,62,63,72,82,85 |
| `references/platform-and-i18n.md` | Dark mode, i18n/RTL, immagini responsive, overflow | §66,77,81,84 |
| `references/system-boundaries.md` | Client/server boundary, offline-first, onboarding, dark pattern | §3,65,80,83 |
