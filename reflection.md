# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

  The core component of the game works as you can guess the secret number. However, there are numerous bugs as well as a phew things that dont make sense. The new game button siply doesnt work and the count for the amount of hints you have is off. Changing the difficulty also doesnt work if you have already lost a game

**Bug Reproduction Log** (I had the bug report complete and looking good but something happened and I spent way to much time on it to fix how it looks. all the answers are there)

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

The AI that I am using is whatever is built into VScode. A correct suggestion the AI made was to update the hint code in check_guess() so that Too high would return Go lower and vise versa. A misleading example of the AI making a suggestion was when I asked it to help fix how the guess button worked. It did help fix the button however it went out of its way to change the layout too.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

I decided that the bugs were fixed when I tested the game and the behavior was acceptable to me. I manually tested everything by playing the game and changing what I was currently working on. AI didnt help me understand the tests because I knew what I was looking for and was the one making sure the AI was doing everything right.
---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

I would explain that the game reruns the code for every interaction but that the current games session state keeps the values like the secret and amount of guesses. Every session state key is initialized and recorded before any changes are made and the game reruns. 
---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.

One strategy I deploy for my projects is focusing on one aspect I want to fix and then commit after fixing or changing whatever I was working on. Next time maybe I should clarify to the AI what I dont want changed so that it doesnt accidently change something unrelated like the layout again. I had previously known that AI could be used to help code but I think I was underestimating it. Now when I use AI i think im going to be more strategic with how I give it commands.