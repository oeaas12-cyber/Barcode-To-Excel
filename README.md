# Barcode to Excel

**Live app:** https://oeaas12-cyber.github.io/Barcode-To-Excel/

A phone web app for recording store items into Excel: **item name, barcode, production (factory) date and expiration date**.

## How to use
1. **Scan barcode** – point the camera at the barcode; it scans automatically. (Or tap 🖼 Photo to use a picture.)
2. **Dates** – tap **📷 Scan** next to *Production date* or *Expiration date* to read just that date, or **Capture both dates** when they are printed together.
3. Check the details, type the item name the first time (it is remembered for that barcode), tap **Save item**.
4. Tap **Export Excel** to download all items as an `.xlsx` file.

Tip: on Android Chrome use **⋮ → Add to Home screen** to install it like an app.

## Languages
English and Arabic (العربية), switchable at the top of the page. Arabic uses a right-to-left layout, and the Excel export uses the same language (Arabic sheets open right-to-left).

## Reading text
- **Offline (default)** – dates are read on the phone with Tesseract OCR. Free, no account, photos never leave the phone.
- **ChatGPT** or **Gemini** (optional) – also reads the item name and is better with small dotted print. Each user pastes their own API key, which is stored only on their phone and sent only to that provider; usage is billed to their own account.
  - Gemini key (free tier): https://aistudio.google.com/apikey → sign in with Google → Create API key
  - OpenAI key: https://platform.openai.com/api-keys (a ChatGPT Plus subscription does not include API use)

## Notes
- Saved items stay in the browser on that phone until exported.
- Barcodes in GS1 format (DataMatrix / GS1-128) can contain the dates themselves; those are filled in automatically.
- Hosted as a static site (GitHub Pages). No server, no database.

## Files
- `index.html` – the whole app
- `tess/eng.traineddata` – English text-recognition data for the offline reader
- `sw.js`, `manifest.webmanifest`, `icon*` – install-to-home-screen and offline support
