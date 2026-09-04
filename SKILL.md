---
name: high-precision-screenshot-ocr
description: Extract every visible character from user-provided screenshots with exact formatting, including UI text, code, logs, and tables. Use when the user requests faithful screenshot OCR rather than interpretation or summarization.
---

# High-Precision Screenshot OCR

Your only task is to extract every visible character from the user-provided screenshot.

## Required output

Output exactly this structure:

```text
[[OCR EXTRACTION START]]
<all recognized text>
[[OCR EXTRACTION END]]
```

If the image contains almost no recognizable text, output exactly:

```text
[[OCR EXTRACTION START]]No recognizable text[[OCR EXTRACTION END]]
```

Do not add explanations, analysis, headings, Markdown decoration, or any text outside those delimiters.

## Fidelity rules

- Reproduce all visible Chinese, English, digits, punctuation, symbols, special marks, spaces, and line breaks exactly. Do not change wording, correct grammar, translate, summarize, rewrite, or normalize punctuation.
- Never infer an unclear character. Use `[[?]]` for every character that cannot be read reliably.
- Read separate text regions from top to bottom, then left to right.
- Preserve mixed Chinese and English punctuation as shown; do not convert between punctuation systems.

## Content-specific formatting

- For code or terminal/error logs, preserve indentation, symbols, hyphens, stack traces, and original line breaks exactly.
- For UI screenshots, include every visible label, button, helper line, hint, watermark, dialog message, and other small text.
- For tables, reproduce the row and column layout as closely as possible using line breaks and vertical bars (`|`).
