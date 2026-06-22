# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

- [x] **Describe the game's purpose**: A number guessing game where players select a difficulty, guess a secret number within a range, receive hints, and earn points based on how quickly they win.

- [x] **Detail which bugs you found**:
  - **Reversed hints**: When guess was too high, hint said "Go HIGHER"; when guess was too low, hint said "Go LOWER" — both backwards.
  - **New Game button broken**: Clicking "New Game" didn't reset state or generate a new secret, leaving the game in an unplayable state.
  - **Guess count off by 1**: Counter started at 0 and invalid guesses incremented the counter, causing the loss condition to trigger one guess too early.
  - **Double-click submit bug**: The Submit button required two clicks to register a valid guess.
  - **Weak input validation**: Non-numeric inputs and out-of-range guesses were accepted without clear error messages.
  - **Hard mode range wrong**: Hard difficulty was 1–50 instead of 1–500.

- [x] **Explain what fixes you applied**:
  - Fixed `check_guess()` to return "Go LOWER" for too-high guesses and "Go HIGHER" for too-low guesses.
  - Fixed New Game button to reset `attempts`, `secret`, `status`, `history`, `score`, and clear the input field.
  - Moved guess increment inside the valid-guess branch so only legitimate guesses count; adjusted counter display to show "Guess X of Y" starting at 1.
  - Added Streamlit form to ensure single-click submission and immediate guess registration.
  - Tightened `parse_guess()` to reject non-numeric values and enforce difficulty range limits with specific error messages.
  - Updated `get_range_for_difficulty()` to return Hard = 1–500 and made the info banner show the dynamic range.

## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

1. **Select a difficulty** from the sidebar (Easy: 1–20, Normal: 1–100, Hard: 1–500).
2. **Enter a number** within the difficulty range and click "Submit Guess 🚀". Invalid inputs (non-numeric or out of range) show an error message.
3. **Read the hint** which now correctly says "Go LOWER" when your guess is too high and "Go HIGHER" when your guess is too low.
4. **Track your progress** via the "Guess X of Y" counter which starts at 1 and increments only for valid guesses.
5. **Win or lose** — if you guess the secret number, balloons appear and your final score is displayed. If you run out of attempts, the game reveals the secret and ends.
6. **Click "New Game 🔁"** to reset the game state, generate a new secret number, and start fresh without reloading the page.

**Screenshot** *(optional)*: <!-- Insert a screenshot of your fixed, winning game here -->

## 🧪 Test Results

```
(The following tests are currently failing because the game logic functions 
need to be refactored from app.py into logic_utils.py as part of Challenge 4.)

============================= test session starts ==============================
platform win32 -- Python 3.13.14, pytest-9.0.3, pluggy-1.6.0
collected 3 items                                                              

tests/test_game_logic.py::test_winning_guess FAILED                      [ 33%]
tests/test_game_logic.py::test_guess_too_high FAILED                     [ 66%]
tests/test_game_logic.py::test_guess_too_low FAILED                      [100%]

========================= 3 failed in 1.18s =========================

To pass all tests, refactor check_guess(), parse_guess(), get_range_for_difficulty(),
and update_score() from app.py into logic_utils.py.
```


## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, describe the Enhanced UI changes here — a screenshot is optional]
