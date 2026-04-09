# Holded Toolkits — One-pagers por sector

Este repositorio contiene los documentos de venta de Holded por sector: uno para compartir con clientes o partners (**EXTERNO**) y otro de uso interno para el equipo de Sales (**INTERNO**).

Están hechos en HTML y son documentos estáticos listos para imprimir o compartir como PDF.

---

## Sectores disponibles

| Sector | EXTERNO | INTERNO |
|--------|---------|---------|
| Servicios Profesionales | ✅ | ✅ |
| Retail | ✅ | ✅ |
| Distribución al por Mayor | ✅ | ✅ |
| E-commerce | ✅ | ✅ |
| Agencias | ✅ | ✅ |

---

## Cómo crear un toolkit para un nuevo sector

> Sigue estos pasos en orden. No necesitas saber programar.

---

### Antes de empezar — ¿Qué necesitas?

- [ ] El **documento Word o Google Doc** del nuevo sector (con los pain points, mensajes clave, testimonios, etc.). Si no lo tienes, pídeselo al equipo de Marketing o a quien gestione el proyecto.
- [ ] Una cuenta en **[Claude](https://claude.ai)** con acceso al proyecto **Holded Toolkits**. Si no tienes acceso al proyecto, pídelo a Jennifer García.
- [ ] Los **4 archivos de fuente** Font Awesome 7 Pro (`.otf`). Son archivos de licencia que no están en este repositorio. Pídeselos directamente a Jennifer García.
- [ ] Acceso de escritura a este repositorio de GitHub. Si no tienes acceso, pídelo a Jennifer García.

---

### Paso 1 — Abre Claude y el proyecto Holded Toolkits

1. Ve a [claude.ai](https://claude.ai) e inicia sesión con tu cuenta.
2. En el panel izquierdo, busca la sección **Proyectos** y haz clic en **Holded Toolkits**.
3. Dentro del proyecto, haz clic en **Nueva conversación** (o el botón `+`).

> El proyecto guarda el historial de todas las conversaciones anteriores como referencia, pero Claude no recuerda automáticamente lo que se habló antes. Por eso, el primer mensaje siempre debe incluir el contexto completo (Paso 2).

---

### Paso 2 — Dale contexto a Claude

Para que Claude sepa exactamente cómo construir el toolkit, necesita leer el archivo de instrucciones del proyecto (`PROMPT.md`).

1. Abre el archivo [`PROMPT.md`](./PROMPT.md) en GitHub (haz clic en el nombre del archivo).
2. Haz clic en el botón **Raw** (arriba a la derecha del contenido).
3. Selecciona todo el texto (`Ctrl+A` en Windows / `Cmd+A` en Mac) y cópialo.
4. Pégalo como **primer mensaje** en la conversación nueva de Claude.
5. Envíalo.

Claude te confirmará que ha recibido las instrucciones.

---

### Paso 3 — Facilita el documento del sector

En el siguiente mensaje, proporciona el contenido del sector. Tienes dos opciones:

**Opción A — Pegar el texto directamente**
Copia y pega el contenido completo del Word o Google Doc en el chat de Claude.

**Opción B — Compartir el enlace del Google Doc**
Si el documento está en Google Drive y es accesible con el enlace, escribe algo así en el chat:
> "Aquí tienes el documento del sector Hostelería: [pega el enlace]"

Después de leer el documento, Claude generará los dos archivos HTML. Puede tardar unos minutos.

---

### Paso 4 — Revisa y ajusta

Antes de guardar nada, revisa el resultado con el equipo:

- Pide a Claude que te muestre una **previsualización** o que describa las secciones generadas.
- Si algo no está bien (un texto, un dato, una sección que falta), díselo a Claude en el mismo chat y pedirá los cambios.
- Cuando estés conforme, pide a Claude que te entregue el **código HTML completo** de cada archivo.

---

### Paso 5 — Guarda los archivos en tu ordenador

1. Crea una carpeta nueva en tu ordenador con este nombre exacto (sustituye `[sector]` por el nombre real, todo en minúsculas y con guiones):
   ```
   holded-toolkits-[sector]
   ```
   Ejemplo: `holded-toolkits-hosteleria`

2. Dentro de esa carpeta, crea dos archivos de texto vacíos con extensión `.html`:
   - `holded-[sector]-EXTERNO.html`
   - `holded-[sector]-INTERNO.html`

   > **¿Cómo crear un archivo .html?** Abre el Bloc de notas (Windows) o TextEdit (Mac), pega el código que te ha dado Claude, y guarda el archivo con el nombre exacto indicado, asegurándote de cambiar la extensión a `.html` (no `.txt`).

3. Copia los **4 archivos `.otf`** de Font Awesome en esa misma carpeta (los que pediste en el paso *Antes de empezar*). Sin estos archivos, los iconos del documento no se verán correctamente.

4. Para comprobar que todo está bien, abre cualquiera de los `.html` con Google Chrome (doble clic). Deberías ver el documento con el diseño completo, fuentes e iconos incluidos.

---

### Paso 6 — Sube al repositorio de GitHub

Tienes dos formas de hacerlo:

#### Opción A — Sin conocimientos de Git (recomendado si es tu primera vez)

1. Ve a este repositorio en GitHub: [github.com/Jengarlo/holded-toolkits](https://github.com/Jengarlo/holded-toolkits)
2. Haz clic en **Add file** → **Upload files**.
3. Arrastra la carpeta `holded-toolkits-[sector]/` completa (con los dos HTML dentro) al área de carga.
   > ⚠️ No subas los archivos `.otf` — son de licencia y no deben estar en GitHub.
4. Abajo, en el campo **Commit changes**, escribe un mensaje descriptivo, por ejemplo:
   `Add hosteleria toolkit (EXTERNO + INTERNO)`
5. Haz clic en **Commit changes**.

#### Opción B — Con Git en tu ordenador

```bash
git clone https://github.com/Jengarlo/holded-toolkits.git
# Mueve la carpeta holded-toolkits-[sector]/ dentro del repositorio clonado
git add holded-toolkits-[sector]/
git commit -m "Add [sector] toolkit (EXTERNO + INTERNO)"
git push origin main
```

---

### Paso 7 — Actualiza este README

Una vez subido el toolkit, añade el nuevo sector a la tabla de **Sectores disponibles** al principio de este archivo:

1. En GitHub, haz clic en el lápiz ✏️ que aparece al abrir `README.md`.
2. Añade una fila nueva a la tabla con el nombre del sector y las dos ✅.
3. Guarda con **Commit changes**.

---

### Paso 8 — Comparte los links con el equipo

Los links directos a los documentos en GitHub son:

```
https://github.com/Jengarlo/holded-toolkits/blob/main/holded-toolkits-[sector]/holded-[sector]-EXTERNO.html

https://github.com/Jengarlo/holded-toolkits/blob/main/holded-toolkits-[sector]/holded-[sector]-INTERNO.html
```

> **Nota**: En GitHub, el HTML se muestra como código fuente. Para ver el documento renderizado, descarga el archivo y ábrelo con Google Chrome, o usa una extensión de GitHub como [GitHub HTML Preview](https://htmlpreview.github.io/).

---

### Paso 9 — Exporta los documentos a PDF

Los documentos se envían al equipo y a clientes en formato PDF. Están diseñados para exportarse como **una sola página continua** (sin cortes de página).

> ⚠️ **Importante**: Usa siempre **Google Chrome** para generar los PDFs. Otros navegadores (Safari, Firefox) pueden alterar el diseño o los iconos.

1. Asegúrate de tener la carpeta del sector en tu ordenador con los dos `.html` y los 4 archivos `.otf` dentro (si no, repasa el Paso 5).

2. Abre el archivo `holded-[sector]-EXTERNO.html` con Google Chrome (doble clic sobre el archivo).

3. Cuando el documento se cargue correctamente en el navegador, abre el menú de impresión:
   - En Mac: `Cmd + P`
   - En Windows: `Ctrl + P`

4. En la ventana de impresión, ajusta estas opciones:
   - **Destino**: Guardar como PDF
   - **Márgenes**: Ninguno (None)
   - Activa la opción **Gráficos de fondo** (Background graphics) — imprescindible para que se vean los colores y fondos
   - El **tamaño de papel** se configura automáticamente desde el propio HTML para generar una página única continua — no lo cambies

5. Haz clic en **Guardar** y nombra el archivo:
   ```
   Holded-Toolkit-[Sector]-EXTERNO.pdf
   ```

6. Repite los pasos 2 a 5 con el archivo `holded-[sector]-INTERNO.html` y guárdalo como:
   ```
   Holded-Toolkit-[Sector]-INTERNO.pdf
   ```

7. Ya tienes los dos PDFs listos para enviar al equipo — cada uno será una sola página larga, sin cortes.

---

## Requisitos locales (Font Awesome)

Los cuatro archivos `.otf` de Font Awesome 7 Pro no están incluidos en este repositorio por licencia. Deben copiarse manualmente en la carpeta de cada sector al trabajar en local:

- `Font_Awesome_7_Pro-Thin-100.otf`
- `Font_Awesome_7_Pro-Light-300.otf`
- `Font_Awesome_7_Pro-Regular-400.otf`
- `Font_Awesome_7_Pro-Solid-900.otf`

Si no tienes estos archivos, contacta con **Jennifer García**.

---

## Estructura del repositorio

```
holded-toolkits/
├── README.md                                        ← Esta guía
├── PROMPT.md                                        ← Instrucciones completas para Claude
├── holded-toolkits-servicios-profesionales/
│   ├── holded-servicios-profesionales-EXTERNO.html
│   └── holded-servicios-profesionales-INTERNO.html
├── holded-toolkits-retail/
│   ├── holded-retail-EXTERNO.html
│   └── holded-retail-INTERNO.html
└── holded-toolkits-distribucion/
    ├── holded-distribucion-EXTERNO.html
    └── holded-distribucion-INTERNO.html
```

---

## ¿Dudas o problemas?

Contacta con **Jennifer García**, que gestiona este proyecto.
