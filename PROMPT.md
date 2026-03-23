# Prompt maestro — Holded Sector Toolkits

Usa este documento como instrucción completa para generar, desde cero, los dos one-pagers HTML de cualquier sector de Holded. Solo necesitas tener el documento Word (o Google Doc) con el contenido del sector en cuestión.

---

## Contexto del proyecto

Holded produce dos documentos por sector:

| Documento | Audiencia | Propósito |
|-----------|-----------|-----------|
| **EXTERNO** | Partners / clientes | One-pager de venta: presentar Holded como solución al sector |
| **INTERNO** | Equipo de Sales | Guía rápida interna: pain points, mensajes clave, datos y frases de clientes |

Ambos son **HTML estáticos, print-ready, de 691px de ancho**, con diseño system Holded (Inter + Font Awesome 7 Pro).

---

## Stack técnico

- **Fuente de texto**: `Inter` (Google Fonts, pesos 400/600/700)
- **Iconos**: Font Awesome 7 Pro local (archivos `.otf` en la misma carpeta):
  - `Font_Awesome_7_Pro-Thin-100.otf`
  - `Font_Awesome_7_Pro-Light-300.otf`
  - `Font_Awesome_7_Pro-Regular-400.otf`
  - `Font_Awesome_7_Pro-Solid-900.otf`
- **Iconos renderizados** con la clase `.fa-icon` (font-weight: 900 = Solid)
- **Assets Holded** (logo diamond + wordmark) via Figma MCP:
  - Diamond: `https://www.figma.com/api/mcp/asset/643cdf15-3efa-414d-a6a1-14156f92585b`
  - Wordmark: `https://www.figma.com/api/mcp/asset/f461efb3-4547-44bf-9392-c34d5d346495`
- **Imagen hero**: URL de imagen libre o asset de Figma relevante para el sector

### Variables CSS comunes

```css
--gray-900: #111827;
--gray-500: #6B7280;
--gray-400: #9CA3AF;
--gray-100: #F3F4F6;
--white:    #FFFFFF;
--red:      #FF5454;   /* solo INTERNO */
--doc-width: 691px;
```

### Regla @page — PDF de página única continua

Incluir siempre este bloque CSS justo después del cierre `}` del bloque `:root`, en todos los documentos (EXTERNO e INTERNO):

```css
@page {
  size: 691px 5000px;
  margin: 0;
}
```

Y añadir siempre este script justo antes de `</body>`, en todos los documentos (EXTERNO e INTERNO):

```html
<script>
(function() {
  var doc = document.querySelector('.document');
  if (!doc) return;
  var height = Math.ceil(doc.getBoundingClientRect().height) + 106;
  var style = document.createElement('style');
  style.textContent = '@page { size: 691px ' + height + 'px; margin: 0; }';
  document.head.appendChild(style);
})();
</script>
```

El CSS define un fallback de 5000px. El script mide el contenido real al cargar la página y sobreescribe el @page con el height exacto (altura del documento + 96px de padding del body + 10px de margen de seguridad). Esto garantiza que el PDF sea siempre una página continua ajustada al contenido, sin espacio sobrante, sin necesidad de medir nada manualmente.

### Clase de iconos FA7

```css
.fa-icon {
  font-family: 'Font Awesome 7 Pro';
  font-weight: 900;   /* Solid */
  font-style: normal;
  font-size: 12px;
  color: #111827;
  line-height: 12px;
  display: block;
}
```

---

## Referencia de codepoints FA7 Pro confirmados

