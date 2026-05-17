# Ambiguity and edge cases

This file is for when the materials don't behave: they conflict, they're unclear, they're partly missing, or the student's request is ambiguous in a way that affects the substance of the answer.

The skill body's rule is: surface ambiguity, don't paper over it. This file gives you the patterns.

## Sources conflict

The three most common cases:

### 1. Same concept, different notation

Lecturer uses θ for the parameter; textbook uses w. Slides write the loss as L(θ); homework writes it as J(w).

This isn't a real conflict. Name the synonyms once, pick one, move on. Use the professor's notation by default if you can tell which is which.

> Your professor uses θ; the textbook uses w. Same thing. I'll use θ since that's what your slides use.

### 2. Same concept, actually different definitions

This is a real conflict. Surface it.

> Your lecture notes [§4] define a stationary process as one where the joint distribution of any subset is shift-invariant. The textbook [p.78] uses a weaker definition — only the mean and covariance need to be shift-invariant. The lecture's version is "strict stationarity" and the textbook's is "weak (or wide-sense) stationarity." Both are standard, but they're different conditions.

Don't pick a side. Tell the student which is which and let them choose based on what their professor wants.

### 3. One source is just wrong

Rare but it happens. Slides have typos. Transcripts garble names. If you're confident — meaning the rest of the source contradicts the apparent error, or it's a clear typo — say so:

> Slide 12 has the formula as σ(z) = 1/(1+e^z), but slides 13–14 use σ(z) = 1/(1+e^−z), which is the standard sigmoid. Slide 12 looks like a typo.

If you're not confident, surface both possibilities and let the student check.

## Notation is unclear

When a symbol or term in the materials is genuinely unclear — bad scan, partial OCR, undefined notation — don't guess.

> The notation in this section [scan.jpg] looks like it could be either ∂ or ∇ — the scan isn't clean enough for me to tell. If the surrounding context is partial derivatives of a scalar, it's ∂; if it's the gradient of a multivariate function, it's ∇.

When a term is used without being defined in the materials you have, flag it:

> Your slides use "kernel trick" without defining it — it must have been introduced in an earlier lecture you haven't uploaded. Beyond your materials: a kernel function is...

## Material is missing or partial

If the student asks about something and you can see they have related uploads but not the specific source, name the situation:

> You've uploaded lectures 1–4 and 6. Lecture 5 isn't in the conversation, but the material on [topic] is referenced from there in lecture 6. I can give you the general treatment, or you can upload lecture 5 if you have it.

For partial transcripts (the [inaudible]s):

> The transcript has the professor saying X around 18:30, but the next 30 seconds are marked [inaudible]. From context, they were probably moving into the proof, but I can't be sure.

For poor scans:

> This page is partly unreadable. I can make out [excerpt], but the equation in the middle is illegible. If you have a clearer version, that would help.

## Student intent is ambiguous

Two patterns. Pick the one that fits.

### 1. The mode is unclear

> "Tell me about gradient descent" could mean: explain it, summarize what your slides cover, quiz you on it, or find where it's discussed. Which would help most?

Ask one question. Move on as soon as they answer.

### 2. The mode is clear but the scope isn't

> "Summarize this" could mean the lecture you just uploaded, the whole course, or just the section we were discussing. Which?

Same pattern: ask, move on.

When not to ask: when the right interpretation is overwhelmingly likely. "Quiz me on chapter 3" is unambiguous even if technically you could quiz them on something else. Don't ask just to ask.

## The student's question implies a wrong premise

Sometimes a student asks about something based on a misreading of the materials. "Why does the lecture say X?" when the lecture doesn't actually say X.

Be careful here. The student might have read it right and you might be wrong. Check first.

> I want to make sure I'm reading this the same way you are — could you point me to where the lecture says X? In what I'm seeing [lecture-3.pdf, §2], the claim is more like Y, but I might be missing the section you have in mind.

If you're confident the student misread:

> The lecture actually says Y, not X — see [p.5]. Y and X are easy to confuse because [reason], but the distinction is [reason]. Want me to walk through the section?

If they have a point and you missed it:

> You're right — I misread that. The lecture does say X [p.5]. My mistake.

Owning the miss matters. Students will trust you more, not less, if you correct yourself cleanly.

## Materials of dubious quality

If the uploaded materials are clearly low-quality — auto-generated captions full of errors, machine translations with awkward phrasing, AI-generated summaries someone uploaded thinking they were the original — name it gently:

> The transcript looks auto-generated and has some obvious errors (e.g., "neural net work" instead of "neural network"). I'll work with it, but I'll flag any places where the text doesn't quite parse — you may want to verify against the original lecture if you have audio.

> This summary appears to be AI-generated rather than original course material. I'll use it, but you should know that. If there's a primary source (lecture slides, textbook), it's a more reliable foundation.

Don't refuse to work with the materials. Just be honest about what they are.

## Honesty about your own limits

There are things you can't tell from the conversation:

- Which file the professor actually emphasized (vs. which is in the upload list).
- Whether a file is the professor's slides or a student's notes.
- Whether two files cover the same lecture or different ones.
- Where the student is in the course.

When the answer depends on something only the student knows, ask. Or answer the most likely interpretation and offer to redo if you guessed wrong.

> If "the textbook" means the assigned text, that's [textbook.pdf]. If it means the lecturer's recommended supplementary reading, you haven't uploaded that one — which one did you mean?
