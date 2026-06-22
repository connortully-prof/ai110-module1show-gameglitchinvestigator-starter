# AI Interactions Log

> **Stretch features only.** Only fill in the sections that apply to stretch features you attempted. If you did not attempt a stretch feature, leave its section blank or delete it. This file is not required for the core project.

---

## Core Project Summary

**AI Tool Used**: GitHub Copilot (built into VS Code)

**Core Bugs Fixed**:
1. Reversed hints in `check_guess()` — swapped "Go HIGHER" and "Go LOWER" logic
2. Broken New Game button — added full state reset and input clearing
3. Off-by-one guess counter — moved increment inside valid-guess branch and adjusted display to "Guess X of Y"
4. Double-click submit issue — wrapped input in a Streamlit form for single-click registration
5. Weak input validation — tightened `parse_guess()` to enforce range and numeric-only constraints
6. Hard mode range — updated from 1–50 to 1–500

**AI's Role**: Copilot helped identify logic inversions and provided suggestions on Streamlit session state management and form handling. Most fixes required manual debugging and verification by testing edge cases and user interactions.

**Challenges Encountered**:
- Initially applied layout changes that broke the page UI; reverted to keep original layout with only functional changes.
- Required multiple attempts to get session state reset working correctly without triggering Streamlit widget modification errors.
- Input validation needed refinement to handle negative numbers and out-of-range guesses consistently.

---

## Stretch Features

No stretch features were attempted. The focus was on completing and fixing all core game functionality.

---

## Agent Workflow (SF8)

Not attempted.

---

## Test Generation (SF7)

Not attempted. Tests remain unrefactored (logic functions are still in `app.py` rather than `logic_utils.py`).

---

## Linting & Style (SF9)

Not attempted.

---

## Model Comparison (SF11)

Not attempted.