| Icono | Codepoint | Unicode HTML | Uso |
|-------|-----------|--------------|-----|
| Baby carriage (carrito bebé) | F77D | `&#xF77D;` | Tiendas bebés |
| Flask (matraz laboratorio) | F0C3 | `&#xF0C3;` | Cosmética / química |
| Backpack (mochila) | F5D4 | `&#xF5D4;` | Tiendas mochilas / outdoor |
| Building (edificio) | F1AD | `&#xF1AD;` | Empresas / servicios |
| Chart-line (gráfico) | F201 | `&#xF201;` | Finanzas / analítica |
| Store (tienda) | F54E | `&#xF54E;` | Retail genérico |
| Laptop (portátil) | F109 | `&#xF109;` | Tech / SaaS |
| Users (personas) | F0C0 | `&#xF0C0;` | Equipo / RRHH |
| Wrench (llave inglesa) | F0AD | `&#xF0AD;` | Industria / servicios técnicos |
| Briefcase (maletín) | F0B1 | `&#xF0B1;` | Servicios profesionales |
| Hospital | F0F8 | `&#xF0F8;` | Salud / clínicas |
| Utensils (cubiertos) | F2E7 | `&#xF2E7;` | Hostelería / restauración |
| Truck | F0D1 | `&#xF0D1;` | Logística / transporte |
| Graduation-cap | F19D | `&#xF19D;` | Educación |

> **Nota**: FA7 Pro usa codepoints distintos a FA6 en muchos casos. Si un icono no renderiza bien, usar el método de escaneo por grid descrito al final de este documento.

---

## Estructura del documento EXTERNO

```
LOGO
└── HERO
    ├── Título grande: "Sector [Nombre]"
    ├── Tagline (gray-400, 20px)
    ├── Descripción corta (10px)
    └── Imagen hero (330×318px, border-radius 8px)

SECCIÓN: ¿Te suenan estos retos?
└── Lista numerada (6 items) — .retos-list
    └── Cada item: número en badge negro + texto en gray-100

BLOQUE GRIS — .grey-block (padding 80px 0)
├── SECCIÓN: ¿Por qué Holded es tu solución?
│   ├── Intro text (433px de ancho)
│   └── Grid de soluciones (433px):
│       ├── Fila 1: 2 cards (flex:1 + flex:1)
│       ├── Fila 2: 2 cards
│       └── Fila 3: 1 card full-width
│           Cada card: badge título negro + texto gray-500
│
├── SECCIÓN: ¿Algo más? Sí, siempre más con Holded
│   └── Lista de 3 features (bullets)
│
└── SECCIÓN: Los pasos del éxito
    ├── Barra de progreso (3 segmentos: s1=27% negro, s2=46% gris oscuro, s3=27% gris claro)
    └── Lista de 3 pasos (paso-left + paso-right):
        ├── Paso 1 (s1, negro): Diagnóstico inicial
        ├── Paso 2 (s2, gris oscuro): Demostración adaptada + 3 checks
        └── Paso 3 (s3, gris claro): Propuesta personalizada

SECCIÓN: ¿Por qué somos tu mejor aliado?
├── Párrafo intro (aliado-intro, 371px)
└── 3 items numerados (aliado-item, 282px)

BLOQUE CTA — .cta-block (gray-100, padding 40px)
├── Título "¿Empezamos?"
├── Texto con link holded.com/es
└── Botón "Crear cuenta gratis →"

FOOTER
├── Logo
├── Línea separadora
└── "© Holded · Documento para uso externo"
```

---

## Estructura del documento INTERNO

