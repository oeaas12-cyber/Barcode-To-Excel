# Barcode to Excel

**Live app:** https://oeaas12-cyber.github.io/Barcode-To-Excel/

A phone web app that logs items **entering and leaving the warehouse** and exports the log to Excel: item name, barcode, date in, date out, days in warehouse, status, batch and quantity.

## How to use
1. **Scan barcode** – point the camera at the barcode; it scans automatically. (Or tap 🖼 Photo to use a picture, or type the number / use a scanner gun.)
2. Type the item name the first time (it is remembered for that barcode). **Date in** is filled with the current date and time; change it if needed.
3. Tap **Save item**.
4. When the item leaves: scan its barcode again and tap **Mark as out now**, or tap **📤 Check out** on the item in the log.
5. Tap **Export Excel** to download the log as an `.xlsx` file.

Filter the log by **All / In warehouse / Out**. Tip: on Android Chrome use **⋮ → Add to Home screen** to install it like an app.

## Excel file
| Column | Notes |
|---|---|
| Date in / Date out | Excel date-time cells (`yyyy-mm-dd hh:mm`) |
| Days in warehouse | Formula: date out − date in, or today − date in for items still in the warehouse, so it stays current when the file is opened later |
| Status | In warehouse / Out |
| Barcode | Stored as text, so leading zeros are kept |

## Languages
English and Arabic (العربية), switchable at the top of the page. Arabic uses a right-to-left layout, and the Excel export uses the same language (Arabic sheets open right-to-left).

## Reading photos
Only needed when the camera can't read a barcode directly.
- **On phone (default)** – reads the numbers under a barcode with Tesseract OCR. Free, no account, photos never leave the phone.
- **ChatGPT** or **Gemini** (optional) – also reads the item name. Each user pastes their own API key and taps **Test connection**. The key is stored only on their phone and sent only to that provider; usage is billed to their own account.
  - Gemini key (free tier): https://aistudio.google.com/apikey → sign in with Google → Create API key
  - OpenAI key: https://platform.openai.com/api-keys (a ChatGPT Plus subscription does not include API use)

## Notes
- The log stays in the browser on that phone until exported.
- Hosted as a static site (GitHub Pages). No server, no database.

## Files
- `index.html` – the whole app
- `tess/eng.traineddata` – English text-recognition data for the on-phone reader
- `sw.js`, `manifest.webmanifest`, `icon*` – install-to-home-screen and offline support
