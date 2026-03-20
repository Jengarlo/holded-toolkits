# Holded Toolkits — Guía de replicación

Guía para crear nuevos toolkits de sector a partir de un documento Word, siguiendo la estructura y diseño de los Toolkits de Servicios Profesionales.

---

## Estructura de archivos

Cada toolkit contiene:

```
holded-toolkits-[sector]/
├── index.html                              ← Página de selección INTERNO/EXTERNO
├── holded-[sector]-INTERNO.html            ← Versión para el equipo de Sales
├── holded-[sector]-EXTERNO.html            ← Versión para compartir con clientes
├── Font_Awesome_7_Pro-Solid-900.otf
├── Font_Awesome_7_Pro-Light-300.otf
├── Font_Awesome_7_Pro-Regular-400.otf
└── Font_Awesome_7_Pro-Thin-100.otf
```

---

## Tokens de diseño

### Colores
| Variable | Valor | Uso |
|---|---|---|
| `--gray-900` | `#111827` | Textos, fondos oscuros, badges |
| `--gray-500` | `#6B7280` | Textos secundarios |
| `--gray-400` | `#9CA3AF` | Textos sutiles, paso 3 |
| `--gray-100` | `#F3F4F6` | Fondos de bloque gris, cards |
| `--white` | `#FFFFFF` | Fondo documento, cards |
| `--red` | `#FF5454` | Solo en INTERNO: pain points |
| `#4B5563` | — | Paso 2 (gris medio) |

### Tipografía
- **Fuente principal**: Inter (Google Fonts)
- **Fuente iconos**: Font Awesome 7 Pro (archivos .otf locales)
- **Tamaños clave**: 60px (hero), 40px (títulos sección), 20px (subtítulo hero), 16px (subtítulos bloque), 10px (cuerpo), 8.365px (barra de progreso)

### Ancho del documento
- **Doc width**: `691px` (variable CSS `--doc-width`)
- **Contenido principal**: `433–513px` centrado

---

## Secciones del documento EXTERNO

### 1. Header Logo
Logo Holded centrado en la parte superior.

### 2. Hero
- **Título**: 60px, semibold, tracking -3.3px, line-height 0.85
- **Tagline**: 20px, color `--gray-400`
- **Descripción**: 10px, ancho 293px, centrado
- **Imagen**: 330px ancho × 318px alto, border-radius 8px

### 3. ¿Te suenan estos retos?
Lista numerada. Cada ítem con:
- Número en recuadro negro (`background: #111827`, `border-radius: 2.625px`, `16×16px`)
- Texto en gris 10px

### 4. Bloque gris — `grey-block`
`background: #F3F4F6`, `padding: 80px 0`, `gap: 30px`

Contiene 3 subsecciones:

#### 4a. ¿Por qué Holded es tu solución?
- Texto intro centrado (10px, ancho 433px)
- Grid 2 columnas (`gap: 10px`, ancho 433px)
- Cards blancas con badge negro como título (`padding: 2px 7px`, `border-radius: 3px`)
- Última card a ancho completo

#### 4b. ¿Algo más? Sí, siempre más con Holded
- Título: 16px semibold, ancho 352px
- Items: cards blancas con bullet list, `padding: 5px 10px`, ancho 433px

#### 4c. Los pasos del éxito
- Título: 16px semibold, ancho 352px
- Barra de progreso: 3 segmentos (`#111827` / `#374151` / `#9CA3AF`), alto 63px, `border-radius: 6.692px`, ancho 433px
- 3 filas (columna izquierda coloreada + columna derecha blanca):
  - Paso 1: fondo `#111827`
  - Paso 2: fondo `#4B5563`
  - Paso 3: fondo `#9CA3AF`

### 5. ¿Por qué somos tu mejor aliado?
- Texto intro: card gris, centrado, semibold, ancho 371px
- 3 items centrados: cards grises, ancho 282px, con número en cuadrado negro (`21×21px`, `border-radius: 2.625px`)

### 6. ¿Empezamos? (CTA)
`background: #F3F4F6`, `padding: 40px 0`, `gap: 30px`
- Título 40px
- Texto 10px, ancho 353px, con enlace a holded.com/es
- Subtítulo "Tu éxito es nuestro objetivo." — 14px semibold, ancho 289px
- Botón negro

### 7. Footer
Logo → línea separadora (margin 20px arriba) → texto copyright

---

## Secciones del documento INTERNO

### Diferencias respecto al EXTERNO

| Elemento | INTERNO | EXTERNO |
|---|---|---|
| Watermark | "Internal use" solapado sobre hero | No tiene |
| Sección retos | Pain points: problema en rojo + solución | Lista numerada |
| Sección central | Bloque gris con: Mensajes clave, Datos de impacto, Notas para Ventas | Bloque gris con: Por qué Holded, Algo más, Pasos del éxito |
| Testimonios | Sí, con iconos Font Awesome | No |
| Footer | "⚠️ Documento de uso exclusivamente interno" | "© Holded · Documento para uso externo" |
| CTA | No tiene | Sí |

### Pain points (solo INTERNO)
Cada card con:
- Problema: `font-weight: 600`, color `#FF5454`
- Solución: 10px regular, con `<b>` para destacar

---

## Proceso para crear un nuevo toolkit desde un Word

### Paso 1 — Extraer contenido del Word
Identifica y extrae estos bloques:
- **Nombre del sector** → reemplaza "Servicios Profesionales" en títulos
- **Pain points** (problema + solución) → sección INTERNO
- **Retos del cliente** (5 items) → sección EXTERNO
- **Mensajes clave para ventas** → sección INTERNO
- **Datos de impacto** (estadísticas) → sección INTERNO
- **Notas para el equipo de ventas** → sección INTERNO
- **Testimonios** (nombre, empresa, cita) → sección INTERNO
- **Texto CTA** → sección EXTERNO

### Paso 2 — Duplicar los archivos base
1. Copia la carpeta `holded-toolkits-servicios-profesionales/`
2. Renómbrala: `holded-toolkits-[nuevo-sector]/`
3. Renombra los HTML: `holded-[nuevo-sector]-INTERNO.html` y `holded-[nuevo-sector]-EXTERNO.html`
4. Actualiza los enlaces en `index.html`

### Paso 3 — Sustituir contenido
Busca y reemplaza en los HTML:
- "Servicios Profesionales" → nombre del nuevo sector
- "consultorías, arquitectura, legal e ingeniería" → sectores correspondientes
- Pain points, retos, mensajes clave, datos, testimonios → contenido del Word

### Paso 4 — Imagen hero
Sustituye la URL de la imagen en `.hero-image img`:
```html
<img src="[URL-nueva-imagen]" alt="[sector]" />
```

### Paso 5 — Subir a GitHub
1. Sube la carpeta nueva al repo `holded-toolkits` en GitHub
2. El link de GitHub Pages será automáticamente:
   `https://jengarlo.github.io/holded-toolkits/holded-toolkits-[sector]/`

---

## Notas importantes

- Las imágenes del logo de Holded usan URLs de Figma que **caducan a los 7 días**. Si los documentos dejan de mostrar el logo, hay que regenerarlas desde Figma o embeber el SVG directamente.
- Las fuentes Font Awesome deben estar siempre en la misma carpeta que los HTML para que los iconos funcionen offline/en PDF.
- Para generar PDFs desde los HTML, usar **Puppeteer** o la opción "Imprimir → Guardar como PDF" del navegador (Chrome da mejores resultados).
