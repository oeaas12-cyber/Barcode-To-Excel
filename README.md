# Barcode To Excel

A web app that scans barcodes and exports them to an Excel file.

**Live app:** https://oeaas12-cyber.github.io/Barcode-To-Excel/

## Features

- **Camera scanning** of EAN-13, EAN-8, UPC-A, UPC-E, Code 128, Code 39, ITF, QR, Data Matrix and more
- **Scan a photo** when the camera isn't available
- **USB / Bluetooth scanners** and typing: focus the input, scan, and the code is added on Enter
- Repeat scans add to the quantity (can be switched off), with a beep and vibration on each scan
- Edit quantity and add a note per row
- **Export to Excel (.xlsx)** with a Total row, or to CSV. Barcodes are stored as text so leading zeros are kept
- The list is saved in the browser, so it survives a reload

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole app: layout, styles and code |

Libraries are loaded from CDNs: [ZXing](https://github.com/zxing-js/library) 0.21.3 for decoding and [SheetJS](https://sheetjs.com) 0.18.5 for Excel export.

## Run locally

The camera needs HTTPS or `localhost`:

```bash
python3 -m http.server 8080
```

Then open http://localhost:8080.

## Publish on GitHub Pages

Settings → Pages → Build and deployment → Source: **Deploy from a branch**, Branch: **main**, folder **/ (root)** → Save.
The app is then live at https://oeaas12-cyber.github.io/Barcode-To-Excel/ within a minute or two.
