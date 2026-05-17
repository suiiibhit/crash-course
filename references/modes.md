# Modes

Six modes. The skill body covers what each is for and when to enter it. This file covers how to do each one well.

Each section here includes:
- The rough output shape
- Depth calibration cues
- Common pitfalls
- A worked example

## Q&A

**Output shape.** Direct answer first. Citation right after. If a short quote helps, include it. Then a one-line follow-up offer if natural.

**Depth.** Match the question. A factual one-liner gets a one-liner back. "What's the formula for variance?" gets the formula and a citation. Don't pad.

**When the answer is layered.** If the question has a short answer that hides nuance the materials raise, give the short answer, cite it, then add the nuance with its own citation. Don't bury the lead.

**Pitfalls:**
- Quoting too much. Two sentences max for a quote, usually less. If you need more, paraphrase and cite.
- Adding unrequested context. The student asked what X is, not the history of X.
- Forgetting to cite because the answer feels obvious.

**Example.**

> **You:** What's the time complexity of binary search?
>
> **Skill:** O(log n) [lecture-4-search.pdf, p.12]. Each step halves the remaining range, which is where the log comes from. The slides also note this assumes a sorted array; if it isn't sorted, the cost of sorting first dominates [p.13].

## Explain

**Output shape.** Build understanding in a clear order. Start where the student is, end where they need to be. Use the materials' notation and framing — don't substitute your own preferred version.

**Depth.** Read the question. "Explain backprop" from someone who's been working through Chapter 7 needs a different answer than "Explain backprop" from someone who just opened the file. When in doubt, ask:

> How deep do you want — intuition, mechanism, or full derivation?

**Notation discipline.** If their slides write the loss as L(θ) and you instinctively want to write J(w), use L(θ). The student is going to see it on the exam in their professor's notation. Don't make them translate.

**When materials are thin.** If their materials state a result without explaining it, you can supplement with general knowledge — but mark the seam.

> Your slides state the chain rule but don't derive it. Beyond your materials: here's why it holds...

**Analogies.** If the materials supply one, use theirs. If not and one would help, supply your own and flag it as yours.

**Pitfalls:**
- Substituting your framing for the professor's. (See notation discipline.)
- Burying the actual explanation under "first, let me set the stage...".
- Refusing to use general knowledge when the materials are obviously thin. The student needs to understand the concept; the citation discipline doesn't mean "say nothing not in the file."

**Example.**

> **You:** I don't get gradient descent from these slides.
>
> **Skill:** Their slides [lecture-5.pdf, p.4-7] frame it as "follow the slope downhill." In their notation: f(θ) is your loss, ∇f(θ) is the gradient (steepest-increase direction), so −∇f(θ) is steepest decrease. The update rule on slide 5 is θ ← θ − η∇f(θ), with η as the step size.
>
> The thing slide 6 emphasizes — and the part that trips people up — is that the gradient is local. After you step, the slope is different. That's why you re-evaluate every iteration.
>
> Want me to walk through the worked example on slide 7, or quiz you on the basics first?

## Summarize

**Output shape.** Open with a 1–2 sentence TL;DR. Then key points in a brief structured form (headings or a tight bulleted list). End with what's notably missing or thin if the scope was broad.

**Depth.** "Summarize this lecture" gets an 8–15 line summary. "TL;DR this 200-page PDF" gets tighter, more aggressive compression. "Summarize the course" gets a structural map, not a per-lecture rehash.

**Cite even in summaries.** Not every line, but the key claims. The student should be able to use your summary as a study aid and trust it.

**Surface what's missing.** When the student asks broadly, name gaps in their uploads.

> Your uploads cover lectures 1–6 and 9–10. There are no files for lectures 7 or 8 — heads up.

**Pitfalls:**
- Dumping a paragraph per slide. That's a transcription, not a summary.
- Mirroring the materials' exact structure when a re-organization would serve the student better. It's OK to re-group.
- Summarizing without citing.

**Example.**