```
HERO WRAPPER (posición relativa para watermark)
├── WATERMARK: texto "Internal use" (font-size 134px, color rgba(14,36,85,0.05))
├── LOGO (z-index 2)
└── HERO (z-index 2)
    ├── Título: "Toolkit [Sector]"
    ├── Subtítulo: "Claves rápidas para Ventas" (gray-400)
    ├── Descripción: para qué sirve la guía (2 líneas, 293px)
    └── Imagen hero (330×318px, igual que EXTERNO)

SECCIÓN: Problemas comunes y soluciones de Holded
└── Grid de pain points (513px):
    ├── Fila 1: 2 cards
    ├── Fila 2: 2 cards
    └── Fila 3: 1 card (ancho 251.5px, .full)
    Cada card:
    ├── .pain-problem (texto en ROJO #FF5454, font-weight 600)
    └── .pain-solution (texto en gray-900, con <b> para destacar soluciones)

⚠️ BLOQUE OPCIONAL: Funcionalidades clave
(Solo si el documento fuente lo incluye — verificar siempre)
└── SECCIÓN: "Funcionalidades clave para las empresas de [sector]:"
    ├── Título: section-title (40px, centered, max-width 503px)
    └── Lista .funcionalidades-list (513px, gap 10px)
        └── Cada item .funcionalidades-item:
            ├── .funcionalidades-icon — caja blanca 21×21px, border-radius 2.625px, emoji ✅
            └── .funcionalidades-text — <b>Título:</b> descripción (10px, gray-900)
    Ejemplo: Distribución ✅ tiene este bloque / Retail ❌ no lo tiene

BLOQUE GRIS — .grey-block
└── .grey-inner
    ├── Mensajes clave para Ventas
    │   └── 4 list-items blancos (433px)
    │
    ├── Datos de impacto
    │   └── 3 list-items blancos
    │
    └── Notas para el equipo de Ventas
        └── 3 list-items blancos (puede incluir links)

SECCIÓN: Frases inspiradoras de clientes satisfechos
└── 3 columnas (testimonials-row, 525px, gap 40px)
    Cada columna:
    ├── Icono FA7 en badge gris (.testimonial-icon)
    ├── "Equipo," (nombre — en la práctica siempre es "Equipo,")
    ├── Nombre empresa (font-weight 600)
    └── Frase entre comillas (gray-500)

FOOTER
├── Logo
├── Línea separadora
└── "⚠️ Documento de uso exclusivamente interno. No compartir con clientes."
```

---

## Cómo construir un nuevo toolkit desde un Word/Google Doc

> ⚠️ **REGLA CRÍTICA — Fidelidad al documento fuente**
>
> **Lee el documento fuente completo de principio a fin antes de escribir una sola línea de HTML.**
> Cada sección, cada ítem y cada dato del toolkit debe tener su origen exacto en el documento.
> **NUNCA asumas que una sección existe por analogía con otro sector.**
> Si una sección no aparece en el documento (ej. "Datos de impacto"), **no la incluyas**.
> Si una sección tiene N ítems en el documento, incluye exactamente N, ni más ni menos.
> En caso de duda, vuelve al documento y verifica.

### Paso 1 — Leer el documento fuente

Lee el documento Word o Google Doc del sector **completo** antes de empezar. Identifica y extrae únicamente lo que está presente en el documento:

**Para el EXTERNO:**
- Sector name (para el `<title>` y el hero)
- Tagline del sector (subtítulo gris bajo el H1)
- 6 retos/challenges del sector (lista numerada)
- Frase intro para la sección de soluciones
- 5 soluciones (nombres + descripción): 2+2+1 para el grid
- 3 features adicionales ("algo más con Holded")
- Texto de los 3 pasos del éxito (los pasos son siempre los mismos en estructura, solo cambia el sub-item del paso 2)
- 3 beneficios del aliado (pueden ser genéricos)
- Texto CTA personalizado

**Para el INTERNO:**
- N pain points del sector en primera persona (pueden ser 5, 7 u otro número — **usar TODOS los que haya en el documento, sin omitir ninguno**)
- Solución de Holded para cada pain point (con palabras clave en **negrita**)
- ⚠️ **Bloque opcional "Funcionalidades clave"**: comprobar si el documento lo incluye (lista con ✅ y descripción). Si existe, añadirlo entre los pain points y el bloque gris. Si no existe, omitirlo. Ejemplo: Distribución ✅ / Retail ❌
- 4 mensajes clave para el equipo de ventas _(solo si el documento los incluye)_
- ⚠️ **"Datos de impacto"**: solo incluir esta subsección si el documento la tiene explícitamente. Si no aparece, omitirla.
- 3 notas para ventas (decision maker, precio/argumento, link caso de éxito)
- 3 testimonials: nombre + empresa + frase + icono representativo

### Paso 2 — Seleccionar imagen hero

Usar una imagen libre relevante al sector, o un asset de Figma si está disponible. Dimensiones: mínimo 330×318px, `object-fit: cover`.

