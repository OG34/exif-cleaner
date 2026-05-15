# 🧹 EXIF Cleaner

**Remove hidden metadata from your images — privately, instantly, right in your browser.**

No upload. No server. No tracking. Everything happens locally on your device.

---

## What is EXIF data?

Every photo taken with a smartphone or camera contains invisible metadata embedded in the file — called **EXIF data**. This can include:

- 📍 **GPS coordinates** — the exact location where the photo was taken
- 🕐 **Timestamps** — date and time of capture
- 📷 **Device info** — camera make, model, lens, serial number
- ⚙️ **Camera settings** — ISO, aperture, shutter speed, focal length
- 💻 **Software info** — editing apps used, operating system

When you share a photo online, all of this data travels with it. EXIF Cleaner strips it out before the image leaves your hands.

---

## Features

- **Drag & drop** or file picker — supports JPG, PNG, HEIC, HEIF
- **Multiple files at once** — load and clean a whole batch
- **Full metadata preview** — see every EXIF field grouped by category before cleaning
- **Smart risk badges** — GPS flagged in red, other sensitive fields in amber
- **Lossless JPEG cleaning** — strips metadata at the binary level, pixel data is never recompressed
- **Before/after file size** — see exactly how much was removed
- **One-click batch download** — "Clean & Download All" processes everything at once
- **100% private** — images never leave your device; all processing runs in the browser

---

## Usage

1. Open `index.html` in any modern browser
2. Drop your images onto the drop zone (or click to select)
3. Review the metadata that was found
4. Click **Clean & Download** per file, or **Clean & Download All**
5. Done — the downloaded copies contain no metadata

---

## How cleaning works

| Format | Method |
|--------|--------|
| **JPEG / JPG** | Binary segment stripping — APP0–APP15 and COM markers are removed without touching the compressed image data (lossless) |
| **PNG** | Re-encoded via HTML Canvas — all metadata chunks are dropped |
| **HEIC / HEIF** | Decoded via Canvas and exported as clean JPEG (native HEIC support depends on the browser; works out of the box in Safari) |

---

## Privacy

- No data is ever sent to a server
- No analytics, no cookies, no external requests (except loading the `exifr` parsing library from jsDelivr CDN on first load)
- Works offline after the first load if the CDN script is cached

---

## Tech

- Vanilla HTML / CSS / JavaScript — single file, no build step
- [`exifr`](https://github.com/MikeKovarik/exifr) for EXIF parsing (loaded from CDN)
- Web Canvas API for image re-encoding
- Custom binary parser for lossless JPEG segment stripping

---

## License

MIT