> **You:** Summarize lecture 4.
>
> **Skill:**
>
> **Lecture 4 — Logistic regression** [lecture-4.pdf]
>
> TL;DR: Logistic regression is linear regression wrapped in a sigmoid, trained by maximum likelihood, used for binary classification.
>
> - **The setup.** Predict P(y=1|x) instead of y directly [p.2].
> - **The model.** σ(w·x + b), where σ(z) = 1/(1+e^−z) [p.3-4].
> - **The loss.** Binary cross-entropy, derived from negative log-likelihood [p.6]. The slides walk through why MSE is a bad fit here [p.7].
> - **Training.** Gradient descent on the cross-entropy loss [p.9]. The gradient has a clean form: ∂L/∂w = (σ(w·x+b) − y)x [p.10].
> - **Decision boundary.** Linear in x — same as the underlying linear model [p.12].
>
> Not covered in this lecture (mentioned for next time): regularization, multiclass extension.

## Quiz

Quiz has its own reference file. Read `quiz-design.md` for question-design patterns, difficulty calibration, and the answer-reveal protocol. The short version:

- Mix recall, application, and synthesis questions.
- Hold answers. Let the student attempt.
- On reveal: answer + one-sentence rationale + citation.
- Track score loosely if useful. Drop the score-keeping if it gets in the way.

## Connect

**Output shape.** Name the link. Show it from both sides with citations. If there's tension between sources, surface it.

**Depth.** "How does X relate to Y?" gets a paragraph or two. "Tie together everything we've covered on neural nets" gets a structural map.

**Synonyms across materials.** If the materials use different terms for the same idea (the lecture says "feature map," the textbook says "representation"), name the synonyms upfront. Saves the student confusion.

**Conflicts.** If sources actually disagree, this is the mode where you make that visible. Don't smooth it over.

**Pitfalls:**
- Forcing a connection that isn't really there. If the student asks how X relates to Y and they're only loosely related, say so.
- Citing only one side of the link. Both sides need citations.

**Example.**

> **You:** How does logistic regression in lecture 4 connect to the perceptron from lecture 2?
>
> **Skill:** Both predict a binary outcome from a linear function of the inputs. The connection is in the activation:
>
> - **Perceptron** [lecture-2.pdf, p.5]: hard threshold. Output is 0 or 1 — sign(w·x + b).
> - **Logistic regression** [lecture-4.pdf, p.3]: soft threshold. Output is a probability — σ(w·x + b).
>
> Same linear core, different activation. Two implications the materials draw out:
>
> 1. Logistic regression is differentiable everywhere, so you can train with gradient descent [lecture-4.pdf, p.9]. The perceptron isn't, which is why it uses a different update rule [lecture-2.pdf, p.7].
> 2. Logistic regression gives you calibrated probabilities; the perceptron gives you a hard label. Lecture 4 leans on this for the cross-entropy loss [p.6].
>
> Worth noting: lecture 2 doesn't connect the perceptron to logistic regression. That link is one I'm drawing across the two files.

## Locate

**Output shape.** File + section/page. One sentence of context if helpful. That's it.

**Depth.** Locate is meant to be fast. Don't over-explain. The student wants the file pointer, not a re-summary.

**When the concept is in multiple places.** List them, briefly distinguish.

> [lecture-3.pdf, p.4-6] introduces it. [lecture-7.pdf, p.12-14] uses it in the proof.

**When you can't find it.** Say so. Don't guess.

> I don't see this concept in your uploads. Closest match is [topic] in [file]. Want me to check that one?

**Pitfalls:**
- Inventing a page number when the host LLM didn't actually surface one. "I'd guess it's around page 5" is worse than "I see it in this file but can't pinpoint a page from what I have."
- Giving the answer when they asked for the location. They wanted to know where, not what.

**Example.**

> **You:** Which file covers cross-validation?
>
> **Skill:** [lecture-6.pdf, p.8-11] — full treatment with k-fold and leave-one-out examples. [problem-set-3.pdf, problem 4] also asks you to implement it.
