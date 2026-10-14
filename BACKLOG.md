# Backlog

Turning Switch log into a learning hub, one weekend session at a time. Each item ships on its own, is useful the day it lands, and leaves job tracking working. Tick items off as they ship.

Dates that set the order: NeetCode starts Mon 19 Oct, the first Friday redo is 23 Oct, ML fundamentals block 1 starts Mon 2 Nov, interview loops start 25 Jan, offer by 14 Mar.

- [x] **1. Learn tab: curriculum checklist and topic notes.**
  The curriculum lives in `data/curriculum.json`: coding patterns, ML fundamentals in six dated weekly blocks, statistics and probability, SQL, ML system design (the 8-step skeleton and 10 cases) and GenAI/LLM. Each topic is not started, learning or done, and has its own notes page. Sets up what later items build on: the schema version, and progress keyed by permanent topic ids.
  Needed by 2 Nov; pattern notes are useful from 19 Oct.

- [ ] **2. NeetCode 150 list with attempts and a Friday redo queue.**
  The 150 problems go into `data/curriculum.json` under their pattern. Log an attempt in a couple of clicks: solved, solved with hints, or missed. A miss goes into the Friday redo queue and stays there until you re-solve it cleanly. The 150 grid counts distinct problems solved; coding counts already in the prep log are carried over, not dropped.
  Needed for the second Friday, 30 Oct.

- [ ] **3. Flashcards with a due-today queue.**
  Write cards on any topic page. A review session shows the cards due today; "missed" sends a card back to the first box, "got it" moves it up one (roughly 1, 3, 7, 14 and 30 days). Leitner boxes rather than SM-2: two buttons, predictable intervals, nothing to tune.
  Needed by 2 Nov, so block 1 gets reviewed from the start.

- [ ] **4. Split index.html into index.html, styles.css and app.js.**
  A pure move with no behaviour change. By this point index.html will be around 1,400 lines; past about 1,000, one file is slow to find things in and its diffs are hard to review on GitHub. Move it earlier if the file gets there sooner.

- [ ] **5. Today view on the dashboard.**
  The dashboard opens with what's due: flashcards due, the Friday redo queue, this week's ML block, the next two NeetCode problems, and any gap in yellow. Job-search panels move below it, and the nav lists learning first and job search after.

- [ ] **6. Weekly targets count what you tick.**
  Topics done, problems solved, cards reviewed and cases practised come from the Learn and NeetCode data instead of prep-log counts, so nothing is logged twice. The prep log keeps hours. The weekly review shows the new numbers.

- [ ] **7. ML system design practice with the 8-step rubric.**
  On a case page, start a 45-minute attempt, write the answer under the eight skeleton headings, then score each step 0 to 2 against "what a strong answer covers" (public, in `data/curriculum.json`). Each case keeps its attempt history, and your weakest steps across all cases show as the gap to close.

- [ ] **8. Story bank for behavioral prep.**
  Eight STAR stories and six project stories, each project story with its hard follow-up question and your answer. Common behavioral questions live in `data/curriculum.json`; a coverage grid shows which questions have no story yet. The stories are personal, so they stay in localStorage.

- [ ] **9. Mock interview log.**
  Date, type, interviewer, score and what went wrong. Anything that went wrong can become a flashcard or a redo item in one click. Replaces the mock count in the prep log.

Not separate features: GenAI/LLM, statistics and SQL are Learn tracks plus flashcards, so they need no screens of their own.
