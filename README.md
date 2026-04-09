# Holded Toolkits — One-pagers por sector

Este repositorio contiene los documentos de venta de Holded por sector: uno para compartir con clientes o partners (**EXTERNO**) y otro de uso interno para el equipo de Sales (**INTERNO**).

Están hechos en HTML y son documentos estáticos listos para imprimir o compartir como PDF.

---

## Sectores disponibles

| Sector | EXTERNO | INTERNO |
|--------|---------|---------|
| Agencias | ✅ | ✅ |
| Servicios Profesionales | ✅ | ✅ |
| Retail | ✅ | ✅ |
| Distribución al por Mayor | ✅ | ✅ |
| E-commerce | ✅ | ✅ |

---

## Cómo crear un toolkit para un nuevo sector

---

### Requisitos previos

- [ ] **Contenido del sector**: documento con los pain points, mensajes clave, testimonios, etc. Puede ser un Word, Google Doc o diseño en Figma. Si no lo tienes, solicítalo al equipo de Marketing.
- [ ] **Acceso al proyecto Holded Toolkits** en [Claude](https://claude.ai). Contacta con Jennifer García si necesitas acceso.
- [ ] **4 archivos de fuente** Font Awesome 7 Pro (`.otf`). Son archivos con licencia que no están en este repositorio. Solicítalos a Jennifer García.
- [ ] **Acceso de escritura** a este repositorio de GitHub. Contacta con Jennifer García si no lo tienes.

---

### Paso 1 — Genera los archivos HTML con Claude

1. Abre el proyecto **Holded Toolkits** en [claude.ai](https://claude.ai) e inicia una nueva conversación.
2. Copia el contenido del archivo [`PROMPT.md`](./PROMPT.md) (usa el botón **Raw** en GitHub) y pégalo como primer mensaje. Esto proporciona a Claude las instrucciones de diseño y estructura.
3. En el siguiente mensaje, facilita el contenido del sector (pega el texto o comparte el enlace del documento).
4. Claude generará los dos archivos HTML: `EXTERNO` e `INTERNO`.

---

### Paso 2 — Revisa y ajusta

Revisa el resultado antes de guardarlo. Si hay algún error en el contenido o la estructura, indícaselo a Claude en la misma conversación. Cuando el resultado sea correcto, solicita el código HTML final de cada archivo.

---

### Paso 3 — Prepara los archivos en local

1. Crea una carpeta con el nombre `holded-toolkits-[sector]` (en minúsculas, con guiones).
2. Guarda los dos archivos HTML dentro con los nombres:
   - `holded-[sector]-EXTERNO.html`
   - `holded-[sector]-INTERNO.html`
3. Copia los 4 archivos `.otf` de Font Awesome en la misma carpeta.
4. Abre los `.html` en **Google Chrome** para verificar que el diseño, las fuentes y los iconos se muestran correctamente.

---

### Paso 4 — Sube al repositorio de GitHub

Desde la interfaz web de GitHub:

1. Ve al repositorio [Jengarlo/holded-toolkits](https://github.com/Jengarlo/holded-toolkits).
2. Haz clic en **Add file → Upload files** y sube la carpeta con los dos HTML (no incluyas los archivos `.otf`).
3. Escribe un mensaje descriptivo en el campo de commit, por ejemplo: `Add hosteleria toolkit (EXTERNO + INTERNO)`.
4. Actualiza también la tabla de **Sectores disponibles** en este `README.md` añadiendo el nuevo sector.

Si prefieres usar Git por línea de comandos:

```bash
git clone https://github.com/Jengarlo/holded-toolkits.git
git add holded-toolkits-[sector]/
git commit -m "Add [sector] toolkit (EXTERNO + INTERNO)"
git push origin main
```

---

### Paso 5 — Exporta a PDF

Los documentos están diseñados para exportarse como una sola página continua. Usa siempre **Google Chrome** para generar los PDFs (otros navegadores pueden alterar el diseño).

1. Abre el archivo `.html` en Chrome.
2. Imprime con `Cmd + P` (Mac) o `Ctrl + P` (Windows).
3. Configura: **Destino** → Guardar como PDF, **Márgenes** → Ninguno, y activa **Gráficos de fondo**. No modifiques el tamaño de papel (se configura automáticamente desde el HTML).
4. Guarda como `Holded-Toolkit-[Sector]-EXTERNO.pdf` y repite con el archivo `INTERNO`.

---

### Compartir con el equipo

Los links directos a los documentos en GitHub siguen este formato:

```
https://github.com/Jengarlo/holded-toolkits/blob/main/holded-toolkits-[sector]/holded-[sector]-EXTERNO.html
https://github.com/Jengarlo/holded-toolkits/blob/main/holded-toolkits-[sector]/holded-[sector]-INTERNO.html
```

Para ver el HTML renderizado, descarga el archivo y ábrelo en Chrome, o usa [GitHub HTML Preview](https://htmlpreview.github.io/).

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
