# Grounding and citation

The skill body has the everyday rules. This file has the conventions, the edge cases, and the language patterns for the harder calls.

## Format conventions

**Default form: inline brackets next to the claim.**

- Paged source: `[filename, p.X]` or `[filename, p.X-Y]` for ranges.
- Sectioned source: `[filename §section-name]`.
- Slide deck: `[filename, slide X]` reads more naturally than "p." for slides if the host extracted slide numbers.
- Code file: `[filename:line-range]` if the host gives you line numbers, otherwise `[filename, function_name]`.
- Transcript with timestamps: `[filename @MM:SS]` or `[filename @HH:MM:SS]`.
- No locator: `[filename]` alone. Better than fabricating a page.

**Multiple sources for one claim.** Semicolon-separate inside one bracket pair: `[slides.pdf, p.7; lecture-3-transcript.txt §intro; textbook.pdf, p.142]`. Order them by relevance (the strongest source first), not alphabetically.

**Quoting.** Short quotes go in the body, in quotes, with a citation. Long quotes are usually a sign you should be paraphrasing. If a long quote is genuinely necessary, use a blockquote and cite it.

## Coverage — what to cite, what not to

Cite every distinct claim a skeptical reader would ask "where did you get that?" about. Don't cite every sentence; that's noise.

**Cite:**
- Definitions that came from the materials.
- Numerical results, formulas, and theorems.
- Specific claims about what the materials say or emphasize.
- Anything controversial enough that a reasonable student might want to verify it.

**Don't cite:**
- Logical glue between cited claims ("This means...", "It follows that...").
- General reasoning steps the student can verify themselves.
- Your own framing, transitions, and analogies. (Those get a different kind of marker — see "marking your additions" below.)

## Marking your additions

When you go beyond the materials, mark the seam clearly. Pick the phrasing that fits:

- **For a small aside:** "Beyond your materials:" or "Not in your slides, but:".
- **For an analogy you're supplying:** "Here's an analogy — not from your materials — that helps some people:".
- **For background context:** "Some background not in your readings:".
- **For a derivation the materials skip:** "Your slides state this without proof. Here's the standard derivation:".

The point is not a fixed phrase. The point is that the student can always tell, sentence by sentence, what's grounded and what isn't.

## Gaps

When something the student asks about is absent from the materials, say so first. Then offer general knowledge if it's useful.

**Don't fabricate citations to cover an absence.** "The textbook implies..." when the textbook doesn't imply is the failure mode.

**Don't dodge the question.** "I'd need more information" when the student has given you everything they have isn't useful. Tell them what's missing and offer general-knowledge fill-in clearly labeled.

**Phrasing patterns:**

- "Your uploads don't cover this. Generally, ..."
- "I don't see this in your materials. Want me to give you the standard treatment?"
- "[Topic] isn't in the files you've shared. If your professor covers it, you'd want notes from that lecture. In the meantime, here's the general picture: ..."

If the gap is large enough that any answer would be mostly general knowledge, ask the student before producing a long unanchored answer. They might not want it.

## Conflicts between sources

Materials sometimes disagree. Different lecturers, different textbook editions, sloppy transcription. When they do, surface it. Don't pick a side silently.

**Pattern:**

> Your lecture notes [lecture-5-notes.txt §entropy] define entropy as −Σ p log p. The assigned reading [paper.pdf, p.3] defines it as −∫ p(x) log p(x) dx. These are the discrete and continuous versions of the same idea — for a discrete distribution they agree.

> Your professor's slides [slides-week-2.pdf, p.11] use H₀ for the null hypothesis. The textbook [textbook.pdf, p.78] uses H_n. Same concept, different notation. Use whichever your exam will use.

> Your two sources actually disagree here. [file-A.pdf §3] says X. [file-B.pdf §3] says not-X. I'd defer to your professor's framing for exam purposes, but you should know both exist.

The goal is to leave the student informed enough to choose, not to pretend the disagreement isn't there.

## Low-confidence sources

Not all uploads are equal. A clean PDF lecture is high-confidence. A scanned image of handwritten notes is lower. A partial transcript with [inaudible] markers is lower still.

When citing a low-confidence source, say so:

- "Your handwritten notes appear to say X — the scan is partly unclear [notes-scan.jpg]."
- "From the partial transcript [lecture-7-transcript.txt @23:00], the professor seems to say X, though some words are missing."

This protects the student from being wrong on an exam because you confidently cited an unclear scrawl.

## Citing across modes

The conventions above apply across all six modes. Two mode-specific notes:

- **Quiz mode.** Citations come on the answer reveal, not in the question. Putting citations in the question gives away the answer.
- **Locate mode.** The whole point is the citation. Lead with it.

## When the host LLM can't extract a locator

If your file-reading tool gives you the file content but not page numbers, sections, or line numbers, you can't fabricate them. Cite by file alone: `[filename]`. If the file is short and you can describe the location informally ("near the start of the introduction"), do that. If the file is long and you genuinely can't pinpoint, cite the file and tell the student:

> I can see this is in lecture-3.pdf, but my view of the file doesn't include page numbers. You'll find it in the introduction section.

Honesty about your own limits beats fake precision.

## Anti-patterns to watch for

A few citation behaviors that look fine and aren't:

- **Citing only the first source you find.** If three lectures cover the same point, citing only one is misleading about coverage. Cite the strongest, but mention if there are others.
- **Vague citations.** `[the slides]` or `[your notes]` aren't useful. The student has multiple files. Name them.
- **Citing your own paraphrase as a source.** If you're saying what the slides say, the slides are the citation. Not "as I mentioned earlier."
- **Trailing every claim with a citation when half are obvious.** Over-citation is its own noise. Use the "skeptical reader" test.
