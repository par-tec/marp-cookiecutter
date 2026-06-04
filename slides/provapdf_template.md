---
marp: true
paginate: false
---

<!--
  Render:
    marp provapdf_template.md --html --output provapdf_template.html
    marp provapdf_template.md --html --pdf  --output provapdf_template.pdf

  Il flag --html è obbligatorio: le slide usano <div> con position:absolute.
  Canvas: 1440×810 (stesso formato degli SVG background).
-->

<style>
/* ── Canvas 1440×810 (stesso formato degli SVG di background) ───── */
section {
  width: 1440px;
  height: 810px;
  padding: 0;
  margin: 0;
  overflow: hidden;
  background: transparent;
}

/* Rimuove header/footer/logo del tema di default */
header, footer,
section::before, section::after { display: none !important; }

/* Reset elementi markdown che non usiamo come flow */
h1, h2, h3, p, ul, li { margin: 0; padding: 0; }

/* ── Elemento base per testi posizionati (coordinate 1:1 dal PDF) ── */
.t {
  position: absolute;
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.2;
  white-space: nowrap;
}

.t.wrap { white-space: normal; }
</style>

---

<!-- ══════════════════════════════════════════════
     SLIDE 1 — Cover
     Testo crema (#f8f7eb) su pannello scuro sx
     ══════════════════════════════════════════════ -->

<!-- _backgroundImage: url("assets/img/SLIDE2.svg") -->
<!-- _backgroundSize: cover -->

<div class="t" style="left:106px;top:63px;width:405px;font-size:70px;color:#f8f7eb;font-weight:bold;line-height:1.15">Template<br>Par-Tec<br>istituzionale</div>

---

<!-- ══════════════════════════════════════════════
     SLIDE 2 — Header doppio + numero pagina
     ══════════════════════════════════════════════ -->

<!-- _backgroundImage: url("assets/img/SLIDE6.svg") -->
<!-- _backgroundSize: cover -->

<div class="t" style="left:88px;top:72px;font-size:19px;color:#000000">Par-Tec S.p,A.</div>
<div class="t" style="left:1031px;top:70px;font-size:19px;color:#000000">Success stories tecnologia Dynatrace</div>
<div class="t" style="left:87px;top:740px;font-size:19px;color:#1f0202">2</div>

---

<!-- ══════════════════════════════════════════════
     SLIDE 3 — Contenuto: Titolo Capitolo + corpo
     ══════════════════════════════════════════════ -->

<!-- _backgroundImage: url("assets/img/SLIDE3.svg") -->
<!-- _backgroundSize: cover -->

<div class="t" style="left:88px;top:72px;font-size:19px;color:#585858">Par-Tec S.p.A.</div>
<div class="t" style="left:1258px;top:94px;font-size:19px;color:#000000">Titolo slide</div>
<div class="t" style="left:88px;top:269px;width:204px;font-size:32px;color:#000000">Titolo  Capitolo</div>
<div class="t wrap" style="left:88px;top:379px;width:550px;font-size:23px;color:#000000;line-height:28px">Inserire qui il tuo testo non farlo troppo lungo e tieni in considerazione che questo testo di esempio è della lunghezza sufficiente. Non ridurre il carattere o l'interlinea, attieniti a questo spazio e, semmai lo ritenessi più opportuno, potresti utilizzare un carattere grassetto.</div>
<div class="t" style="left:87px;top:745px;font-size:18px;color:#f8f7eb">3</div>

---

<!-- ══════════════════════════════════════════════
     SLIDE 4 — Sidebar navigazione + contenuto sx
     ══════════════════════════════════════════════ -->

<!-- _backgroundImage: url("assets/img/SLIDE3.svg") -->
<!-- _backgroundSize: cover -->

<div class="t" style="left:88px;top:72px;font-size:19px;color:#585858">Par-Tec S.p.A.</div>
<div class="t" style="left:88px;top:228px;font-size:32px;color:#000000;font-weight:bold">titolo</div>
<div class="t" style="left:88px;top:334px;font-size:23px;color:#000000">Text</div>
<div class="t" style="left:961px;top:96px;font-size:32px;color:#000000">• Presentazione BU<br>Technolo-</div>
<div class="t" style="left:97px;top:751px;font-size:19px;color:#1f0202">4</div>

---

<!-- ══════════════════════════════════════════════
     SLIDE 5 — Solo grafica / immagini
     ══════════════════════════════════════════════ -->

<!-- _backgroundImage: url("assets/img/SLIDE3.svg") -->
<!-- _backgroundSize: cover -->

---

<!-- ══════════════════════════════════════════════
     SLIDE 6 — Solo grafica / immagini
     ══════════════════════════════════════════════ -->

<!-- _backgroundImage: url("assets/img/SLIDE3.svg") -->
<!-- _backgroundSize: cover -->

---

<!-- ══════════════════════════════════════════════
     SLIDE 7 — Contenuto (variante senza header)
     ══════════════════════════════════════════════ -->

<!-- _backgroundImage: url("assets/img/SLIDE3.svg") -->
<!-- _backgroundSize: cover -->

<div class="t" style="left:1258px;top:94px;font-size:19px;color:#000000">Titolo slide</div>
<div class="t" style="left:88px;top:269px;width:204px;font-size:32px;color:#000000">Titolo  Capitolo</div>
<div class="t wrap" style="left:88px;top:379px;width:550px;font-size:23px;color:#000000;line-height:28px">Inserire qui il tuo testo non farlo troppo lungo e tieni in considerazione che questo testo di esempio è della lunghezza sufficiente. Non ridurre il carattere o l'interlinea, attieniti a questo spazio e, semmai lo ritenessi più opportuno, potresti utilizzare un carattere grassetto.</div>
<div class="t" style="left:97px;top:753px;font-size:19px;color:#1f0202">7</div>

---

<!-- ══════════════════════════════════════════════
     SLIDE 8 — Contatti footer
     ══════════════════════════════════════════════ -->

<!-- _backgroundImage: url("assets/img/SLIDE6.svg") -->
<!-- _backgroundSize: cover -->

<div class="t" style="left:142px;top:725px;font-size:24px;color:#000000;font-weight:bold">www.par-tec.it</div>
<div class="t" style="left:421px;top:725px;font-size:24px;color:#000000;font-weight:bold">info@par-tec.it</div>
<div class="t" style="left:700px;top:722px;font-size:24px;color:#000000;font-weight:bold">Milano: +39 02 667321</div>
<div class="t" style="left:1062px;top:722px;font-size:24px;color:#000000;font-weight:bold">Roma: +39 06 98269600</div>

---

<!-- ══════════════════════════════════════════════
     SLIDE 9 — Solo grafica / immagini
     ══════════════════════════════════════════════ -->

<!-- _backgroundImage: url("assets/img/SLIDE6.svg") -->
<!-- _backgroundSize: cover -->

---

<!-- ══════════════════════════════════════════════
     SLIDE 10 — Griglia 6 box (Titolo 1–6)
     ══════════════════════════════════════════════ -->

<!-- _backgroundImage: url("assets/img/SLIDE6.svg") -->
<!-- _backgroundSize: cover -->

<div class="t" style="left:81px;top:211px;font-size:70px;color:#1f0202;font-weight:bold">Titolo 3</div>
<div class="t" style="left:204px;top:379px;width:101px;font-size:29px;color:#000000;font-weight:bold">Titolo 1<br>Te -</div>
<div class="t" style="left:204px;top:530px;width:101px;font-size:29px;color:#000000;font-weight:bold">Titolo 3<br>Te -</div>
<div class="t" style="left:638px;top:380px;width:101px;font-size:29px;color:#000000;font-weight:bold">Titolo 2<br>Te -</div>
<div class="t" style="left:638px;top:530px;width:101px;font-size:29px;color:#000000;font-weight:bold">Titolo 4<br>Te -</div>
<div class="t" style="left:1075px;top:378px;width:101px;font-size:29px;color:#000000;font-weight:bold">Titolo 5<br>Te -</div>
<div class="t" style="left:1075px;top:528px;width:101px;font-size:29px;color:#000000;font-weight:bold">Titolo 6<br>Te -</div>
<div class="t" style="left:88px;top:751px;font-size:19px;color:#f8f7eb">10</div>

---

<!-- ══════════════════════════════════════════════
     SLIDE 11 — Tabella placeholder
     ══════════════════════════════════════════════ -->

<!-- _backgroundImage: url("assets/img/SLIDE6.svg") -->
<!-- _backgroundSize: cover -->

<div class="t" style="left:81px;top:166px;font-size:70px;color:#1f0202;font-weight:bold">Esempio Tabella</div>
<div class="t" style="left:88px;top:751px;font-size:19px;color:#f8f7eb">11</div>

---

<!-- ══════════════════════════════════════════════
     SLIDE 12 — Lista 01/02/03
     Numeri bianchi sopra cerchi scuri (nell'SVG)
     ══════════════════════════════════════════════ -->

<!-- _backgroundImage: url("assets/img/SLIDE3.svg") -->
<!-- _backgroundSize: cover -->

<div class="t" style="left:1258px;top:94px;font-size:19px;color:#000000">Titolo slide</div>
<div class="t" style="left:871px;top:186px;font-size:26px;color:#ffffff;font-weight:bold">01</div>
<div class="t" style="left:871px;top:368px;font-size:26px;color:#ffffff;font-weight:bold">02</div>
<div class="t" style="left:871px;top:539px;font-size:26px;color:#ffffff;font-weight:bold">03</div>
<div class="t" style="left:94px;top:753px;font-size:19px;color:#1f0202">12</div>

---

<!-- ══════════════════════════════════════════════
     SLIDE 13 — Solo grafica / immagini
     ══════════════════════════════════════════════ -->

<!-- _backgroundImage: url("assets/img/SLIDE6.svg") -->
<!-- _backgroundSize: cover -->

---

<!-- ══════════════════════════════════════════════
     SLIDE 14 — Testo + etichette grafico a torta
     ══════════════════════════════════════════════ -->

<!-- _backgroundImage: url("assets/img/SLIDE6.svg") -->
<!-- _backgroundSize: cover -->

<div class="t" style="left:81px;top:176px;font-size:70px;color:#1f0202;font-weight:bold">Tar-</div>
<div class="t wrap" style="left:81px;top:349px;width:625px;font-size:29px;color:#1f0202;line-height:36px">Irure dolore velit excepteur Lorem eiusmod qui aliquip velit esse ipsum nulla occaecat.</div>
<div class="t wrap" style="left:81px;top:481px;width:602px;font-size:21px;color:#1f0202;line-height:26px">Irure dolore velit excepteur Lorem eiusmod culpa et ipsum occaecat ut in excepteur consectetur qui aliquip velit esse ipsum nulla occaecat id ad sint in nulla incididunt cupidatat nisi officia est ex eu amet aute ullamco nostrud eu magna magna mollit commodo proident aliqua officia culpa occaecat.</div>
<div class="t" style="left:87px;top:745px;font-size:19px;color:#1f0202">14</div>
<div class="t" style="left:906px;top:177px;font-size:14px;color:#1f0202">Age 18-25</div>
<div class="t" style="left:911px;top:235px;font-size:14px;color:#1f0202">Age 25-35</div>
<div class="t" style="left:1068px;top:219px;font-size:15px;color:#1f0202">Gender</div>
<div class="t" style="left:1075px;top:403px;font-size:14px;color:#1f0202">Age 35-45</div>
<div class="t" style="left:1086px;top:438px;font-size:15px;color:#1f0202">Gender</div>
<div class="t" style="left:1066px;top:473px;font-size:14px;color:#1f0202">33% Female</div>
<div class="t" style="left:923px;top:483px;font-size:14px;color:#1f0202">33% Other</div>
<div class="t" style="left:930px;top:518px;font-size:14px;color:#1f0202">33% Male</div>

---

<!-- ══════════════════════════════════════════════
     SLIDE 15 — Grafico placeholder (A)
     ══════════════════════════════════════════════ -->

<!-- _backgroundImage: url("assets/img/SLIDE3.svg") -->
<!-- _backgroundSize: cover -->

<div class="t" style="left:70px;top:264px;font-size:60px;color:#000000;font-weight:bold">GRAFICO 1</div>
<div class="t" style="left:112px;top:400px;font-size:42px;color:#000000;line-height:50px">•  Fare clic per modificare gli<br>stili del testo dello schema<br>•  ⚬  Secondo livello<br>•  ⚬  Terzo livello</div>
<div class="t" style="left:213px;top:565px;font-size:27px;color:#000000">•  Quarto livello<br>•  ⚬  Quinto livello</div>
<div class="t" style="left:87px;top:741px;font-size:18px;color:#f8f7eb">15</div>

---

<!-- ══════════════════════════════════════════════
     SLIDE 16 — Grafico placeholder (B)
     ══════════════════════════════════════════════ -->

<!-- _backgroundImage: url("assets/img/SLIDE3.svg") -->
<!-- _backgroundSize: cover -->

<div class="t" style="left:70px;top:264px;font-size:60px;color:#000000;font-weight:bold">GRAFICO 1</div>
<div class="t" style="left:112px;top:400px;font-size:42px;color:#000000;line-height:50px">•  Fare clic per modificare gli<br>stili del testo dello schema<br>•  ⚬  Secondo livello<br>•  ⚬  Terzo livello</div>
<div class="t" style="left:213px;top:583px;font-size:27px;color:#000000">•  Quarto livello</div>
<div class="t" style="left:87px;top:745px;font-size:19px;color:#1f0202">16</div>

---

<!-- ══════════════════════════════════════════════
     SLIDE 17 — Icone placeholder
     ══════════════════════════════════════════════ -->

<!-- _backgroundImage: url("assets/img/SLIDE6.svg") -->
<!-- _backgroundSize: cover -->

<div class="t" style="left:79px;top:153px;font-size:18px;color:#000000;font-weight:bold">TI SERVONO DELLE ICONE?</div>
<div class="t" style="left:92px;top:751px;font-size:19px;color:#1f0202">17</div>
