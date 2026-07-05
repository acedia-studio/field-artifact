# Field Artifact

Browser tool that reads a photo's embedded EXIF (camera, timestamp, exposure, GPS
if present), enriches it with terrain elevation, the nearest named peak, and the
historical weather at that coordinate and moment, then imprints a "field artifact"
data card over the image. Everything runs client-side; nothing is uploaded.

- EXIF: exifr (vendored `exifr.umd.js`); a built-in HEIF/HEIC Exif-item extractor
  handles formats exifr can't parse (e.g. Fujifilm `.HIF`).
- HEIF/HEIC decode (incl. 10-bit HEVC): libheif-js (vendored `libheif-bundle.js`).
- Elevation + historical weather: open-meteo (public, no key).
- Nearest named peak: OpenStreetMap Overpass (public CORS mirror).
- Location (for GPS-less cameras like the X100VI): type a place name (Nominatim
  forward-geocode) or `lat, lon` to fill the location-derived fields.

Static site: `index.html` + the three vendored scripts. No build step.
