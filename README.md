# PDF Padder

A tiny single-file web app with a handful of PDF utilities. Everything runs locally in the browser via [pdf-lib](https://pdf-lib.js.org/), [pdf.js](https://mozilla.github.io/pdf.js/) and [JSZip](https://stuk.github.io/jszip/) — your files never leave your machine.

## Features

### 여백 추가 (Add padding)

Adds outer margins to each page of a PDF. The page size grows by the amount of padding and the original content is centered within the new page.

1. Choose a PDF file.
2. Pick a unit (pt, mm, or inch).
3. Enter the top / bottom / left / right padding.
4. Click **여백 추가하여 다운로드**.

### 2페이지 가로로 붙이기 (2-up)

Places two consecutive pages side by side on a single page. The new page's width is the sum of the two pages and its height is the larger of the two. Optionally leave the first page on its own.

### 이미지 → PDF (Images to PDF)

Combines several images into one PDF, **creating a page sized to fit each individual image** — so mixed-size images keep their own dimensions instead of being letterboxed onto a common page size.

1. Select one or more image files.
2. Set the DPI used to convert image pixels into page units (72 DPI means 1 px = 1 pt).
3. Optionally sort the files by name (natural ordering, so `img2` comes before `img10`); uncheck to keep the order you selected them in.
4. Click **PDF로 만들어 다운로드**.

PNG and JPEG are embedded directly. Other formats the browser can decode (WebP, GIF, BMP, …) are converted to PNG via a canvas first. Files that cannot be decoded are skipped and reported in the status line.

### PDF 합치기 (Merge PDFs)

Concatenates several PDFs into one, in order. Pages keep their original sizes and rotation (pdf-lib's `copyPages` is used, so page attributes carry over).

1. Select two or more PDF files.
2. Optionally sort by name, or uncheck to keep selection order.
3. Click **합쳐서 다운로드**.

Files that cannot be parsed are skipped and reported instead of failing the whole batch.

### PDF → 이미지 ZIP (PDF to image ZIP)

Renders each page of a PDF to an image and packages them into a ZIP.

1. Choose a PDF file.
2. Set the DPI (150 by default; higher is sharper but slower and larger).
3. Pick PNG (lossless) or JPEG (smaller; a quality field appears).
4. Click **이미지 ZIP으로 다운로드**.

Files are named `page-1.png`, `page-2.png`, … zero-padded to a consistent width. Pages are rendered on a white background so JPEG output (which has no transparency) looks right. ZIP entries are stored uncompressed, since the images are already compressed.

## Usage

Open `index.html` in a browser. No server needed.

## Development

No build step. Just edit `index.html` and reload.
