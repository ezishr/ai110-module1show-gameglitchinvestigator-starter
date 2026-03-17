# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?

I can tell that the user interface is fairly straightforward and simple. The player shouldn't see the developer debug info window, though. The instructions are basic and clarified, however they still don't demonstrate how to play the game for a beginner. For instance, there is no instruction to enter the number in the box; this may be due to the user interface's simplicity, which prevents the player from being drawn to the answer box.

- List at least two concrete bugs you noticed at the start  
  (for example: "the secret number kept changing" or "the hints were backwards").

  - The game accepts invalid string input and still removes an attempt; it should warn without penalizing the player.
  - The hint messages are reversed (“higher” vs “lower”).
  - The attempt counter is inconsistent (UI shows 1 left, but game says no attempts); they should match.
  - Guess history updates late (after the next guess), likely causing attempt count errors.
  - The “New Game” button doesn’t reset properly; it only changes (and miscounts) attempts.
  - Difficulty modes are inconsistent: easy has fewer attempts than normal, ranges differ, and scoring is incorrect. It should start at 100 points and decrease (e.g., -5 per wrong guess).

---

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

- In your own words, explain why the secret number kept changing in the original app.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