### Paso 3 — Seleccionar iconos para testimonials

Para cada empresa en los testimonials, elegir el icono FA7 Pro Solid más representativo de su sector usando la tabla de codepoints de arriba.

Si el icono necesario no está en la tabla, usar el método de escaneo:
```javascript
// En el preview del documento, ejecutar en la consola:
(function() {
  const div = document.createElement('div');
  div.style.cssText = 'position:fixed;top:0;left:0;width:100%;height:100%;background:white;overflow:auto;z-index:9999;padding:20px;';
  const range = {start: 0xF5C0, end: 0xF5F0}; // Ajustar el rango
  let html = '<div style="display:flex;flex-wrap:wrap;gap:10px;">';
  for (let i = range.start; i <= range.end; i++) {
    html += `<div style="text-align:center;width:50px;">
      <span style="font-family:'Font Awesome 7 Pro';font-weight:900;font-size:24px;">${String.fromCodePoint(i)}</span>
      <div style="font-size:9px;">${i.toString(16).toUpperCase()}</div>
    </div>`;
  }
  html += '</div>';
  div.innerHTML = html;
  document.body.appendChild(div);
})()
```

### Paso 4 — Copiar la plantilla base

Copiar el archivo HTML del sector más cercano (ej. `holded-retail-EXTERNO.html`) como base y reemplazar únicamente el contenido de las secciones. **No modificar el CSS ni la estructura HTML.**

Cambios por sección en el EXTERNO:
1. `<title>` → nombre del sector
2. `.hero-title` → nombre del sector únicamente. **NUNCA añadir "y Holded" ni variantes al título.**
3. `.hero-tagline` → tagline del sector
4. `.hero-desc` → descripción corta
5. `.hero-image src` → URL imagen del sector
6. `.retos-list` → 6 `.reto-item` con los retos
7. `.soluciones-intro` → frase intro
8. 5 `.solucion-card` → título + descripción de cada solución
9. `.features-list` → 3 features
10. Sub-item del paso 2 en `.pasos-list`
11. `.cta-text` → texto CTA con link y frase final en `<b>`
12. `.footer-text` → "© Holded · Documento para uso externo"

Cambios en el INTERNO:
1. `<title>` → nombre del sector
2. `.hero-title` → "Toolkit\n[Sector]". **NUNCA añadir "y Holded" ni variantes al título.**
3. `.hero-desc` → descripción de para qué sirve la guía
4. `.hero-image src` → misma URL imagen que el EXTERNO del mismo sector
5. 5 `.pain-card` → `.pain-problem` (rojo) + `.pain-solution` (con `<b>`)
6. 4 `.list-item` en mensajes clave
7. 3 `.list-item` en datos de impacto
8. 3 `.list-item` en notas de ventas
9. 3 `.testimonial-col` → icono (`&#xXXXX;`) + empresa + frase

---

## Archivos del repositorio

```
holded-toolkits/
├── README.md
├── PROMPT.md                          ← este archivo
├── holded-toolkits-servicios-profesionales/
│   ├── holded-servicios-profesionales-EXTERNO.html
│   ├── holded-servicios-profesionales-INTERNO.html
│   ├── index.html
│   └── Font_Awesome_7_Pro-*.otf (×4)
└── holded-toolkits-retail/
    ├── holded-retail-EXTERNO.html
    ├── holded-retail-INTERNO.html
    ├── index.html
    └── Font_Awesome_7_Pro-*.otf (×4)
```

> Los archivos `.otf` de Font Awesome 7 Pro **no se suben a GitHub** por licencia. Deben copiarse manualmente en cada carpeta de sector al trabajar en local.

---

## Naming convention

- Carpeta: `holded-toolkits-[sector]/`
- EXTERNO: `holded-[sector]-EXTERNO.html`
- INTERNO: `holded-[sector]-INTERNO.html`

Sectores en desarrollo o planificados:
- ✅ Servicios Profesionales
- ✅ Retail
- ⏳ Hostelería
- ⏳ Construcción
- ⏳ Salud
