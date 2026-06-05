---
marp: true
theme: partec
paginate: false
---

<!-- Global footer — logo appears on every slide via CSS background -->
<!-- _footer: Mastering API Design at Scale · Roberto Polli -->

<style>
/* ────────────────────────────────────────────────────────────────
   FONT SETUP
   ──────────────────────────────────────────────────────────────── */

/*
  Option A — Use Abordage (commercial, if you have the file):
  Place Abordage-Regular.woff2 in assets/ and uncomment:

@font-face {
  font-family: "Abordage";
  src: url("assets/Abordage-Regular.woff2") format("woff2");
  font-weight: normal;
}
*/

/*
  Option B (default) — Free fallback via Google Fonts CDN.
  Add this <link> tag before rendering, or use --allow-local-files
  with a downloaded copy:
  https://fonts.google.com/specimen/Space+Grotesk
*/
@import url("https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Proxima+Nova:wght@400;500;700&display=swap");

/* ────────────────────────────────────────────────────────────────
   DESIGN TOKENS  — change these to retheme everything
   ──────────────────────────────────────────────────────────────── */
:root {
  --color-bg:      #F5F4EF;   /* off-white parchment */
  --color-black:   #0D0D0D;
  --color-yellow:  #C9B135;   /* golden yellow */
  --color-yellow2: #F5C842;   /* bright yellow (section slides) */
  --color-mint:    #B2EDD4;   /* mint green */
  --color-white:   #FFFFFF;

  --font-display:  "Abordage", "Space Grotesk", "Plus Jakarta Sans", sans-serif;
  --font-body:     "Proxima Nova", "Space Grotesk", system-ui, sans-serif;
  --font-mono:     "JetBrains Mono", "Fira Code", monospace;

  --logo-path:     url("assets/logo-partec.png");  /* ← change logo here */
}

/* ────────────────────────────────────────────────────────────────
   BASE SLIDE
   ──────────────────────────────────────────────────────────────── */
section {
  background-color: var(--color-bg);
  color: var(--color-black);
  font-family: var(--font-body);
  font-size: 28px;
  line-height: 1.5;
  padding: 60px 80px 100px 80px;
  width: 1280px;
  height: 720px;
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
}

/* ────────────────────────────────────────────────────────────────
   TYPOGRAPHY
   ──────────────────────────────────────────────────────────────── */
h1 {
  font-family: var(--font-display);
  font-size: 80px;
  font-weight: 400;
  line-height: 1.05;
  margin: 0 0 32px 0;
  color: var(--color-black);
}

h2 {
  font-family: var(--font-display);
  font-size: 52px;
  font-weight: 400;
  margin: 0 0 24px 0;
  color: var(--color-black);
}

h3 {
  font-family: var(--font-body);
  font-size: 28px;
  font-weight: 600;
  margin: 0 0 12px 0;
}

p, li {
  font-family: var(--font-body);
  font-size: 26px;
  line-height: 1.6;
  margin: 0 0 12px 0;
}

ul {
  padding-left: 1.2em;
  margin: 0;
}

li + li { margin-top: 6px; }

code {
  font-family: var(--font-mono);
  font-size: 0.85em;
  background: rgba(0,0,0,0.06);
  padding: 2px 6px;
  border-radius: 4px;
}

pre {
  font-family: var(--font-mono);
  font-size: 20px;
  background: var(--color-black);
  color: var(--color-white);
  padding: 24px 28px;
  border-radius: 8px;
  overflow: auto;
  line-height: 1.5;
}

pre code {
  background: none;
  padding: 0;
  font-size: inherit;
}

/* ────────────────────────────────────────────────────────────────
   FOOTER  (logo + slide meta)
   ──────────────────────────────────────────────────────────────── */
footer {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 72px;
  display: flex;
  align-items: center;
  padding: 0 80px;
  font-family: var(--font-body);
  font-size: 16px;
  color: rgba(255,255,255,0.85);
  background: transparent;
}

/* Logo disabled */
section::after { display: none; }

/* ────────────────────────────────────────────────────────────────
   DECORATIVE SHAPES  (left-side accent, used on most slides)
   ──────────────────────────────────────────────────────────────── */

/* The distinctive "octagon with hole" shape, top-left */
section.has-shapes::before {
  content: "";
  position: absolute;
  left: -20px;
  top: 30px;
  width: 380px;
  height: 400px;
  background: var(--shape-color, var(--color-yellow));
  clip-path: polygon(
    20% 0%, 80% 0%, 100% 20%, 100% 80%,
    80% 100%, 20% 100%, 0% 80%, 0% 20%
  );
  z-index: 0;
}

/* Inner cutout (white square) to simulate the "frame" look */
section.has-shapes .shape-cutout {
  position: absolute;
  left: 20px;
  top: 100px;
  width: 200px;
  height: 200px;
  background: var(--color-bg);
  z-index: 1;
}

