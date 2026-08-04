# AirTrunk OSE — Label Identifier

A single‑page, client‑side tool that reads a photo of a goods label and gives its **best‑effort guess at the OSE Banking article number**, based on the AirTrunk paperwork (OSE Banking workbook, SKU Alignment doc, and the loaded Ongoing article master for *Air Trunk Test*).

**Live:** https://tnixo21.github.io/airtrunk-label-id/

## How it works
1. Drop in one or more label photos (nothing is uploaded — OCR runs in your browser via Tesseract.js).
2. It extracts the text, then pattern‑matches against a built‑in knowledge base to pick the most likely **article number**, with a confidence %.
3. It also pulls out the **identifying number** (serial / catalog no.) — e.g. FWU serial `21F0146283…`, genset serial `C26H036981`, kiosk enclosure serial `AC255010028`, Canalis catalog `KSA1000ABG4`.
4. If OCR misreads (phone photos, rotated/creased labels), edit the text box and press **Identify** — the matcher runs on any text. There's also a "type text" mode for when OCR can't load.

## What it recognises
FWU (Fan Wall Unit), GEN (Cummins generator), KTX (Schneider kiosk transformer), HDC (BAC hybrid dry cooler), CDU, WCC chiller, WCC load bank, PTU, 3200A primary busway + parts (BFC/BRC), 1000A inrow busway + end‑feed boxes (KSA), 1000A TOB, and the 63A/32A inrow tap‑offs (KSB → `TOB63`/`TOB32`, flagged as **not yet in the Ongoing master**).

## Notes / limitations
- Best‑effort. Always confirm serialised items (FWU/GEN/KTX) against the serial on the plate.
- OCR quality varies with photo angle/lighting; the editable text box is the reliable fallback.
- Reference table (in the page) shows every article and the label clues used, so results are transparent.
