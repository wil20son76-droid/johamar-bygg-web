# Johamar AB — Guía de migración a WordPress / Divi
**Dominio destino:** johamarbygg.se  
**Fecha:** Junio 2026  
**Paleta:** Greige cálido (`#D8D2C8`) · Azul-carbón oscuro (`#1A2535`) · Naranja Johamar (`#C8520A`)

---

## Índice

1. [SEO Básico](#1-seo-básico)
2. [Configuración inicial en Divi](#2-configuración-inicial-en-divi)
3. [Estructura sección por sección](#3-estructura-sección-por-sección)
4. [CSS personalizado para Divi Theme Options](#4-css-personalizado)
5. [HTML por secciones (módulos Code)](#5-html-por-secciones)
6. [Recomendaciones de imágenes](#6-recomendaciones-de-imágenes)
7. [Optimización móvil — checklist](#7-optimización-móvil)
8. [Plugins recomendados](#8-plugins-recomendados)

---

## 1. SEO Básico

### Título de la página (SEO title)
```
Johamar AB – Byggfirma i Kungsängen & Stockholm | Renovering, Målning, Köksrenovering
```

### Meta description
```
Johamar AB är din lokala byggfirma i Kungsängen och Stockholm. Vi utför renovering, målning, köksrenovering, golvläggning, fasadrenovering och altaner i Upplands-Bro, Järfälla och Sollentuna. Kostnadsfri offert – ring 0723213232.
```

### H1 (en Hero)
```
Vi bygger drömmar — du lever dem
```

### H2 por sección
| Sección | H2 |
|---|---|
| Tjänster | Våra Tjänster |
| Om oss | Om Johamar AB |
| Varför | Varför välja Johamar? |
| Process | Så här arbetar vi |
| Projekt | Senaste Projekt |
| Omdömen | Vad kunderna säger |
| Google CTA | Vad tycker våra kunder? |
| Kontakt | Begär din kostnadsfria offert |

### Palabras clave locales a incluir en el contenido
- Byggfirma Stockholm
- Renovering Kungsängen
- Målare Upplands-Bro
- Köksrenovering Järfälla
- Golvläggning Sollentuna
- Fasadrenovering Stockholm
- Altanbyggare Kungsängen

### URL Slug
```
/ (página de inicio)
```

### Configurar en Yoast SEO / Rank Math
- **Focus keyword:** `byggfirma kungsängen`
- **OG Image:** foto de portada del hero (obra terminada o equipo trabajando)
- **Schema type:** LocalBusiness → Contractor

---

## 2. Configuración inicial en Divi

### 2.1 Tipografías (Divi > Theme Options > Typography)
| Uso | Fuente | Peso |
|---|---|---|
| Títulos (H1–H4) | **Sora** | 800 |
| Cuerpo / UI | **DM Sans** | 400 / 500 |

→ Importar desde Google Fonts añadiendo en **Divi > Theme Options > General > Custom CSS** (o via plugin `Google Fonts for WordPress`):
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Sora:wght@700;800&family=DM+Sans:wght@400;500;600&display=swap" rel="stylesheet">
```
También pegar en **Divi > Theme Options > Integration > Add code to the <head> of your blog**.

### 2.2 Colores del Brand (guardar en Divi Global Colors)
| Nombre | Hex |
|---|---|
| Johamar Orange | `#C8520A` |
| Johamar Orange Light | `#E8651A` |
| Dark Charcoal | `#1A2535` |
| Dark Steel | `#212E42` |
| Dark Slate | `#273448` |
| Greige Canvas | `#D8D2C8` |
| Greige Stone | `#CDCABE` |
| Card Cream | `#ECE8E1` |
| Text Dark | `#1F2937` |
| Text Body | `#374151` |
| Text Sub | `#4B5563` |
| Off-White | `#EDE8E1` |

### 2.3 Botones globales (Divi > Theme Customizer > Buttons)
- **Botón primario:** fondo `#C8520A`, texto `#FFFFFF`, radio `6px`, padding `15px 32px`
- **Botón secundario (outline):** fondo transparente, borde `#EDE8E1 1.5px solid`, texto `#EDE8E1`

---

## 3. Estructura sección por sección

### ORDEN DE LA PÁGINA
```
NAV (Header fijo)
│
├── 1. HERO
├── 2. STATS BAR
├── 3. TJÄNSTER (Servicios)
├── 4. OM OSS (Sobre nosotros)
├── 5. VARFÖR VÄLJA OSS
├── 6. VÅR ARBETSPROCESS
├── 7. SENASTE PROJEKT (Galería)
├── 8. OMDÖMEN (Testimonios)
├── 9. GOOGLE CTA
├── 10. KONTAKT (Formulario)
│
└── FOOTER
```

---

### SECCIÓN 1 — HERO

**Módulo Divi:** `Fullwidth Header` o `Section` con fondo oscuro + `Text Module`

**Configuración:**
- Background: color `#1A2535`
- Background overlay: gradiente `180deg, #1A2535 0%, #212E42 100%`
- Height: `100vh` (añadir via CSS)
- Padding: `120px 0`

**Contenido:**
```
EYEBROW:    Professionell Byggfirma i Stockholm
H1:         Vi bygger drömmar — du lever dem
PÁRRAFO:    Professionell byggfirma i Stockholm och Kungsängen – 
            målning, renovering, altaner och mycket mer sedan 2012.
BOTÓN 1:    [Begär kostnadsfri offert]  → link: #kontakt
BOTÓN 2:    [Se våra tjänster]          → link: #tjanster
```

**Badge (usar Text Module posicionado):**
```
🛡  Försäkrad & certifierad
    ROT-avdrag godkänt
```

---

### SECCIÓN 2 — STATS BAR

**Módulo Divi:** `Section` (fondo `#212E42`) + `Blurb Module` × 4 o `Number Counter` × 4

**Configuración:**
- Background: `#212E42`
- Columnas: 4 iguales
- Border-left naranja en cada stat (via CSS)

**Contenido:**
| Número | Texto |
|---|---|
| 72+ | Genomförda projekt |
| 14 | Års erfarenhet |
| 98% | Nöjda kunder |
| 1 | Aktivt team |

---

### SECCIÓN 3 — TJÄNSTER (Servicios)

**Módulo Divi:** `Section` (fondo `#D8D2C8`) + `Blurb Module` × 6 en grid 3×2

**Configuración:**
- Background: `#D8D2C8`
- Blurb background: `#ECE8E1`
- Border-radius en Blurb: `12px`
- Icon color: `#C8520A`

**Eyebrow:** `Vad vi gör`  
**H2:** `Våra Tjänster`  
**Intro:** Vi erbjuder ett brett utbud av bygg- och renoveringstjänster i Stockholm, Kungsängen och hela Upplands-Bro. Alla uppdrag utförs av erfarna hantverkare med fokus på kvalitet och nöjda kunder.

**Tarjetas de servicio:**

| Ícono FA | Título | Texto |
|---|---|---|
| `fa-paint-roller` | Målning och tapetsering | Certifierade målare som utför invändig och utvändig målning samt tapetsering med noggrannhet och hållbara resultat i Stockholm och omnejd. |
| `fa-kitchen-set` | Köksrenovering | Helrenovering av kök med fokus på funktion, design och kvalitet – från planering till färdigt drömkök. |
| `fa-grip-lines` | Golvslipning & Golvläggning | Vi slipar, behandlar och lägger golv med precision – och återställer dina parkettgolv till nyskick. |
| `fa-tree` | Altaner & Terrasser | Vi bygger och renoverar altaner och terrasser som håller länge och skapar en trivsam utemiljö. |
| `fa-house` | Taktvätt | Professionell taktvätt som avlägsnar mossa, alger och smuts – och förlänger takets livslängd avsevärt. |
| `fa-building` | Fasadrenovering & Fasadmålning | Vi renoverar och målar fasader som skyddar din fastighet mot väder och vind – och ger den ett nytt ansikte. |

**CTA bajo las tarjetas:**
```
Inte hittat vad du söker? Kontakta oss →
[Kontakta oss för en kostnadsfri offert]  → link: #kontakt
```

---

### SECCIÓN 4 — OM OSS

**Módulo Divi:** `Section` (fondo degradado oscuro) + `Text Module` (izquierda) + `Image Module` (derecha)

**Configuración:**
- Background: `linear-gradient(155deg, #1D2D40 0%, #273448 55%, #212E42 100%)`
- Layout: 2 columnas (60% / 40%)
- Padding: `120px 0`

**Eyebrow:** `Om Johamar AB`  
**H2:** `Lokal expertis – personlig service`

**Texto:**
```
Johamar AB grundades 2012 och har sedan dess hjälpt fastighetsägare i 
Stockholm, Kungsängen och Upplands-Bro med allt från mindre renoveringar 
till större ombyggnationer. Vi är en lokal byggfirma med ett starkt 
engagemang för kvalitet och kundnöjdhet.

Som en etablerad renoveringsfirma i Stockholmsregionen kombinerar vi 
gedigen hantverkserfarenhet med modern teknik och noggranna metoder. 
Vår lokala förankring ger oss god kännedom om regionens byggkrav, 
klimatförutsättningar och leverantörsnätverk – något som gör hela 
processen smidigare för dig.

Vi tar varje uppdrag på allvar, oavsett storlek. Varje projekt utförs 
med samma höga standard, tydlig kommunikation och ett personligt 
engagemang som du märker från första kontakt till spikat sista spik.
```

**Lista de puntos (checkmarks naranjas):**
- Erfarna och certifierade hantverkare
- Lokal kännedom om Stockholm och omnejd
- Kvalitetsgaranti på allt utfört arbete
- Tydlig kommunikation och fasta tidsramar

**Imagen derecha:** logo Johamar sobre fondo texturizado oscuro (o foto del equipo)

---

### SECCIÓN 5 — VARFÖR VÄLJA OSS

**Módulo Divi:** `Section` (fondo greige) + `Blurb Module` × 6 en grid 3×2

**Configuración:**
- Background: `linear-gradient(155deg, #CDCABE 0%, #D8D2C8 50%, #CDCABE 100%)`
- Blurb background: `#ECE8E1`
- Border-radius: `16px`

**Eyebrow:** `Varför välja oss`  
**H2:** `Varför välja Johamar?`

| Ícono | Título | Texto |
|---|---|---|
| `fa-star` | Kvalitet i varje detalj | Vi väljer material noggrant, arbetar metodiskt och lämnar aldrig ett jobb halvfärdigt. Resultatet ska se bra ut inte bara i dag – utan om tio år. |
| `fa-shield-halved` | Trygg process från start till mål | Tydligt avtal, realistisk tidsplan och löpande uppdateringar via din föredragna kanal. Du vet alltid var vi är i processen. |
| `fa-hammer` | Bred erfarenhet inom bygg & renovering | Sedan 2012 har vi genomfört projekt av alla storlekar i Stockholmsregionen. Erfarenheten syns i detaljerna. |
| `fa-comments` | Personlig service och tydlig kommunikation | Du pratar direkt med ansvarig hantverkare, inte en mellanhand. Vi svarar snabbt och håller dig informerad. |
| `fa-sliders` | Lösningar anpassade efter dig | Vi lyssnar på dina önskemål, din budget och din tidsram – och tar fram den lösning som passar din situation bäst. |
| `fa-location-dot` | Lokal närvaro i Stockholm med omnejd | Med bas i Kungsängen betjänar vi Stockholm, Upplands-Bro, Järfälla, Sollentuna, Täby och Sundbyberg. |

**CTA box (usar Text Module con fondo naranja suave):**
```
Verksamma sedan 2012 i Stockholm och Kungsängen — 
vi finns nära dig och levererar alltid med stolthet.

[Kontakta oss för en kostnadsfri offert]
```

---

### SECCIÓN 6 — VÅR ARBETSPROCESS

**Módulo Divi:** `Section` (fondo oscuro) + `Number Counter` o `Blurb Module` × 4 en 1 fila

**Configuración:**
- Background: `linear-gradient(155deg, #1D2D40 0%, #273448 55%, #212E42 100%)`
- Layout: 4 columnas iguales
- Separador naranja entre columnas

**Eyebrow:** `Vår arbetsprocess`  
**H2:** `Så här arbetar vi`  
**Intro:** Från första kontakt till färdigt projekt — en tydlig och trygg process där du alltid vet vad som händer härnäst.

| Paso | Ícono | Título | Texto |
|---|---|---|---|
| 01 | `fa-comments` | Kostnadsfri konsultation | Vi lyssnar på dina behov och önskemål, diskuterar projektet och svarar på alla dina frågor utan kostnad. |
| 02 | `fa-file-contract` | Offert & planering | Vi tar fram en tydlig offert och en genomtänkt projektplan med tidsram och material — inga dolda kostnader. |
| 03 | `fa-screwdriver-wrench` | Utförande | Vårt team utför arbetet med precision, kvalitetsmaterial och löpande kommunikation — alltid i tid och enligt plan. |
| 04 | `fa-circle-check` | Slutkontroll & nöjd kund | Vi går igenom projektet tillsammans, säkerställer att allt möter vår kvalitetsstandard och att du är helt nöjd. |

**CTA:**
```
Redo att ta nästa steg? Vi erbjuder alltid kostnadsfri konsultation 
och offert utan förbindelser.

[Boka kostnadsfri konsultation]  → link: #kontakt
```

---

### SECCIÓN 7 — SENASTE PROJEKT (Galería)

**Módulo Divi:** `Section` (fondo `#212E42`) + `Portfolio Module` o `Filterable Portfolio`

**Configuración:**
- Background: `#212E42`
- Usar categorías de WordPress para filtrar: Köksrenovering, Målning, Altaner, Fasad, Badrum, Golv
- Efecto hover: overlay naranja suave
- Columns: 3 (desktop), 2 (tablet), 1 (móvil)

**Eyebrow:** `Vårt arbete`  
**H2:** `Senaste Projekt`

**Si no usas Portfolio Module, usar Gallery Module con estas entradas:**

| Imagen | Categoría | Título | Ubicación |
|---|---|---|---|
| koksrenovering-kungsangen-1.jpg | Köksrenovering | Köksrenovering i Villa | Kungsängen |
| malning-stockholm-1.jpg | Målning utomhus | Utvändig Målning | Stockholm |
| altan-bro-1.jpg | Altan & Trädäck | Altan & Trädäck | Bro |
| *(añadir)* | Fasadrenovering | Fasadrenovering | Järfälla |
| *(añadir)* | Badrumsrenovering | Badrumsrenovering | Stockholm |
| *(añadir)* | Golvläggning | Parkettgolv | Stockholm |

---

### SECCIÓN 8 — OMDÖMEN (Testimonios)

**Módulo Divi:** `Section` (fondo greige) + `Testimonial Module` × 4 o slider

**Configuración:**
- Background: `linear-gradient(155deg, #D2CCC2 0%, #CDCABE 50%, #CFCABD 100%)`
- Card background: `#ECE8E1`
- Estrellas: color `#C8520A`
- Layout: 4 tarjetas en fila horizontal con scroll en móvil

**Eyebrow:** `Vad kunderna säger`  
**H2:** `Vad kunderna säger`

**Testimonios:**

```
★★★★★
"Johamar renoverade vårt kök från grunden. Professionellt bemötande, 
snyggt slutresultat och de höll både tid och budget."
— Anna Lindqvist, Kungsängen

★★★★★
"Vi anlitade dem för att bygga en altan och är jättenöjda. 
Snabb kontakt, schysst pris och fint hantverk."
— Mikael Berg, Bro

★★★★★
"Fasadrenoveringen blev över förväntan. Noggranna hantverkare 
som städade efter sig varje dag. Rekommenderas varmt!"
— Sara Holm, Järfälla

★★★★★
"Snabb respons, tydlig offert och ett härligt gäng som gjorde om 
vårt badrum på utsatt tid. Toppenresultat!"
— Johan Ekström, Stockholm
```

---

### SECCIÓN 9 — GOOGLE CTA

**Módulo Divi:** `Section` (fondo `#212E42`) + `Text Module` (izquierda) + `Code Module` (derecha, tarjeta Google)

**Configuración:**
- Background: `#212E42`
- Layout: 2 columnas (50/50)

**Eyebrow:** `Vad tycker våra kunder?`  
**H2:** `Vad tycker våra kunder?`

**Texto izquierda:**
```
Har vi hjälpt dig med ditt projekt? Vi uppskattar din feedback. 
Dina recensioner hjälper oss att växa och hjälper nya kunder 
att känna sig trygga med sitt val.
```

**Tarjeta Google (Code Module, derecha):**
```html
<div style="background:linear-gradient(145deg,rgba(20,24,32,0.9),rgba(15,42,74,0.4));
     border:1px solid rgba(237,232,225,0.1);border-radius:20px;padding:40px 36px;
     text-align:center;">
  <div style="display:flex;align-items:center;justify-content:center;gap:10px;margin-bottom:20px;">
    <div style="width:36px;height:36px;border-radius:50%;background:#fff;
         display:flex;align-items:center;justify-content:center;font-weight:700;">
      <span style="background:linear-gradient(135deg,#4285F4 0% 25%,#EA4335 25% 50%,
           #FBBC05 50% 75%,#34A853 75% 100%);-webkit-background-clip:text;
           -webkit-text-fill-color:transparent;font-size:1.2rem;font-weight:800;">G</span>
    </div>
    <strong style="color:#EDE8E1;font-size:1rem;">Google Recensioner</strong>
  </div>
  <div style="color:#FBBC05;font-size:1.5rem;letter-spacing:4px;margin-bottom:8px;">★★★★★</div>
  <p style="font-size:3rem;font-weight:800;color:#EDE8E1;line-height:1;margin:0 0 4px;">5,0</p>
  <p style="font-size:0.82rem;color:#8A9099;margin-bottom:28px;">Baserat på Google-recensioner</p>
  <a href="https://g.page/r/CeP5kmNfpg7SEBM/review" target="_blank" rel="noopener"
     style="display:block;width:100%;padding:16px;background:#fff;color:#202124;
     border-radius:8px;font-weight:600;text-decoration:none;font-size:0.95rem;">
    ⭐ Lämna ett omdöme
  </a>
</div>
```

---

### SECCIÓN 10 — KONTAKT

**Módulo Divi:** `Section` (fondo `#D8D2C8`) + columna izquierda `Text Module` + columna derecha `Contact Form Module`

**Configuración:**
- Background: `#D8D2C8`
- Form background: `#ECE8E1`
- Layout: 2 columnas (45% / 55%)

**Eyebrow:** `Hör av dig idag`  
**H2:** `Begär din kostnadsfria offert`

**Texto + datos izquierda:**
```
Fyll i formuläret eller ring oss direkt – vi återkommer inom 
24 timmar med ett svar. Vi täcker Stockholm, Kungsängen, 
Upplands-Bro och omgivande kommuner.

📍 Mullbärstigen 7, 196 34 Kungsängen
📞 0723213232 / 0720324203
✉  info@johamarbygg.se
⏰ Mån–Fre 07:00–18:00

[Skriv till oss på WhatsApp]  → https://wa.me/46723213232
```

**Formulario (Contact Form Module):**
| Campo | Tipo | Obligatorio |
|---|---|---|
| Namn | Text | Sí |
| E-post | Email | Sí |
| Telefon | Tel | Sí |
| Tjänst | Select | Sí |
| Meddelande | Textarea | No |

**Opciones del Select Tjänst:**
- Målning och tapetsering
- Köksrenovering
- Golvslipning & Golvläggning
- Altaner & Terrasser
- Taktvätt
- Fasadrenovering & Fasadmålning
- Badrumsrenovering
- Annat

**Email destino del formulario:** `info@johamarbygg.se`  
**Asunto del email:** `Ny förfrågan via johamarbygg.se – {Tjänst}`

---

### FOOTER

**Módulo Divi:** `Footer` global (Divi Builder en pie de página) + 4 columnas

**Configuración:**
- Background: `#1A2535`
- Border-top: `1px solid rgba(255,255,255,0.04)`
- Padding: `58px 0 42px`

**Columna 1 — Marca:**
```
[Logo footer versión clara]
Professionell byggfirma i Stockholm och Kungsängen sedan 2012.

[Icono Facebook]  [Icono Instagram]  [Icono WhatsApp]
```

**Columna 2 — Navigation:**
```
NAVIGATION
• Hem
• Tjänster
• Om oss
• Projekt
• Kontakt
```

**Columna 3 — Tjänster:**
```
TJÄNSTER
• Målning och tapetsering
• Köksrenovering
• Golvslipning & Golvläggning
• Altaner & Terrasser
• Taktvätt
• Fasadrenovering
```

**Columna 4 — Kontakt:**
```
KONTAKT
Mullbärstigen 7
196 34 Kungsängen

0723213232
0720324203
info@johamarbygg.se
Mån–Fre 07:00–18:00
```

**Copyright bar** (fondo `#0E1926`):
```
© 2025 Johamar AB · Mullbärstigen 7, 196 34 Kungsängen · 
Org.nr: 559XXX-XXXX · info@johamarbygg.se
```

---

## 4. CSS Personalizado

Pegar en **Divi > Theme Options > General > Custom CSS**:

```css
/* =============================================
   JOHAMAR AB — CSS personalizado para Divi
   johamarbygg.se
   ============================================= */

/* === TIPOGRAFÍAS === */
@import url('https://fonts.googleapis.com/css2?family=Sora:wght@700;800&family=DM+Sans:wght@400;500;600&display=swap');

:root {
  --jm-dark:        #1A2535;
  --jm-steel:       #212E42;
  --jm-slate:       #273448;
  --jm-canvas:      #D8D2C8;
  --jm-stone:       #CDCABE;
  --jm-card:        #ECE8E1;
  --jm-orange:      #C8520A;
  --jm-orange-lt:   #E8651A;
  --jm-text-dark:   #1F2937;
  --jm-text-body:   #374151;
  --jm-text-sub:    #4B5563;
  --jm-off-white:   #EDE8E1;
  --jm-muted:       #8A9099;
}

body,
.et_pb_section .et_pb_text,
.et_pb_section .et_pb_blurb_description {
  font-family: 'DM Sans', sans-serif;
  color: var(--jm-text-body);
}

h1, h2, h3, h4,
.et_pb_title_container h1,
.et_pb_module_header,
.et_pb_blurb_title {
  font-family: 'Sora', sans-serif;
  font-weight: 800;
  line-height: 1.15;
}

/* === EYEBROW LABELS === */
.jm-eyebrow {
  display: inline-block;
  font-family: 'DM Sans', sans-serif;
  font-weight: 600;
  font-size: 0.85rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  margin-bottom: 12px;
}
.jm-eyebrow--light { color: var(--jm-orange-lt); }  /* sobre fondos oscuros */
.jm-eyebrow--dark  { color: #8B3505; }              /* sobre fondos greige */

/* === SECCIÓN HERO === */
.jm-hero-section {
  min-height: 100vh;
  background: linear-gradient(180deg, #1A2535 0%, #212E42 100%) !important;
  display: flex;
  align-items: center;
}
.jm-hero-section h1 {
  font-size: clamp(2.4rem, 7vw, 4.6rem);
  color: var(--jm-off-white);
}
.jm-hero-section .et_pb_text_inner p {
  color: var(--jm-off-white);
  opacity: 0.85;
  font-size: clamp(1rem, 2.4vw, 1.3rem);
  max-width: 560px;
}

/* === BARRA DE STATS === */
.jm-stats-section {
  background: var(--jm-steel) !important;
  border-top: 1px solid rgba(237,232,225,0.06);
  border-bottom: 1px solid rgba(237,232,225,0.06);
}
.jm-stats-section .et_pb_number_counter_title,
.jm-stats-section .et_pb_more_button {
  color: var(--jm-off-white) !important;
}
.jm-stats-section .et_pb_counter_amount {
  background-color: var(--jm-orange) !important;
  color: var(--jm-orange) !important;
}
.jm-stats-section h2 {
  color: var(--jm-orange);
  font-size: clamp(2.2rem, 5vw, 3.2rem);
}

/* === SECCIONES GREIGE (servicios, varför, omdömen, contacto) === */
.jm-greige-section {
  background: var(--jm-canvas) !important;
  color: var(--jm-text-dark);
}
.jm-greige-section h2,
.jm-greige-section h3 {
  color: var(--jm-text-dark) !important;
}
.jm-greige-section p {
  color: var(--jm-text-body);
}

/* === SECCIONES OSCURAS (om oss, process) === */
.jm-dark-section {
  background: linear-gradient(155deg, #1D2D40 0%, #273448 55%, #212E42 100%) !important;
}
.jm-dark-section h2,
.jm-dark-section h3 {
  color: var(--jm-off-white) !important;
}
.jm-dark-section p,
.jm-dark-section .et_pb_blurb_description {
  color: rgba(237,232,225,0.80);
}

/* === TARJETAS SERVICIO / VARFÖR === */
.jm-card {
  background: var(--jm-card) !important;
  border: 1px solid rgba(31,41,55,0.08) !important;
  border-radius: 12px !important;
  transition: transform 0.35s ease, box-shadow 0.35s ease, border-color 0.35s ease !important;
}
.jm-card:hover {
  transform: translateY(-8px) !important;
  box-shadow: 0 20px 50px rgba(31,41,55,0.14) !important;
  border-color: rgba(200,82,10,0.28) !important;
}
.jm-card .et_pb_blurb_title,
.jm-card h3 {
  color: var(--jm-text-dark) !important;
}
.jm-card .et_pb_blurb_description,
.jm-card p {
  color: var(--jm-text-body) !important;
}
/* Barra naranja superior al hacer hover */
.jm-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 3px;
  background: linear-gradient(90deg, #C8520A, #E8651A);
  opacity: 0;
  transition: opacity 0.35s ease;
  border-radius: 12px 12px 0 0;
}
.jm-card:hover::before { opacity: 1; }

/* === ÍCONO CHIP (fondo tarjetas) === */
.jm-icon-chip {
  width: 56px;
  height: 56px;
  border-radius: 12px;
  background: linear-gradient(150deg, rgba(200,82,10,0.12), rgba(15,42,74,0.10));
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
  font-size: 1.5rem;
  color: var(--jm-orange);
}

/* === BOTONES === */
.jm-btn-primary,
.et_pb_button.jm-btn-primary {
  background: linear-gradient(135deg, #E8651A, #C8520A) !important;
  color: #fff !important;
  border: none !important;
  border-radius: 6px !important;
  padding: 15px 32px !important;
  font-family: 'DM Sans', sans-serif !important;
  font-weight: 500 !important;
  box-shadow: 0 6px 20px rgba(200,82,10,0.28) !important;
  transition: all 0.3s ease !important;
}
.jm-btn-primary:hover,
.et_pb_button.jm-btn-primary:hover {
  transform: translateY(-2px) !important;
  box-shadow: 0 14px 36px rgba(200,82,10,0.45) !important;
}
.jm-btn-outline,
.et_pb_button.jm-btn-outline {
  background: transparent !important;
  color: var(--jm-off-white) !important;
  border: 1.5px solid rgba(237,232,225,0.4) !important;
  border-radius: 6px !important;
  padding: 15px 32px !important;
  transition: all 0.3s ease !important;
}
.jm-btn-outline:hover {
  border-color: var(--jm-off-white) !important;
  background: rgba(237,232,225,0.08) !important;
}

/* === TESTIMONIOS === */
.jm-testimonial-card {
  background: var(--jm-card) !important;
  border: 1px solid rgba(26,31,44,0.08);
  border-radius: 14px;
  padding: 32px;
  box-shadow: 0 2px 16px rgba(26,31,44,0.07);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}
.jm-testimonial-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 40px rgba(26,31,44,0.12);
  border-color: rgba(200,82,10,0.28);
}
.jm-testimonial-card .et_pb_testimonial_quote,
.jm-testimonial-card p {
  color: var(--jm-text-body) !important;
  font-style: italic;
}
.jm-testimonial-card .et_pb_testimonial_author {
  color: var(--jm-text-dark) !important;
  font-family: 'Sora', sans-serif;
  font-weight: 700;
}
.jm-testimonial-card .et_pb_testimonial_company {
  color: var(--jm-text-sub) !important;
  font-size: 0.85rem;
}

/* === PROCESO (pasos) === */
.jm-process-step-num {
  width: 56px;
  height: 56px;
  border-radius: 50%;
  background: rgba(10,18,32,0.75);
  border: 2px solid var(--jm-orange);
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 32px;
  font-size: 1.2rem;
  color: var(--jm-orange);
  transition: background 0.35s ease, transform 0.35s ease;
}
.jm-process-step:hover .jm-process-step-num {
  background: var(--jm-orange);
  color: #fff;
  transform: scale(1.1);
}

/* === FORMULARIO DE CONTACTO === */
.jm-contact-form,
.et_pb_contact_form_container {
  background: var(--jm-card) !important;
  border-radius: 16px !important;
  padding: 40px !important;
  border: 1px solid rgba(15,15,15,0.08) !important;
  box-shadow: 0 30px 80px rgba(15,15,15,0.06) !important;
}
.et_pb_contact_field input,
.et_pb_contact_field select,
.et_pb_contact_field textarea {
  background: #F0EDE8 !important;
  border: 1.5px solid rgba(15,15,15,0.14) !important;
  border-radius: 8px !important;
  font-family: 'DM Sans', sans-serif !important;
  color: var(--jm-text-dark) !important;
  padding: 14px 16px !important;
}
.et_pb_contact_field input:focus,
.et_pb_contact_field select:focus,
.et_pb_contact_field textarea:focus {
  border-color: var(--jm-orange) !important;
  outline: none !important;
}

/* === FOOTER === */
.et_pb_footer_container {
  background: var(--jm-dark) !important;
  color: var(--jm-off-white) !important;
}
.et_pb_footer_container h4,
.footer-widget h4 {
  font-size: 0.82rem;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: rgba(237,232,225,0.45) !important;
  font-weight: 600;
}
.et_pb_footer_container a {
  color: rgba(237,232,225,0.65) !important;
  transition: color 0.25s ease;
}
.et_pb_footer_container a:hover {
  color: var(--jm-orange) !important;
}
#bottom-bar {
  background: #0E1926 !important;
  color: rgba(237,232,225,0.35) !important;
  font-size: 0.82rem;
}

/* === BOTÓN WHATSAPP FIJO === */
.jm-whatsapp-float {
  position: fixed;
  bottom: 28px;
  right: 24px;
  z-index: 9999;
  width: 56px;
  height: 56px;
  border-radius: 50%;
  background: #25D366;
  color: #fff;
  font-size: 1.6rem;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 6px 20px rgba(37,211,102,0.5);
  text-decoration: none;
  transition: transform 0.25s ease;
}
.jm-whatsapp-float:hover {
  transform: scale(1.1) translateY(-4px);
  color: #fff;
}

/* === REVEAL ANIMATIONS === */
@keyframes jm-fadeUp {
  from { opacity: 0; transform: translateY(32px); }
  to   { opacity: 1; transform: translateY(0); }
}
.jm-reveal {
  animation: jm-fadeUp 0.8s ease both;
}

/* === MOBILE === */
@media (max-width: 768px) {
  .jm-hero-section h1 {
    font-size: clamp(2rem, 9vw, 3rem);
  }
  .jm-whatsapp-float {
    bottom: 20px;
    right: 16px;
    width: 50px;
    height: 50px;
    font-size: 1.4rem;
  }
  .et_pb_contact_form_container {
    padding: 24px 20px !important;
  }
  .jm-card {
    margin-bottom: 16px;
  }
}

@media (max-width: 480px) {
  .et_pb_section .et_pb_column {
    padding-left: 16px !important;
    padding-right: 16px !important;
  }
  .jm-btn-primary,
  .jm-btn-outline {
    white-space: normal;
    text-align: center;
    line-height: 1.4;
    width: 100%;
  }
}
```

---

## 5. HTML por Secciones

Para usar con **módulos "Code"** dentro de Divi. Útil si prefieres control total sobre el markup.

---

### 5.1 Hero — Code Module

```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<section id="hero" style="
  min-height: 100vh;
  background: linear-gradient(135deg, #1A2535 0%, #1D2D40 50%, #212E42 100%);
  display: flex; align-items: center;
  position: relative; overflow: hidden;
  padding: 120px 24px;">

  <!-- Textura sutil de fondo -->
  <div style="position:absolute;inset:0;
    background: radial-gradient(circle at 78% 28%, rgba(200,82,10,0.18), transparent 52%),
                radial-gradient(circle at 16% 82%, rgba(15,42,74,0.4), transparent 50%);
    pointer-events:none;"></div>

  <div style="max-width:1200px;margin:0 auto;position:relative;z-index:1;">
    <span style="display:inline-block;color:#E8651A;font-weight:600;
      letter-spacing:0.12em;text-transform:uppercase;font-size:0.85rem;
      margin-bottom:16px;">Professionell Byggfirma i Stockholm</span>

    <h1 style="font-family:'Sora',sans-serif;font-weight:800;
      font-size:clamp(2.4rem,7vw,4.6rem);line-height:1.1;
      color:#EDE8E1;margin-bottom:24px;max-width:760px;">
      Vi bygger drömmar<br>— du lever dem
    </h1>

    <div style="height:3px;background:#C8520A;width:140px;margin-bottom:36px;"></div>

    <p style="font-size:clamp(1rem,2.4vw,1.3rem);color:#EDE8E1;
      opacity:0.85;max-width:540px;margin-bottom:40px;line-height:1.6;">
      Professionell byggfirma i Stockholm och Kungsängen – målning, renovering,
      altaner och mycket mer sedan 2012.
    </p>

    <div style="display:flex;flex-wrap:wrap;gap:18px;">
      <a href="#kontakt" style="
        display:inline-flex;align-items:center;gap:10px;
        padding:15px 32px;border-radius:6px;text-decoration:none;
        background:linear-gradient(135deg,#E8651A,#C8520A);
        color:#fff;font-weight:600;font-size:0.95rem;
        box-shadow:0 6px 20px rgba(200,82,10,0.35);">
        <i class="fa-solid fa-arrow-right"></i> Begär kostnadsfri offert
      </a>
      <a href="#tjanster" style="
        display:inline-flex;align-items:center;gap:10px;
        padding:15px 32px;border-radius:6px;text-decoration:none;
        border:1.5px solid rgba(237,232,225,0.4);
        color:#EDE8E1;font-weight:500;font-size:0.95rem;">
        Se våra tjänster
      </a>
    </div>
  </div>

  <!-- Badge: ROT-avdrag -->
  <div style="position:absolute;bottom:48px;right:48px;
    background:rgba(26,30,36,0.7);backdrop-filter:blur(10px);
    border:1px solid rgba(237,232,225,0.12);
    padding:16px 24px;border-radius:10px;
    display:flex;align-items:center;gap:14px;">
    <i class="fa-solid fa-shield-halved" style="font-size:1.6rem;color:#C8520A;"></i>
    <div>
      <strong style="display:block;font-family:'Sora',sans-serif;
        font-size:0.95rem;color:#EDE8E1;">Försäkrad & certifierad</strong>
      <span style="font-size:0.8rem;color:#8A9099;">ROT-avdrag godkänt</span>
    </div>
  </div>
</section>
```

---

### 5.2 Stats Bar — Code Module

```html
<section style="background:#212E42;padding:64px 24px;
  border-top:1px solid rgba(237,232,225,0.06);
  border-bottom:1px solid rgba(237,232,225,0.06);">
  <div style="max-width:1200px;margin:0 auto;
    display:grid;grid-template-columns:repeat(4,1fr);gap:32px;text-align:center;">
    
    <div style="padding:0 12px;border-left:2px solid rgba(200,82,10,0.35);">
      <div style="font-family:'Sora',sans-serif;font-weight:800;
        font-size:clamp(2.2rem,5vw,3.2rem);color:#C8520A;">72+</div>
      <div style="color:#8A9099;font-size:0.95rem;margin-top:6px;">Genomförda projekt</div>
    </div>
    <div style="padding:0 12px;border-left:2px solid rgba(200,82,10,0.35);">
      <div style="font-family:'Sora',sans-serif;font-weight:800;
        font-size:clamp(2.2rem,5vw,3.2rem);color:#C8520A;">14</div>
      <div style="color:#8A9099;font-size:0.95rem;margin-top:6px;">Års erfarenhet</div>
    </div>
    <div style="padding:0 12px;border-left:2px solid rgba(200,82,10,0.35);">
      <div style="font-family:'Sora',sans-serif;font-weight:800;
        font-size:clamp(2.2rem,5vw,3.2rem);color:#C8520A;">98%</div>
      <div style="color:#8A9099;font-size:0.95rem;margin-top:6px;">Nöjda kunder</div>
    </div>
    <div style="padding:0 12px;border-left:2px solid rgba(200,82,10,0.35);">
      <div style="font-family:'Sora',sans-serif;font-weight:800;
        font-size:clamp(2.2rem,5vw,3.2rem);color:#C8520A;">2012</div>
      <div style="color:#8A9099;font-size:0.95rem;margin-top:6px;">Grundat</div>
    </div>
  </div>
</section>
```

---

### 5.3 Botón WhatsApp fijo — Code Module (en Footer o Theme Builder)

```html
<a href="https://wa.me/46723213232" target="_blank" rel="noopener"
   aria-label="Kontakta oss på WhatsApp"
   style="position:fixed;bottom:28px;right:24px;z-index:9999;
     width:56px;height:56px;border-radius:50%;
     background:#25D366;color:#fff;font-size:1.6rem;
     display:flex;align-items:center;justify-content:center;
     box-shadow:0 6px 20px rgba(37,211,102,0.5);
     text-decoration:none;transition:transform 0.25s ease;"
   onmouseover="this.style.transform='scale(1.1) translateY(-4px)'"
   onmouseout="this.style.transform='scale(1) translateY(0)'">
  <i class="fa-brands fa-whatsapp"></i>
</a>
```

---

### 5.4 Proceso (4 pasos) — Code Module

```html
<section style="background:linear-gradient(155deg,#1D2D40 0%,#273448 55%,#212E42 100%);
  padding:120px 24px;position:relative;overflow:hidden;">
  
  <div style="max-width:1200px;margin:0 auto;">
    <!-- Header -->
    <div style="text-align:center;max-width:620px;margin:0 auto 80px;">
      <span style="display:block;color:#E8651A;font-weight:600;
        letter-spacing:0.12em;text-transform:uppercase;
        font-size:0.85rem;margin-bottom:14px;">Vår arbetsprocess</span>
      <h2 style="font-family:'Sora',sans-serif;font-weight:800;color:#EDE8E1;
        font-size:clamp(2rem,5vw,3rem);margin-bottom:18px;">Så här arbetar vi</h2>
      <p style="color:rgba(237,232,225,0.72);font-size:1.02rem;line-height:1.7;">
        Från första kontakt till färdigt projekt — en tydlig och trygg process 
        där du alltid vet vad som händer härnäst.
      </p>
    </div>

    <!-- Pasos -->
    <div style="display:grid;grid-template-columns:repeat(4,1fr);
      gap:32px;text-align:center;">
      
      <div>
        <div style="width:56px;height:56px;border-radius:50%;
          background:rgba(10,18,32,0.75);border:2px solid #C8520A;
          display:flex;align-items:center;justify-content:center;
          margin:0 auto 32px;font-size:1.2rem;color:#C8520A;position:relative;">
          <i class="fa-solid fa-comments"></i>
          <span style="position:absolute;top:-10px;right:-10px;
            width:22px;height:22px;border-radius:50%;
            background:#C8520A;color:#fff;font-size:0.65rem;
            font-weight:700;display:flex;align-items:center;justify-content:center;">01</span>
        </div>
        <h3 style="font-family:'Sora',sans-serif;color:#EDE8E1;
          font-size:1rem;font-weight:700;margin-bottom:12px;">Kostnadsfri konsultation</h3>
        <p style="font-size:0.88rem;color:rgba(237,232,225,0.70);line-height:1.65;">
          Vi lyssnar på dina behov och önskemål, diskuterar projektet och svarar 
          på alla dina frågor utan kostnad.
        </p>
      </div>

      <div>
        <div style="width:56px;height:56px;border-radius:50%;
          background:rgba(10,18,32,0.75);border:2px solid #C8520A;
          display:flex;align-items:center;justify-content:center;
          margin:0 auto 32px;font-size:1.2rem;color:#C8520A;position:relative;">
          <i class="fa-solid fa-file-contract"></i>
          <span style="position:absolute;top:-10px;right:-10px;
            width:22px;height:22px;border-radius:50%;
            background:#C8520A;color:#fff;font-size:0.65rem;
            font-weight:700;display:flex;align-items:center;justify-content:center;">02</span>
        </div>
        <h3 style="font-family:'Sora',sans-serif;color:#EDE8E1;
          font-size:1rem;font-weight:700;margin-bottom:12px;">Offert & planering</h3>
        <p style="font-size:0.88rem;color:rgba(237,232,225,0.70);line-height:1.65;">
          Vi tar fram en tydlig offert och en genomtänkt projektplan 
          med tidsram och material — inga dolda kostnader.
        </p>
      </div>

      <div>
        <div style="width:56px;height:56px;border-radius:50%;
          background:rgba(10,18,32,0.75);border:2px solid #C8520A;
          display:flex;align-items:center;justify-content:center;
          margin:0 auto 32px;font-size:1.2rem;color:#C8520A;position:relative;">
          <i class="fa-solid fa-screwdriver-wrench"></i>
          <span style="position:absolute;top:-10px;right:-10px;
            width:22px;height:22px;border-radius:50%;
            background:#C8520A;color:#fff;font-size:0.65rem;
            font-weight:700;display:flex;align-items:center;justify-content:center;">03</span>
        </div>
        <h3 style="font-family:'Sora',sans-serif;color:#EDE8E1;
          font-size:1rem;font-weight:700;margin-bottom:12px;">Utförande</h3>
        <p style="font-size:0.88rem;color:rgba(237,232,225,0.70);line-height:1.65;">
          Vårt team utför arbetet med precision, kvalitetsmaterial och 
          löpande kommunikation — alltid i tid och enligt plan.
        </p>
      </div>

      <div>
        <div style="width:56px;height:56px;border-radius:50%;
          background:rgba(10,18,32,0.75);border:2px solid #C8520A;
          display:flex;align-items:center;justify-content:center;
          margin:0 auto 32px;font-size:1.2rem;color:#C8520A;position:relative;">
          <i class="fa-solid fa-circle-check"></i>
          <span style="position:absolute;top:-10px;right:-10px;
            width:22px;height:22px;border-radius:50%;
            background:#C8520A;color:#fff;font-size:0.65rem;
            font-weight:700;display:flex;align-items:center;justify-content:center;">04</span>
        </div>
        <h3 style="font-family:'Sora',sans-serif;color:#EDE8E1;
          font-size:1rem;font-weight:700;margin-bottom:12px;">Slutkontroll & nöjd kund</h3>
        <p style="font-size:0.88rem;color:rgba(237,232,225,0.70);line-height:1.65;">
          Vi går igenom projektet tillsammans, säkerställer att allt möter 
          vår kvalitetsstandard och att du är helt nöjd.
        </p>
      </div>
    </div>

    <!-- CTA -->
    <div style="text-align:center;margin-top:80px;">
      <p style="color:rgba(237,232,225,0.78);font-size:1.05rem;
        margin-bottom:24px;font-weight:500;">
        Redo att ta nästa steg? Vi erbjuder alltid kostnadsfri konsultation och offert utan förbindelser.
      </p>
      <a href="#kontakt" style="
        display:inline-flex;align-items:center;gap:10px;
        padding:15px 32px;border-radius:6px;text-decoration:none;
        background:linear-gradient(135deg,#E8651A,#C8520A);
        color:#fff;font-weight:600;font-size:0.95rem;
        box-shadow:0 6px 20px rgba(200,82,10,0.35);">
        Boka kostnadsfri konsultation
      </a>
    </div>
  </div>
</section>
```

---

## 6. Recomendaciones de imágenes

### Hero
- **Tipo:** Foto profesional de una renovación terminada (cocina o salón moderno en casa sueca)  
- **Alternativa:** Foto del equipo trabajando en una obra  
- **Dimensiones mínimas:** 1920×1080 px  
- **Formato:** WebP (< 200 KB) o JPEG optimizado  
- **Alt text:** `Johamar AB – Professionell renovering i Kungsängen och Stockholm`  
- **Dónde buscar:** Unsplash (buscar "swedish kitchen renovation", "scandinavian home renovation"), Pexels, o fotos propias del equipo

### Servicios (tarjetas)
| Servicio | Imagen sugerida |
|---|---|
| Målning | Pintor profesional aplicando pintura en una pared clara |
| Köksrenovering | Cocina renovada moderna, tonos neutros |
| Golvslipning | Suelo de parquet antes/después, o maquinaria de pulido |
| Altaner | Terraza de madera con jardín sueco |
| Taktvätt | Tejado limpio vs. con musgo (antes/después) |
| Fasadrenovering | Fachada de casa sueca recién pintada |

### Galería de proyectos (antes/después)
Para el slider "Före / Efter" en la galería:

| Archivo `before` | Archivo `after` | Descripción |
|---|---|---|
| `koksrenovering-before.jpg` | `koksrenovering-kungsangen-1.jpg` | Cocina antes y después |
| `malning-before.jpg` | `malning-stockholm-1.jpg` | Fachada antes y después |
| `altan-before.jpg` | `altan-bro-1.jpg` | Terraza antes y después |

**Guía para fotos propias:**
- Fotografía en horizontal (4:3 o 16:9)
- Misma posición exacta para "antes" y "después"  
- Buena luz natural, sin flash directo  
- Resolución mínima 1200×900 px  
- Comprimir en [Squoosh.app](https://squoosh.app) a < 250 KB por imagen  

### Logo en footer
- Usar `logo-footer.png` (versión para fondo oscuro)
- Altura recomendada en footer: 46px

---

## 7. Optimización móvil

### Checklist en Divi (Responsive Mode)

- [ ] **Hero:** Reducir H1 a `clamp(2rem, 9vw, 3rem)` en móvil  
- [ ] **Hero CTAs:** Stack vertical en móvil (flex-direction: column)  
- [ ] **Stats bar:** 2×2 en tablet, 2×2 en móvil  
- [ ] **Tarjetas de servicio:** 1 columna en móvil  
- [ ] **About:** columna única (texto arriba, imagen abajo)  
- [ ] **Varför:** 1 columna en móvil  
- [ ] **Proceso:** 2 columnas en tablet, 1 columna en móvil  
- [ ] **Galería:** 1 columna en móvil  
- [ ] **Testimonios:** scroll horizontal o stack  
- [ ] **Google CTA:** columna única en móvil  
- [ ] **Formulario:** padding reducido, botón full-width  
- [ ] **Footer:** 2 columnas en tablet, 1 columna en móvil  
- [ ] **WhatsApp float:** visible siempre (bottom-right, 50×50px)  
- [ ] **Botones:** `white-space: normal` + `text-align: center` en móvil  
- [ ] **Padding secciones:** reducir a `72px 0` en móvil  
- [ ] **Container padding:** `0 16px` en móvil  

### Breakpoints a configurar en Divi
| Breakpoint | Ancho |
|---|---|
| Desktop | > 1024px |
| Tablet | 768px – 1024px |
| Móvil | < 768px |
| Móvil pequeño | < 480px |

---

## 8. Plugins recomendados

| Plugin | Uso | Gratis/Pago |
|---|---|---|
| **Yoast SEO** o **Rank Math** | SEO, meta tags, Schema LocalBusiness | Gratis |
| **WP Rocket** o **LiteSpeed Cache** | Velocidad y caché | WP Rocket €59/año |
| **Smush** o **ShortPixel** | Optimización automática de imágenes | Gratis (básico) |
| **Contact Form 7** o usar Divi Contact | Formulario de contacto | Gratis |
| **WP Mail SMTP** | Envío fiable de formularios por email | Gratis |
| **Google Analytics for WordPress (MonsterInsights)** | Analytics | Gratis |
| **Really Simple SSL** | Forzar HTTPS | Gratis |
| **Wordfence** | Seguridad | Gratis |
| **Divi Pixel** | Módulos extra para Divi | Pago |

### Configuración crítica post-instalación
1. **SSL:** Activar HTTPS en el hosting y con Really Simple SSL
2. **Caché:** Configurar WP Rocket / LiteSpeed para excluir el formulario de contacto
3. **SMTP:** Configurar WP Mail SMTP con el email `info@johamarbygg.se`
4. **Schema:** En Yoast/Rank Math, configurar tipo de organización como `LocalBusiness > Contractor` con:
   - Nombre: Johamar AB
   - Teléfono: +46723213232
   - Dirección: Mullbärstigen 7, 196 34 Kungsängen
   - Área de servicio: Stockholm, Kungsängen, Upplands-Bro, Järfälla, Sollentuna

---

## Resumen del flujo de trabajo en Divi

```
1. Instalar WordPress + Divi en johamarbygg.se
2. Instalar plugins: Yoast, WP Rocket, Smush, WP Mail SMTP
3. Crear página de inicio en blanco (Divi Builder)
4. Pegar CSS personalizado en Divi > Theme Options > Custom CSS
5. Añadir fuentes Sora + DM Sans en <head>
6. Configurar colores globales del brand
7. Construir sección por sección siguiendo esta guía
8. Para control total: usar módulos "Code" con el HTML de la Sección 5
9. Configurar formulario → email: info@johamarbygg.se
10. Añadir botón WhatsApp fijo en Theme Builder > Footer
11. Subir fotos de proyectos (imágenes/projects/)
12. Configurar SEO con Yoast (title, meta, schema)
13. Verificar en móvil real (360px, 390px, 430px)
14. Activar caché y optimización de imágenes
15. Publicar ✓
```

---

*Documento generado para johamarbygg.se · Johamar AB · Junio 2026*