/* Top corner decorative triangles (the "cat ears") */
section.has-shapes .shape-top {
  position: absolute;
  left: 60px;
  top: -10px;
  width: 200px;
  height: 80px;
  background: var(--shape-top-color, var(--color-black));
  clip-path: polygon(15% 100%, 42% 0%, 58% 100%, 100% 0%, 85% 100%);
  z-index: 2;
}

/* Bottom half-circle */
section.has-shapes .shape-bottom {
  position: absolute;
  left: 30px;
  bottom: -60px;
  width: 240px;
  height: 150px;
  background: var(--shape-bottom-color, var(--color-mint));
  border-radius: 120px 120px 0 0;
  z-index: 0;
}

/* Content area pushed right when shapes are present */
section.has-shapes .content {
  margin-left: 420px;
}

/* --- Three stacked hexagons (left accent) --- */
section.has-hexagons .hex-stack {
  position: absolute;
  left: 30px;
  top: 100px;
  display: flex;
  flex-direction: column;
  gap: 14px;
  z-index: 1;
}

section.has-hexagons .hex {
  width: 130px;
  height: 150px;
  background: var(--hex-color, var(--color-yellow));
  clip-path: polygon(50% 0%, 100% 25%, 100% 75%, 50% 100%, 0% 75%, 0% 25%);
}

section.has-hexagons .content {
  margin-left: 210px;
}

/* ────────────────────────────────────────────────────────────────
   SLIDE VARIANTS
   ──────────────────────────────────────────────────────────────── */

/* --- Cover / Title slide --- */
section.cover {
  background-color: var(--color-bg);
  color: var(--color-white);
  padding-left: 0;
  overflow: hidden;
}

section.cover .left-panel {
  position: absolute;
  left: 0; top: 0; bottom: 0;
  width: 480px;
  background: var(--color-black);
  display: flex;
  align-items: center;
  justify-content: center;
}

section.cover .title-area {
  margin-left: 540px;
  padding-top: 80px;
}

section.cover h1 {
  font-size: 72px;
  line-height: 1.0;
}

section.cover .subtitle {
  font-size: 26px;
  color: rgba(255,255,255,0.75);
  margin-top: 16px;
}

section.cover .author {
  position: absolute;
  bottom: 60px;
  left: 540px;
  font-size: 28px;
  font-weight: 500;
}

/* --- Section break slide (large title, dark bg) --- */
section.section-break {
  background-color: var(--color-black);
  color: var(--color-white);
}

section.section-break h1 {
  color: var(--color-white);
  font-size: 96px;
  line-height: 1.0;
  margin-top: 160px;
}

section.section-break .subtitle {
  color: rgba(255,255,255,0.65);
  font-size: 28px;
  margin-top: 8px;
}

section.section-break::after {
  filter: invert(1);  /* white logo on dark bg */
}

/* --- Two-column content --- */
section.two-col .columns {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 48px;
  margin-top: 8px;
}

/* --- Code-heavy slide --- */
section.code-slide pre {
  margin-top: 12px;
  font-size: 18px;
}

/* --- Geometric circles (half-moon decorations on left and right) --- */
section.circles {
  background-color: var(--color-bg);
  overflow: hidden;
}

section.circles .circle {
  position: absolute;
  border-radius: 50%;
  top: 50%;
  transform: translateY(-50%);
}

