# Satélites — Observatorio Uritorco

Snapshot público de los objetos orbitales que cruzan el encuadre de la cámara del
Observatorio Uritorco (Cerro Uritorco, Capilla del Monte, Argentina), para las
próximas 24 h.

El sitio es **estático**: `index.html` es siempre el mismo y los datos se cargan
por `fetch` desde los JSON, que son lo único que se actualiza:

- **`sat_candidatos_<AAAAMMDD>.json`** — un archivo por día con los objetos que entran
  al encuadre, iluminados por el Sol y con cielo oscuro en las próximas 24 h (NORAD,
  nombre, tipo, tamaño RCS, órbita y TLE). El visor busca automáticamente el archivo
  con la fecha más reciente; los anteriores quedan como archivo diario.
- **`catalogo_astro.json`** — catálogo de estrellas, constelaciones y espacio
  profundo que dibuja la capa de astros.

`sat_config.json` contiene la configuración de observador, cámara, colores y
parámetros del visor; se actualiza solo cuando cambia el diseño.

La página se refresca sola: propaga los TLE en el navegador cada segundo, de modo
que los JSON pueden actualizarse sin tocar el HTML.

Datos generados automáticamente desde el servidor del observatorio (snapshot; no
es en vivo). Página servida por **GitHub Pages**.
