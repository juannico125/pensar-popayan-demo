# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A sales/pitch demo for "Pensar Popayán," a Saber 11 (Colombian standardized test) exam-prep product. It is a rebrand of an existing demo template ("Smart") with new branding, copy, and colors — see the initial commit message. The repo is two static, self-contained HTML files with no build system, no package manager, and no backend.

- `index.html` — the student-facing mobile app (viewport-constrained "phone" shell): login, home dashboard, quiz flow, results, wrong-answer review, and a teacher question-creation screen.
- `panel.html` — the institute admin/staff web panel (sidebar layout): results dashboard, question bank editor, quiz list, student roster, and simulacro (full mock-exam) tracking.

Each file is fully self-contained: inline `<style>` and inline `<script>`, no imports, no dependencies besides two Google Fonts loaded via `<link>` (Plus Jakarta Sans, IBM Plex Mono). There is no `package.json`, no test suite, and no linter.

## Running / previewing

There is nothing to build. Open the file directly in a browser, or serve the directory statically, e.g.:

```
python -m http.server 8000
```

Then visit `http://localhost:8000/index.html` or `/panel.html`. The two pages cross-link to each other (`index.html` → "Ver panel del instituto (web)" → `panel.html`, and `panel.html` sidebar → "← App del estudiante" → `index.html`).

## Architecture notes

**Single-page-per-file navigation.** Both files implement their own tiny SPA router by toggling a CSS `.active` class:
- `index.html` uses `go(screenName)` to switch between `<section id="screen-*">` elements (`login`, `home`, `quiz`, `results`, `review`, `teacher`).
- `panel.html` uses `show(viewName)` to switch between `<div class="main" id="view-*">` elements (`resultados`, `banco`, `cuestionarios`, `estudiantes`, `simulacros`), keeping the sidebar `nav-item` highlighted in sync.

**Everything is in-memory, nothing persists.** All app state lives in plain JS objects/vars (`state` in `index.html`; `correct`/`saved` in `panel.html`). "Save" actions (`teacherSave()`, `save()` in the bank editor) just increment a counter and show a toast (`t-toast` / `b-toast` / `demo-toast`) — they do not write anywhere. A page reload resets everything. Several buttons across `panel.html` (export report, add student, schedule simulacro, view enrolled list) are intentionally unwired and call `demoToast('... estará disponible en la versión completa')` to signal "not in this demo tier."

**Question bank is hardcoded.** `index.html`'s `BANK` array (top of the `<script>` block) defines the entire quiz: each question has `area`, `tipo` (`'Conceptual'` vs `'Tipo ICFES'`), optional `context` (reading passage), `text`, `opts`, `correct` index, `exp` (explanation shown on review), and `tip`. The quiz flow, scoring (`showResults`), and per-area breakdown all derive from this array — extend the demo content by editing `BANK` directly. `panel.html`'s question-bank form/preview is a separate, unconnected mockup (`DEFAULT_OPTS`) that does not read from or write to `BANK`.

**Design tokens are duplicated, not shared.** Both files define their own color palette and component styles independently inside their `<style>` blocks (no shared CSS file). Key palette: `#A67C00`/`#8F6B00` (amber/gold primary), `#26221B` (near-black, sidebar/header bg), `#EFE3BD`/`#FFFCF0`/`#FBF2D2` (cream backgrounds), `#C24B3A` (error/incorrect red), `#F2C200`/`#F5D45C` (yellow accents/logo). When restyling or rebranding (as this repo already was once), grep both files for these hex values rather than assuming a single source of truth.

**Spanish-language, ICFES/Saber 11 domain terms** appear throughout — `Lectura Crítica`, `Conceptual` vs `Tipo ICFES`, `simulacro` (full mock exam), `banco de preguntas` (question bank), `refuerzo sugerido` (suggested remediation). Keep new copy consistent with this terminology and in Spanish.
