# PDF Padder

A tiny single-file web app with a few PDF utilities. Everything runs locally in the browser via [pdf-lib](https://pdf-lib.js.org/) — your files never leave your machine.

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

## Usage

Open `index.html` in a browser. No server needed.

## Development

No build step. Just edit `index.html` and reload.
