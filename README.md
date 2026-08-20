# Antovero International, LLC — sitio de presentación

Sitio estático de una sola página, bilingüe (ES/EN), sin dependencias de build.
Todo el CSS y el JavaScript están en línea dentro de `index.html`.

## Publicar

Sube `index.html` a cualquier hosting estático. No requiere servidor, base de datos ni backend.

- **Netlify / Vercel / Cloudflare Pages:** arrastra la carpeta. Listo.
- **GitHub Pages:** sube el archivo al repo, activa Pages en la rama `main`.
- **Hosting cPanel tradicional:** sube `index.html` a `public_html/`.

Antes de publicar, cambia el dominio en dos lugares dentro de `index.html`:

- `<link rel="canonical" href="https://antoveroint.com/">`
- `"url": "https://antoveroint.com/"` dentro del bloque JSON-LD

## Idioma

- Español es el idioma por defecto.
- El botón ES/EN del encabezado cambia el idioma sin recargar la página.
- `?lang=en` abre el sitio directamente en inglés — útil para enviar el enlace a
  contactos federales o de habla inglesa.
- Los dos idiomas están en el HTML, así que la página se lee completa sin
  JavaScript y ambos idiomas son indexables por buscadores.

## Editar contenido

Cada texto traducible existe dos veces, uno junto al otro:

```html
<span class="es">Texto en español</span><span class="en">English text</span>
```

Al editar, cambia **ambos**. Los precios están escritos como texto plano
(`$350`, `$250`, …) y aparecen en dos lugares: la tarjeta del servicio y la
tabla de resumen (`#honorarios`). Actualiza los dos.

## Colores

Definidos como variables CSS al inicio de la hoja de estilo (`:root`):

| Variable | Valor | Uso |
|---|---|---|
| `--navy-800` | `#0d1f38` | fondo principal oscuro, encabezados |
| `--navy-900` | `#081729` | pie de página, degradados |
| `--gold-500` | `#967c4b` | **dorado exacto del logo** — acentos sobre fondo claro |
| `--gold-400` | `#b99a64` | el mismo dorado aclarado, para fondos oscuros |
| `--ink` / `--ink-2` | `#131a24` / `#3d4757` | texto |

Cambiar la marca completa = cambiar esos valores en un solo sitio.

## Logo

El logo está **dibujado en SVG dentro del HTML** — no es una imagen. Eso significa
que se ve nítido en cualquier pantalla y a cualquier tamaño, no pesa nada, y
cambia de color solo según el fondo (dorado sobre blanco en el encabezado,
dorado claro sobre azul en el pie).

En la carpeta `logo/` hay tres versiones sueltas por si las necesita para otros
usos — tarjetas, membretes, redes:

- `antovero-marca-dorado.svg` — dorado de marca `#967C4B`
- `antovero-marca-blanco.svg` — para fondos oscuros
- `antovero-marca-navy.svg` — para fondos claros de una sola tinta

El texto "ANTOVERO / INTERNATIONAL, LLC" del encabezado está compuesto en
**Montserrat Bold** con espaciado ancho, que es la tipografía que más se acerca
a la del logo original.

## Tipografía

Source Serif 4 (títulos), Inter (texto) y Montserrat (logo), cargadas desde
Google Fonts. Si el hosting no puede alcanzar Google Fonts, la página cae
automáticamente a fuentes de sistema sin romper el diseño.

## Incluido

- Encabezado fijo con menú móvil accesible (`aria-expanded`, cierre con `Esc`)
- Enlace "saltar al contenido", orden de encabezados correcto, foco visible
- Metadatos Open Graph, favicon SVG en línea, JSON-LD `ProfessionalService`
  con dirección, teléfono y correo — para Google y Google Maps
- Hoja de estilo de impresión: el cliente puede imprimir la página como
  documento de presentación limpio
- Respeta `prefers-reduced-motion`

## Pendiente de decidir con el cliente

- Dominio final y hosting
- Si quiere formulario de contacto o WhatsApp (hoy son enlaces directos:
  teléfono, correo y Google Maps)
- Aviso de privacidad / términos, si eventualmente añade analítica
