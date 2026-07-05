# Field Artifact

Browser tool that reads a photo's embedded EXIF (GPS, timestamp, exposure),
enriches it with terrain elevation, the nearest named peak, and the historical
weather at that coordinate and moment, then imprints a "field artifact" data card
over the image. Everything runs client-side; nothing is uploaded.

- EXIF: [exifr] (vendored, `exifr.umd.js`)
- Elevation + historical weather: open-meteo (public, no key)
- Nearest named peak: OpenStreetMap Overpass (public mirror)

Static site: `index.html` + `exifr.umd.js`. No build step.
