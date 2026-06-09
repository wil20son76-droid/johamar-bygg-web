# Johamar AB – Sitio Web

Sitio web de una sola página para Johamar AB, empresa de construcción y renovación en Kungsängen, Estocolmo.

---

## Cómo agregar nuevas fotos de proyectos

### Paso 1 — Prepara la imagen

- **Formato recomendado:** JPEG (`.jpg`) para fotos, PNG para imágenes con transparencia.
- **Tamaño recomendado:** 800 × 600 píxeles (ratio 4:3) o mayor. El sitio recorta automáticamente con `object-fit: cover`.
- **Peso máximo recomendado:** menos de 300 KB por imagen para que cargue rápido en móvil.
- **Tip:** Usa [Squoosh](https://squoosh.app) para comprimir la imagen sin perder calidad visible.

### Paso 2 — Sube la imagen a la carpeta correcta

Coloca el archivo en:

```
images/
  projects/
    tu-imagen.jpg
```

**Convención de nombres recomendada:**

```
[servicio]-[ciudad]-[numero].jpg
```

Ejemplos:
- `koksrenovering-kungsangen-1.jpg` → Köksrenovering en Kungsängen, primera foto
- `malning-stockholm-2.jpg` → Målning en Estocolmo, segunda foto
- `altan-bro-1.jpg` → Altan en Bro, primera foto
- `fasadrenovering-jarfalla-1.jpg` → Fasadrenovering en Järfälla

> Usa guiones (`-`), no espacios ni caracteres especiales en el nombre del archivo.

### Paso 3 — Añade el proyecto en el HTML

Abre el archivo `index.html` y busca la sección marcada con este comentario:

```html
<!-- PROYECTO 1 — Köksrenovering, Kungsängen -->
```

Copia cualquier bloque `<article>` completo y pégalo después del último `</article>` dentro del `<div class="projects-grid">`.

**Estructura de un proyecto:**

```html
<!-- PROYECTO N — Descripción corta -->
<article class="project-card reveal"
  data-category="Nombre del servicio"
  data-title="Título del proyecto"
  data-location="Ciudad, Región"
  data-desc="Descripción larga que aparece en el lightbox al hacer clic en la tarjeta.">

  <!-- Cambia el src por la ruta a tu imagen real -->
  <img class="pc-img" loading="lazy" width="800" height="600"
    src="images/projects/tu-imagen.jpg"
    alt="Descripción SEO de la imagen – ciudad – Johamar AB"
    onerror="this.style.display='none'">

  <div class="pc-bg"></div>
  <div class="pc-info">
    <span class="pc-category">Nombre del servicio</span>
    <h3>Tipo de propiedad, Ciudad</h3>
    <span class="pc-location">
      <i class="fa-solid fa-location-dot" aria-hidden="true"></i> Ciudad
    </span>
  </div>
  <div class="pc-zoom" aria-hidden="true">
    <i class="fa-solid fa-expand"></i>
  </div>
</article>
```

### Paso 4 (opcional) — Añadir vista "Antes / Después"

Si tienes una foto del estado original (antes) y una foto del resultado (después), puedes activar el botón "Före / Efter" en el lightbox:

```html
<article class="project-card reveal"
  data-category="Köksrenovering"
  data-title="Köksrenovering i Villa"
  data-location="Kungsängen"
  data-desc="Descripción del proyecto..."
  data-before="images/projects/koksrenovering-kungsangen-1-before.jpg"
  data-after="images/projects/koksrenovering-kungsangen-1.jpg">
  <img class="pc-img" loading="lazy" width="800" height="600"
    src="images/projects/koksrenovering-kungsangen-1.jpg"
    alt="Köksrenovering, Kungsängen – Johamar AB"
    onerror="this.style.display='none'">
  ...
</article>
```

El botón "Före / Efter" aparece automáticamente cuando ambos atributos (`data-before` y `data-after`) están presentes.

### Paso 5 — Reemplaza las imágenes de marcador de posición

Los tres primeros proyectos ya tienen nombres de archivo asignados. Simplemente sube tu foto real con el mismo nombre y se mostrará automáticamente:

| Archivo a reemplazar | Proyecto |
|---|---|
| `images/projects/koksrenovering-kungsangen-1.jpg` | Köksrenovering, Kungsängen |
| `images/projects/malning-stockholm-1.jpg` | Målning utomhus, Stockholm |
| `images/projects/altan-bro-1.jpg` | Altan & Trädäck, Bro |

> Si el archivo de imagen no existe, la tarjeta muestra un fondo degradado automáticamente. No rompe el diseño.

### Paso 6 — Verifica el resultado

Abre el sitio en el navegador y haz clic en una tarjeta de proyecto para ver el lightbox con la imagen completa, el título, la ubicación y la descripción.

- En **móvil:** desliza lateralmente entre proyectos.
- En **escritorio:** usa las teclas ← → para navegar y `Escape` para cerrar.

---

## Archivos principales

| Archivo | Descripción |
|---|---|
| `index.html` | Todo el sitio — HTML, CSS y JavaScript en un solo archivo |
| `logo.png` | Logotipo original (fondo transparente, 2000×803 px) |
| `logo-footer.png` | Versión del logotipo adaptada para el fondo oscuro del pie de página |
| `images/projects/` | Carpeta para fotos de proyectos |
| `favicon.ico` | Ícono del sitio |

---

## Servicios disponibles (para usar en `data-category`)

- Målning och tapetsering
- Köksrenovering
- Golvslipning och Golvläggning
- Altan & Trädäck
- Badrumsrenovering
- Taktvätt
- Fasadrenovering och Fasadmålning

---

## Contacto técnico

Para dudas sobre el sitio web: **info@johamarbygg.se**
