# Barcode to Excel

**Live app:** https://oeaas12-cyber.github.io/Barcode-To-Excel/

A phone web app for recording store items into Excel: **item name, barcode, production (factory) date, expiration date**, plus a warehouse log of **when each item came in and when it went out**.

## How to use
1. **Scan barcode** – point the camera at the barcode; it scans automatically. (Or tap 🖼 Photo to use a picture, or type the number / use a scanner gun.)
2. **Production / expiry dates** – tap **📷 Scan** next to *Production date* or *Expiration date* to read just that date, or **Capture both dates** when they are printed together.
3. Type the item name the first time (it is remembered for that barcode). **Date in** is filled with the current date and time; change it if needed.
4. Tap **Save item**.
5. When the item leaves: scan its barcode again and tap **Mark as out now**, or tap **📤 Check out** on the item in the log.
6. Tap **Export Excel** to download the log as an `.xlsx` file.

Filter the log by **All / In warehouse / Out**. Tip: on Android Chrome use **⋮ → Add to Home screen** to install it like an app.

## Excel file
| Column | Notes |
|---|---|
| Production date / Expiration date | Excel date cells |
| Days left | Formula: expiration date − today, so it stays current |
| Date in / Date out | Excel date-time cells (`yyyy-mm-dd hh:mm`) |
| Days in warehouse | Formula: date out − date in, or today − date in for items still in the warehouse, so it stays current when the file is opened later |
| Status | In warehouse / Out |
| Barcode | Stored as text, so leading zeros are kept |

## Languages
English and Arabic (العربية), switchable at the top of the page. Arabic uses a right-to-left layout, and the Excel export uses the same language (Arabic sheets open right-to-left).

## Reading text
- **On phone (default)** – production and expiry dates (and barcode numbers when the barcode itself can't be decoded) are read with Tesseract OCR. Free, no account, photos never leave the phone.
- **ChatGPT** or **Gemini** (optional) – also reads the item name and is better with small dotted print. Each user pastes their own API key and taps **Test connection**. The key is stored only on their phone and sent only to that provider; usage is billed to their own account.
  - Gemini key (free tier): https://aistudio.google.com/apikey → sign in with Google → Create API key
  - OpenAI key: https://platform.openai.com/api-keys (a ChatGPT Plus subscription does not include API use)

## Notes
- Barcodes in GS1 format (DataMatrix / GS1-128) can contain the dates themselves; those are filled in automatically.
- The log stays in the browser on that phone until exported.
- Hosted as a static site (GitHub Pages). No server, no database.

## Files
- `index.html` – the whole app
- `tess/eng.traineddata` – English text-recognition data for the on-phone reader
- `sw.js`, `manifest.webmanifest`, `icon*` – install-to-home-screen and offline support
