# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it? 
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

  The core component of the game works as you can guess the secret number. However, there are numerous bugs as well as a phew things that dont make sense. The new game button siply doesnt work and the count for the amount of hints you have is off. Changing the difficulty also doesnt work if you have already lost a game.

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

----------------------------------------------------------------------------------------------------------------------------------------------------------
 Input                 | Clicking Submit Guess                  | Clicking New Game                      | 6
-----------------------|----------------------------------------|----------------------------------------|-----------------------------------------------|
Expected Behavior      | Giving the right amount of attempt     | Clicking new game should create a      | When the guess is higher the hint should be   |
                       |                                        | new game and clear the previous guesses| lower and vise versa                          |
-----------------------|----------------------------------------|----------------------------------------|-----------------------------------------------|
Actual Behavior        | Told me the answer and said I ran out  | Clicking new game does nothing         | When the guess is too high, the hint is too   |
                       | of attempts when I still had 1 left    |                                        | low which is the opposite of what is          |
-----------------------|----------------------------------------|----------------------------------------|-----------------------------------------------|
Console Output / Error | Out of attempts! The secret was 92.    |                                        | Go LOWER!
                       | Score: -35                             |                                        |
-----------------------|----------------------------------------|----------------------------------------|-----------------------------------------------|

------

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
