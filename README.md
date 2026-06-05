# PDF Padder

A tiny single-file web app that adds outer margins (padding) to each page of a PDF. The page size grows by the amount of padding and the original content is centered within the new page.

Everything runs locally in the browser via [pdf-lib](https://pdf-lib.js.org/) — your PDF never leaves your machine.

## Usage

Open `index.html` in a browser, then:

1. Choose a PDF file.
2. Pick a unit (pt, mm, or inch).
3. Enter the top / bottom / left / right padding.
4. Click **여백 추가하여 다운로드** to download the padded PDF.

## Development

No build step. Just edit `index.html` and reload.
