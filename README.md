# PDF Searcher

A single-file, browser-based search tool for working through stacks of PDF reference material. Built originally to power through military course PDFs (DA PAMs, ARs, ADPs), but works on any folder of text-based PDFs.

**Everything runs locally in your browser.** No uploads, no servers, no internet required after the page loads. Your PDFs never leave your computer.

---

## Quick start

1. **Download the tool.** Click `index.html` above → click the **Download raw file** button (down-arrow icon, top-right of the file view). Save it anywhere — Desktop, a course folder, wherever.
2. **Open `index.html`** by double-clicking it. It will open in your default browser. Chrome or Edge required.
3. **Load your PDFs.** Two options:
   - **Click "Pick folder…"** and choose the folder that holds your course PDFs.
   - **Or drag-and-drop** the folder (or a bunch of PDF files) anywhere onto the page. Use this on government/managed computers where the folder picker is blocked.

   Subfolders like `Phase 1 Ref / Lesson 2 / *.pdf` are preserved either way.
4. **Wait for indexing.** First time can take ~30 seconds depending on how many PDFs you have. With folder-picker mode, subsequent loads remember the folder.
5. **Search.** Type a few keywords. Click a result to preview the PDF inline with the matched terms highlighted.

> If you'd rather not download, you can also run it directly in your browser at the GitHub Pages URL listed in the repo's **About** section.

---

## Features

- **Multi-keyword search.** Type `army maintenance standard` and find every page that contains all three words. Use `"quoted phrases"` for exact strings, or check **Phrase** mode for whole-paragraph pasted-text search.
- **Folder-scoped search.** Narrow searches to specific folders or files via the tree on the left.
- **Live PDF preview** with highlighted matches, page-by-page navigation, and arrow-key support.
- **Bookmarks** with custom titles, freeform notes, tags (auto-populated from your search), and pinned regions (drag a box on a page to mark exactly what matters).
- **📌 Pin** a specific region on a page — when you reopen the bookmark, only highlights inside that region show.
- **Recent / History tabs** so you can jump back to anything you opened or searched recently.
- **📋 Cite** button copies a citation like `DA PAM 750-1, p. 4` to your clipboard.
- **Resizable columns** — drag the dividers, double-click to reset.
- **Persistent folder.** Pick once, the browser remembers next time you open the tool.

All bookmarks, history, and settings are stored in your browser's local storage — nothing is sent anywhere.

---

## Requirements

- **Chrome** or **Edge** (the File System Access API isn't supported in Firefox or Safari yet).
- A folder of **text-based PDFs** (scanned/image-only PDFs won't be searchable without an OCR step).
- Internet on first load only, to fetch PDF.js from a CDN. After that the browser caches it and the tool works offline.

---

## For classmates

If you're getting this from someone in the course, you have two options:

### Easiest: just visit the live URL

Open the GitHub Pages URL in Chrome or Edge. Drag a folder of PDFs onto the page (or click **Pick folder…**) and you're set. Nothing is uploaded — files are read directly from your computer.

### Download for offline use

1. Download `index.html` from this repo (click the file, then the download icon).
2. Save it anywhere. Optionally place it next to your PDFs:
   ```
   PDF-Searcher/
     index.html
     Phase 1 Ref/
       ADP 1.pdf
       AR 600-20.pdf
     Phase 2 Ref/
       ...
   ```
3. Double-click `index.html` to open it in your browser.
4. Drag your PDF folder onto the page, **or** click **Pick folder…**.

### On government / managed computers

The "Pick folder…" button often does nothing on locked-down computers — the OS folder picker is blocked by policy. **Drag-and-drop works around this:** just drag the folder (or individual PDF files) from File Explorer onto the page. Same result.

The tool itself contains no course material — you supply your own PDFs from wherever you normally access them (SharePoint, OneDrive, local downloads, etc.).

---

## Privacy

This tool was built specifically so course PDFs **never leave your machine**:

- Files are read directly from your local disk via the browser's File System Access API.
- No backend, no telemetry, no analytics, no cloud sync.
- Bookmarks and history live in your browser's `localStorage`, which is per-browser and per-machine.
- The only network request is the initial load of [PDF.js](https://mozilla.github.io/pdf.js/) from cdnjs.

If you'd prefer fully offline operation, save a copy of `pdf.min.js` and `pdf.worker.min.js` from [cdnjs](https://cdnjs.com/libraries/pdf.js/3.11.174) and update the `<script>` tags in `index.html` to point at local copies.

---

## License

MIT — do whatever you want with it.
