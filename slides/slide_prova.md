---
marp: true
theme: partec
paginate: false
---

<style>
/*
  SVG canvas: 1440×810  →  Marp canvas: 1280×720  (scala 8/9)
  SLIDE2 / SLIDE5: pannello scuro a sinistra, crema da x=703 SVG → x≈625 Marp
  SLIDE3 / SLIDE6: sfondo tutto chiaro, forme decorative come bg
*/

/* Cover — SLIDE2: contenuto nel pannello crema (metà destra) */
section.sv-cover {
  padding-left: 640px;
}

/* Content — SLIDE3: testo libero su sfondo chiaro */
section.sv-content {
  /* il padding base del tema (60/80/100/80) va bene */
}

/* Closing — SLIDE5: contenuto nel pannello crema (metà destra) */
section.sv-closing {
  padding-left: 640px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

section.sv-closing h1 {
  font-size: 96px;
  line-height: 1.0;
  margin-bottom: 16px;
}

section.sv-closing .contact {
  font-size: 26px;
  color: rgba(13,13,13,0.6);
}
</style>

---

<!-- ═══════════════════════════════════════════════════════════════
     SLIDE 1 — COVER
     SVG: SLIDE2  (sfondo scuro sx, pannello crema dx da x≈625px)
     ═══════════════════════════════════════════════════════════════ -->

<!-- _class: sv-cover -->

![bg](assets/img/istituzionale/cover.svg)

# Titolo Presentazione

<div class="subtitle">Sottotitolo o descrizione breve</div>

<div class="author">Nome Autore</div>

---

<!-- ═══════════════════════════════════════════════════════════════
     SLIDE 2 — CONTENUTO
     SVG: SLIDE3  (sfondo chiaro con forme geometriche decorative)
     ═══════════════════════════════════════════════════════════════ -->

<!-- _class: sv-content -->

![bg](assets/img/SLIDE3.svg)

## Titolo Sezione

- Punto uno
- Punto due
- Punto tre

---

<!-- ═══════════════════════════════════════════════════════════════
     SLIDE 3 — CHIUSURA
     SVG: SLIDE5  (sfondo scuro sx, pannello crema dx da x≈625px)
     ═══════════════════════════════════════════════════════════════ -->

<!-- _class: sv-closing -->

![bg](assets/img/SLIDE5.svg)

# Grazie!

<div class="contact">nome.cognome@par-tec.it</div>