section.circles .yellow  { width:548px; height:548px; background:#F5A623;              left:-147px;  z-index:1; }
section.circles .black-l { width:413px; height:413px; background:var(--color-black);   left:-207px;  z-index:2; }
section.circles .blue    { width:548px; height:548px; background:#A8D8E8;              right:-147px; z-index:3; }
section.circles .black-r { width:413px; height:413px; background:var(--color-black);   right:-207px; z-index:4; }

/* Add rotate(180deg) to flip a crescent: transform: translateY(-50%) rotate(180deg) */

section.circles .content {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  z-index: 5;
}

/* --- Thank you / closing slide --- */
section.closing {
  background-color: var(--color-black);
  color: var(--color-white);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  padding-left: 600px;
}

section.closing h1 {
  color: var(--color-white);
  font-size: 110px;
  line-height: 0.95;
}

section.closing .contact {
  font-size: 30px;
  color: var(--color-mint);
  margin-top: 24px;
}

section.closing::after {
  filter: invert(1);
}
</style>

---

<!-- ═══════════════════════════════════════════════════════════════
     COVER SLIDE
     ═══════════════════════════════════════════════════════════════ -->

<!-- _class: cover -->

<div class="left-panel">
  <!-- decorative shapes rendered via CSS -->
</div>

<div class="title-area">

# Mastering API Design at Scale

<div class="subtitle">Resilient and well-documented APIs
that are easy to integrate</div>

<div class="author">Roberto Polli</div>

</div>

---

<!-- ═══════════════════════════════════════════════════════════════
     CONTENT SLIDE — with left shapes + right content
     ═══════════════════════════════════════════════════════════════ -->

<!-- _class: has-shapes -->

<div class="shape-top"></div>
<div class="shape-cutout"></div>
<div class="shape-bottom"></div>

<div class="content">

## Who am I?

Roberto Polli @ioggstream

Solutions Architect @ par-tec.it

Python enthusiast, IETF HTTP & HTTPAPI workgroup

5 years in the Italian Government's Digital Transformation Team

Red Hat, MongoDB | MySQL Certified

</div>

---

<!-- ═══════════════════════════════════════════════════════════════
     CONTENT SLIDE — three stacked yellow hexagons + right content
     Override hex colour: style="--hex-color: #C9B135"
     ═══════════════════════════════════════════════════════════════ -->

<!-- _class: has-hexagons -->

<div class="hex-stack">
  <div class="hex"></div>
  <div class="hex"></div>
  <div class="hex"></div>
</div>

<div class="content">

## Slide Title

- Bullet point one
- Bullet point two
- Bullet point three

</div>

---

<!-- ═══════════════════════════════════════════════════════════════
     AGENDA / BULLET LIST SLIDE
     ═══════════════════════════════════════════════════════════════ -->

## AGENDA

- Intro — environment setup & teaser
- Contract-First API Design
- Schema & Semantics
- Service Management, Caching and Throttling

---

<!-- ═══════════════════════════════════════════════════════════════
     SECTION BREAK SLIDE
     Usage: change --shape-color on the section element,
     and set a subtitle below the h1
     ═══════════════════════════════════════════════════════════════ -->

<!-- _class: section-break has-shapes -->
<!-- style: "section { --shape-color: #C9B135; --shape-top-color: #0D0D0D; }" -->

<div class="shape-top"></div>
<div class="shape-cutout"></div>
<div class="shape-bottom"></div>

<div class="content">

# Contract-First
API Design

<div class="subtitle">OpenAPI, JSON Schema, Connexion</div>

</div>

---

<!-- ═══════════════════════════════════════════════════════════════
     CONTENT SLIDE — plain (no left shapes)
     ═══════════════════════════════════════════════════════════════ -->

## Tutorial Setup

The tutorial is based on Jupyter notebooks.

**Code**
`https://github.com/ioggstream/python-course/`

**Instructions**
`https://github.com/ioggstream/python-course/blob/main/connexion-101/README.md`

---

<!-- ═══════════════════════════════════════════════════════════════
     TWO-COLUMN SLIDE
     ═══════════════════════════════════════════════════════════════ -->

<!-- _class: two-col -->

## Two-Column Layout

<div class="columns">
<div>

### Left column

- Point one
- Point two
- Point three

</div>
<div>

### Right column

- Another point
- And another
- More content here

</div>
</div>

---

<!-- ═══════════════════════════════════════════════════════════════
     CODE SLIDE
     ═══════════════════════════════════════════════════════════════ -->

<!-- _class: code-slide -->

## Contract-First: OpenAPI Example

```yaml
openapi: "3.0.0"
info:
  title: My API
  version: "1.0"
paths:
  /items/{item_id}:
    get:
      summary: Get an item
      parameters:
        - name: item_id
          in: path
          required: true
          schema:
            type: integer
      responses:
        "200":
          description: Success
```

---

<!-- ═══════════════════════════════════════════════════════════════
     SLIDE WITH IMAGE (logos, diagrams, etc.)
     ═══════════════════════════════════════════════════════════════ -->

<!-- _class: two-col -->

## Longtime Friends

<div class="columns">
<div>

### Left column

<!-- Replace with your own logos/images -->
![width:140px](assets/logo-pycon25.png) &nbsp;
![width:140px](assets/logo-europython.png) &nbsp;
![width:140px](assets/logo-kubecon.png)

</div>
<div>

### Right column

- Software & Infrastructure system integrator
- Active in the open source scene for 20+ years
- A team of 200+ employees with 200+ professional certifications

</div>
</div>

---

<!-- ═══════════════════════════════════════════════════════════════
     CIRCLES SLIDE — geometric half-moon decorations
     Yellow crescent left, blue crescent right, content centred.
     To flip a crescent add rotate(180deg) to its transform.
     ═══════════════════════════════════════════════════════════════ -->

<!-- _class: circles -->

<div class="circle yellow"></div>
<div class="circle black-l"></div>
<div class="circle blue"></div>
<div class="circle black-r"></div>

<div class="content">

# Title Here

<div class="subtitle">Subtitle or tagline</div>

</div>

---

<!-- ═══════════════════════════════════════════════════════════════
     CLOSING / THANK YOU SLIDE
     ═══════════════════════════════════════════════════════════════ -->

<!-- _class: closing has-shapes -->

<div class="shape-top" style="--shape-top-color: #C9B135;"></div>
<div class="shape-cutout" style="background: #0D0D0D;"></div>
<div class="shape-bottom" style="--shape-bottom-color: #C9B135;"></div>

# Thank
You!

<div class="contact">roberto.polli@par-tec.it</div>
