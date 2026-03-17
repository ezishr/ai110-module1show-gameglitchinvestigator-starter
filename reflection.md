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

Microsoft Copilot

- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).

Copilot suggested switching the hint logic (“HIGHER” ↔ “LOWER”). I reviewed the code, though it was a bit hard to compare since the changes were added after the original. After applying the fix, I ran and tested the game again to confirm it works correctly.

- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

One issue I haven’t fixed yet is the Developer Debug Info box. I explained to Copilot that the attempts and scoring weren’t synchronized, which was confusing. However, it misunderstood and created a duplicate debug box that updates after each guess. That’s not what I intended. I noticed the problem while reviewing the code, and after running the app, it confirmed that Copilot had misunderstood my request.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?

To verify the bug was fixed, I reviewed the logic, traced how the functions work and are imported, compared the conditions with my expectations, and tested the app multiple times by playing it.

- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.

I tested the point system (including hints and debug info for each difficulty level), and it confirmed that the logic issue is fixed.

- Did AI help you design or understand any tests? How?

The AI helped me quickly find where the bugs were and understand the issues. It also suggested fixes, so I just needed to review the code and apply the changes.

---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

In Streamlit, every time the user interacts with the app, the entire script executes again from the beginning, and the UI is refreshed in the browser. To keep information from being lost between these reruns, you can use session state, which allows data to persist across executions.

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
 
One strategy I plan to keep using in future labs and projects is reviewing the code logic before running the app. It helps me anticipate what the AI’s changes will do and reduces testing time, since I can focus more on edge cases instead of common scenarios.

- What is one thing you would do differently next time you work with AI on a coding task?

I will aim to describe the context and tasks as clearly and thoroughly as possible so the AI can better understand my ideas and provide more accurate and useful help.

- In one or two sentences, describe how this project changed the way you think about AI generated code.

This project shifted my view of AI from seeing it as a superpower that could replace humans to seeing it as a supportive tool that can work alongside me and enhance my skills in programming.
