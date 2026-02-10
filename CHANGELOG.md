# Changelog

All notable design and feature changes are versioned with [Semantic Versioning](https://semver.org/).  
Branches and tags follow `vMAJOR.MINOR.PATCH` (e.g. `v1.0.0`, `release/1.0.0`).

## [1.2.0] - 2025-02-09

### Changed
- Digit rules (0/1→I, 2–9 cycle with 9×11→0/1) are canonical: `applyDigitRule(el, d)` is the single entry point; typo cycle, cycleDigit 9×11 path, and slow degradation all call it so these rules supercede other behavior
- Slow degradation: ~28% of replacements insert a random digit 0–9 and run applyDigitRule

---

## [1.1.0] - 2025-02-09

### Added
- LICENSE (MIT) for the repo
- Fade out text box, upload, and original text (title/author) with labels after 420ms; click to restore
- Random digit sequence for 2–9: each step shows a random digit; when 9 has appeared 11 times, switch to 0 or 1 and apply roll-to-I rule

### Changed
- Inputs and textarea use same opacity transition as labels when `meta-faded` is active

---

## [1.0.0] - 2025-02-09

### Added
- Typo cycle: digits cycle through typographical symbols for 3–500+ iterations, then land on random digit and apply roll/cycle rule
- Slow degradation: poem in bad-OCR mode degrades one character at a time at 45–135s intervals (nearly imperceptible)
- Yes/No clickable toggle for bad vs accurate OCR (replaces checkbox)
- Labels and metatext fade after 420ms; click page to fade back in
- Random typographical substitution pool (letters/digits at low probability) for missing letters
- DRY refactor: `applyReplacements`, `degradeText`/`degradeLine`, `appendSpan`, `isUnstableChar`
- Digits 0 and 1 both roll to I
- Random timing for digit roll and cycle

### Changed
- All digits (0–9) go through typo cycle before applying digit rule

---

## [0.3.0] - 2025-02-09

### Changed
- Code review: extract `escapeRegex`, merge digit branches, rename `pageTexts`→`pageBlobs`, remove dead `isDigit`
- And→ampersand, punctuation-words→symbols (slow appearance), digit cycling for 2–9

---

## [0.2.0] - 2025-02-09

### Added
- Simulate bad OCR for typed poem text
- Neon VS Code–style UI (black bg, white text, thinner font)
- Flicker on fragmentation chars (• · ~ _) and ampersands; slow, varied, sinister
- File upload (image or PDF) with optional bad OCR
- Punctuation words→symbols; math words→symbols

### Changed
- Removed “bad OCR” copy from labels; white labels/status

---

## [0.1.0] - 2025-02-09

### Added
- Initial single-page poem viewer
- Default poem: murmur by Cameron Barnett (OCR text)
- Optional title/author and poem textarea; optional image/PDF upload
- Digits 0/1 roll to I; math words→symbols; fragmentation-style flicker

[1.2.0]: https://github.com/buzzcauldron/helpful-poem-ocr/releases/tag/v1.2.0
[1.1.0]: https://github.com/buzzcauldron/helpful-poem-ocr/releases/tag/v1.1.0
[1.0.0]: https://github.com/buzzcauldron/helpful-poem-ocr/releases/tag/v1.0.0
[0.3.0]: https://github.com/buzzcauldron/helpful-poem-ocr/releases/tag/v0.3.0
[0.2.0]: https://github.com/buzzcauldron/helpful-poem-ocr/releases/tag/v0.2.0
[0.1.0]: https://github.com/buzzcauldron/helpful-poem-ocr/releases/tag/v0.1.0
