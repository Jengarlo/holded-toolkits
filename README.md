# holded-toolkits

One-pagers HTML (EXTERNO + INTERNO) para el equipo de Sales de Holded, por sector.

## Sectores disponibles

| Sector | EXTERNO | INTERNO |
|--------|---------|---------|
| Servicios Profesionales | ✅ | ✅ |
| Retail | ✅ | ✅ |
| Distribución al por Mayor | ✅ | ✅ |

---

## Cómo crear un toolkit para un nuevo sector

### Lo que necesitas antes de empezar

- El documento Word o Google Doc del nuevo sector (con pain points, mensajes clave, testimonios, etc.)
- Acceso a Claude (claude.ai) con el proyecto **Holded Toolkits** abierto
- Los archivos `.otf` de Font Awesome 7 Pro (ver sección *Requisitos locales* más abajo)
- Acceso de escritura a este repositorio de GitHub

---

### Paso 1 — Abre una conversación nueva en el proyecto de Claude

1. Ve a [claude.ai](https://claude.ai) y abre el proyecto **Holded Toolkits**.
2. Abre una conversación nueva dentro del proyecto.
3. Copia y pega el contenido completo del archivo [`PROMPT.md`](./PROMPT.md) como primer mensaje. Ese archivo contiene todas las instrucciones de diseño, estructura y reglas que Claude necesita para construir los documentos.

---

### Paso 2 — Proporciona el documento del sector

En el mismo mensaje (o en el siguiente), facilita a Claude el contenido del sector. Puedes:

- **Pegar el texto** directamente del Word o Google Doc, o
- **Compartir el enlace** al Google Doc (si Claude tiene acceso al navegador activo).

Claude leerá el documento completo antes de escribir ningún HTML.

---

### Paso 3 — Claude genera los dos archivos HTML

Claude producirá:

| Archivo | Para quién |
|---------|-----------|
| `holded-[sector]-EXTERNO.html` | Partners y clientes |
| `holded-[sector]-INTERNO.html` | Equipo de Sales |

Revisa el contenido con el equipo y pide a Claude los ajustes que necesites antes de continuar.

---

### Paso 4 — Prepara la carpeta local

1. Crea una carpeta nueva en tu ordenador con el nombre: `holded-toolkits-[sector]/`
2. Guarda los dos archivos HTML generados por Claude dentro de esa carpeta.
3. Copia los cuatro archivos `.otf` de Font Awesome (ver *Requisitos locales*) en esa misma carpeta — son necesarios para que los iconos se rendericen correctamente al abrir los HTML en el navegador o al imprimir a PDF.

---

### Paso 5 — Sube al repositorio de GitHub

1. Clona el repositorio (si no lo tienes ya):
   ```bash
   git clone https://github.com/Jengarlo/holded-toolkits.git
   ```
2. Mueve la carpeta `holded-toolkits-[sector]/` dentro del repositorio clonado.
3. Haz commit y push:
   ```bash
   git add holded-toolkits-[sector]/
   git commit -m "Add [sector] toolkit (EXTERNO + INTERNO)"
   git push origin main
   ```
4. Actualiza la tabla de **Sectores disponibles** en este README añadiendo la nueva fila.

---

### Paso 6 — Comparte los links con el equipo

Una vez en GitHub, los links directos a los documentos son:

```
https://github.com/Jengarlo/holded-toolkits/blob/main/holded-toolkits-[sector]/holded-[sector]-EXTERNO.html
https://github.com/Jengarlo/holded-toolkits/blob/main/holded-toolkits-[sector]/holded-[sector]-INTERNO.html
```

> **Nota**: Para visualizar los HTML renderizados (no el código fuente), usa la opción **Raw** del archivo en GitHub y ábrelo en el navegador, o trabaja con los archivos en local.

---

## Requisitos locales

Los archivos `.otf` de Font Awesome 7 Pro deben copiarse manualmente en la carpeta de cada sector (no se incluyen en el repo por licencia):

- `Font_Awesome_7_Pro-Thin-100.otf`
- `Font_Awesome_7_Pro-Light-300.otf`
- `Font_Awesome_7_Pro-Regular-400.otf`
- `Font_Awesome_7_Pro-Solid-900.otf`

Si no tienes estos archivos, contacta con el equipo de diseño o con quien administre el proyecto.

---

## Estructura del repositorio

```
holded-toolkits/
├── README.md                          ← Este archivo
├── PROMPT.md                          ← Instrucciones completas para Claude
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
