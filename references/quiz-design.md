# Quiz design

Quiz mode is the highest-leverage mode for actual learning, and the most fragile. Done well, it forces active recall — the move that converts "I've read this" into "I know this." Done badly, it's a worksheet with the answers visible.

This file has the patterns for doing it well.

## Default protocol

1. Ask one question at a time, unless the student explicitly asks for a batch.
2. Wait for the student's attempt before showing the answer. Always.
3. On reveal: answer + one-sentence rationale + citation.
4. After reveal, offer to move on or to drill the same area harder.
5. Track score loosely if it helps. Drop the score-keeping if the student is just trying to learn and the score is creating pressure.

## Question type mix

Three types. A good quiz uses all three. Pure-recall quizzes are weak — they test memorization, not understanding.

### Recall

Tests: do you know the fact?

> What is the time complexity of insertion in a balanced BST?

Use these for definitions, formulas, named results, and the basic facts the student has to have memorized. Keep them short.

### Application

Tests: can you use the concept in a problem?

> Given a sorted array of 1024 elements, how many comparisons does binary search need in the worst case?

Use these to verify the student can actually do something with the concept, not just recite it. These are usually closer to exam-style than pure recall.

### Synthesis

Tests: can you connect concepts or reason about edges?

> When would you choose a hash table over a balanced BST, and when the reverse?

> The lecture defined entropy for discrete distributions. What goes wrong if you try to apply the same definition to a continuous distribution?

Use these to test understanding, not just retention. They're the hardest to write well — too vague and they're a free-form essay, too narrow and they collapse to recall.

A reasonable mix for a chapter quiz: roughly 40% recall, 40% application, 20% synthesis. Adjust by what the student asks for. "Quiz me on definitions" goes mostly recall. "Help me prep for the exam" leans heavier on application and synthesis.

## Difficulty calibration

The student's first 1–2 attempts tell you a lot.

- **They got it right easily** — step up. Move from recall to application, or from application to synthesis.
- **They got it right with effort** — keep the level, vary the angle.
- **They got it wrong but the reasoning was close** — next question on the same area, slightly different framing.
- **They got it wrong with confused reasoning** — step down, give a more basic question on the same area, or offer to switch to Explain mode briefly before resuming.

You're not trying to humiliate them. You're trying to find the productive difficulty.

## Answer reveal

The reveal is where citations matter most. The student is going to remember the answer + the rationale together. Make both correct.

**Format:**

- The answer (1–3 lines, depending on the question).
- A one-sentence rationale that names the *reason* the answer is correct, not just the fact that it is.
- A citation to where the relevant material is.

**Example reveal (correct attempt):**

> Answer: O(log n).
>
> Each comparison halves the remaining search space, so the number of comparisons grows with log₂(n) [lecture-4-search.pdf, p.12].

**Example reveal (incorrect attempt):**

> The correct answer is O(log n).
>
> You wrote O(n) — that would be the cost if you scanned the whole array. Binary search halves at each step, so it's logarithmic. The slides have the recurrence on [lecture-4.pdf, p.13].

Don't pile on. One sentence of correction is usually enough. If the student keeps getting the same idea wrong, switch briefly to Explain mode rather than drilling them through more wrong attempts.

## Special cases

**Multiple-choice format.** If the student asks for MC, generate plausible distractors — wrong answers that reflect actual misconceptions, not obvious nonsense. The whole point of MC is testing whether the student can rule out the close-but-wrong options.

**"Quiz me until I get it right" mode.** Some students prefer relentless drilling on a topic until they're solid. If they ask for that, stay on the same topic, vary the framing, and only move on when they've nailed it 2–3 times in different forms.

**"Mock exam" mode.** Some students want to simulate an exam: a batch of questions, all at once, no feedback until they're done. Honor that. Hold all answers. Reveal at the end with explanations and citations for everything.

**Flashcard / rapid-recall mode.** If the student asks to be "drilled" or "flashcard-style quizzed," shift to short, definition-heavy questions with quick reveals. Same hold-then-reveal protocol, just shorter and faster-paced.

**Time-bound questions.** If the student asks for "exam-realistic" questions and the source mentions exam structure (time limits, point values, format), match it. Don't invent exam parameters that aren't in their materials.

## Pitfalls

- **Giving away the answer in the question.** "What's O(log n) used for?" telegraphs the answer.
- **Asking trivia that isn't actually in the materials.** Stay grounded. The materials are the syllabus.
- **Asking questions that have no clear answer.** "What do you think about gradient descent?" is bad quizzing. "Under what condition does gradient descent converge to a global minimum?" is good quizzing.
- **Skipping the rationale on the reveal.** The rationale is where the learning is.
- **Lecturing on a wrong answer.** Correct, point, move on. Don't write a paragraph.
- **Asking three questions when the student wanted one.** Quiz pace matters. Hold to one at a time unless they say otherwise.

## Closing the session

When the student is done quizzing, a brief recap helps:

> You got 7 of 10. The areas that came up shakiest: gradient descent convergence conditions, and the cross-entropy derivation. Worth a re-read of [lecture-5.pdf, p.6-9] before the next round.

Skip the recap if it would feel pro forma. Use judgment.
