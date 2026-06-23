# BarcodeVault — Bulk Barcode Extractor

A fully client-side web app that extracts barcodes from uploaded images and lets you manage, search, filter, and export the results.

## Features

- **Bulk upload** — drop dozens of images at once
- **Multi-format detection** — QR Code, Code 128, EAN-13, EAN-8, UPC-A, UPC-E, Code 39, PDF417, Aztec, Data Matrix, ITF, Codabar
- **Rotation-aware** — scans each image at 0°, 90°, 180°, 270° to catch vertical/rotated barcodes
- **Dynamic table** — sort by any column, filter by format, full-text search
- **Export** — one-click Excel (.xlsx) or CSV download
- **Import** — re-import a previously exported CSV to continue working
- **Copy** — click any row's copy icon to put the barcode value on your clipboard
- **Zero backend** — everything runs in the browser; no data leaves your machine

## Deploy to GitHub Pages

1. Fork or clone this repo
2. Go to **Settings → Pages**
3. Set Source to **Deploy from a branch → main → / (root)**
4. Hit **Save** — your site will be live at `https://<username>.github.io/<repo>/`

## Tech Stack

| Library | Role |
|---|---|
| [@zxing/library](https://github.com/zxing-js/library) | Barcode detection (multi-format, TRY_HARDER mode) |
| [SheetJS (xlsx)](https://sheetjs.com) | Excel & CSV export |
| Vanilla JS + CSS | Everything else — no framework needed |

## Local Development

```bash
# Any static file server works, e.g.:
npx serve .
# or
python3 -m http.server 8080
```

Then open `http://localhost:8080`.

## Limitations

- ZXing's JS port can miss barcodes in very low-res or heavily blurred images
- Maximum reliable detection works best on images where the barcode covers at least ~10% of the frame
- PDF or TIFF files are not supported (convert to PNG/JPG first)

## License

MIT
