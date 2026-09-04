# Screenshot Exact OCR

A Codex Skill that extracts every visible character from screenshots with faithful formatting.

## Problem It Solves

Conventional OCR can miss secondary UI text, alter code or log indentation, normalize punctuation, or guess at blurred content. This project is for faithful screenshot transcription: it preserves visible characters, spaces, line breaks, and reading order while clearly marking unreadable characters.

## Key Features

- Extracts all visible characters, including Chinese and English text, digits, punctuation, symbols, and special marks.
- Preserves original spaces, line breaks, indentation, and punctuation; it does not translate, correct, or rewrite text.
- Retains formatting for code, terminal output, and error stack traces.
- Includes UI buttons, labels, hints, helper text, watermarks, and dialog messages.
- Reconstructs table rows and columns as closely as possible with line breaks and `|`.
- Marks each unreadable character as `[[?]]`; returns the specified no-text result when almost nothing is recognizable.

## Installation

1. Copy this project directory to your personal Codex skills directory:

   ```text
   ~/.codex/skills/high-precision-screenshot-ocr
   ```

2. Confirm that the directory contains `SKILL.md`.
3. Restart Codex or refresh its skill list so it discovers the skill.

## Usage

Upload a screenshot and request character-accurate OCR, or invoke the skill:

```text
$high-precision-screenshot-ocr
Extract every visible character from this screenshot.
```

The skill returns only the OCR result, without added explanation, image analysis, or summary.

## Input and Output Example

Input:

```text
Screenshot content:
Save changes?
Cancel   Save
```

Output:

```text
[[OCR EXTRACTION START]]
Save changes?
Cancel   Save
[[OCR EXTRACTION END]]
```
