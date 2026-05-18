# crash-course

A portable Agent Skill that turns any LLM into a study partner grounded in your course materials.

You upload your lecture slides, lecture notes, transcripts, textbook PDFs, problem sets, basically anything your LLM can read. The skill makes the model treat those files as the curriculum, cite where every claim comes from, distinguish your materials from its general knowledge, and quiz you, summarize, or explain on demand.

## What it does

Six modes, all driven by your materials:

- **Q&A**: answer factual questions with citations
- **Explain**: build understanding step by step, using your professor's notation
- **Summarize**: condense lectures, chapters, or the whole course
- **Quiz**: active recall with answers held until you attempt
- **Connect**: relate concepts across files; surface conflicts when sources disagree
- **Locate**: find where in your materials a topic lives

The skill picks the mode from how you ask. "Quiz me on chapter 3" enters quiz mode. "Where is logistic regression covered?" enters locate mode. "I don't get backprop" enters explain mode.

## Triggering

The skill triggers automatically. You don't necessarily need to type `/crash-course` or invoke anything explicitly but it is still recommended to do so as LLM's can sometimes choose not to use the skill even when they know they should when the task seems too "trivial" for them (currently trying to find a workaround). Just upload your materials and ask a study-related question ("explain this chapter," "quiz me on lecture 4," "summarize the syllabus," "I don't get this part"). It activates whenever it detects files attached + a study-flavour request, and stays active for the rest of the conversation until you explicitly drop it.

It will NOT activate on: pure code-writing tasks, non-academic uploads with no study intent (contracts, receipts), or factual lookups that don't reference your files.

## Why it exists

Bare LLM study chat hallucinates, papers over conflicts, and silently mixes its training data with your uploads. This skill imposes a discipline: materials are the source of truth, every grounded claim gets a citation, gaps are flagged honestly, and conflicts get surfaced for you to resolve.

## A short example

> **You:** I uploaded lecture 4 and the textbook chapter on logistic regression. Why does the loss in the slides look different from the textbook's?
>
> **Skill:** They're the same loss written differently. Your slides [lecture-4.pdf, p.6] write it as a single expression with `y_i log(p_i) + (1-y_i) log(1-p_i)`. The textbook [textbook.pdf, p.143] splits it into two cases — one for `y_i = 1` and one for `y_i = 0`. Both evaluate to the same number for binary targets; the slides' form is just compact, the textbook's is more explicit.
>
> Your slides don't note this equivalence. Want me to walk through why the two forms agree, or move on?

That's the crux of it. Claims backed by proper citation and materials before general knowledge.

## Installation

The skill is a simple directory of markdown files. Drop it where your host expects skills to live.

### Claude Code

Clone into your skills directory:

```bash
git clone https://github.com/suiiibhit/crash-course.git ~/.claude/skills/crash-course
```

Or your project's `.claude/skills/` directory if you want it scoped to one project. The skill is detected on next session start. Trigger by uploading materials and asking a study question — no slash command needed.

### Claude.ai

Settings → Skills → upload the `crash-course/` directory (or a zip of it). Once installed, the skill triggers automatically when you upload course materials and ask a study-related question.

### Claude API / Anthropic SDK

Clone the repo, load `SKILL.md` from disk, and inject it as part of your system prompt or tool context:

```bash
git clone https://github.com/suiiibhit/crash-course.git
```

The skill is designed for progressive disclosure: load `SKILL.md` upfront, and load files from `references/` on demand using the routing rules in the "When to load reference files" section of `SKILL.md`.

If you're using the Anthropic SDK with Managed Agents, the skill works as a standard Agent Skill — point the agent at the directory.

### Other LLMs supporting the Agent Skills format

The skill is pure markdown. Drop the directory into your host's skill folder in whatever shape that host expects, and it should work with any LLM capable of reading your uploaded files.

## How it works

The skill uses progressive disclosure:

- `SKILL.md` is the always-loaded body. It has the operating principles, mode routing, and everyday citation rules. Kept short so it doesn't bloat the host's context.
- `references/` files are loaded on demand. Each one covers a slice of the methodology in detail: per-mode behavior (`modes.md`), citation conventions (`grounding.md`), quiz patterns (`quiz-design.md`), and ambiguity handling (`ambiguity.md`).

The host LLM reads `SKILL.md` whenever the skill triggers. It pulls in references only when the situation calls for them like `quiz-design.md` only when a quiz starts, `ambiguity.md` only when sources conflict, and so on.

## Limitations

- **File format support depends on the host.** The skill assumes the host LLM can read what you upload. If your host can't parse a particular format (older `.doc`, scanned image PDFs without OCR, video files), the skill can't either.
- **No persistence across sessions.** Skills don't store state. If you start a new conversation, you'll need to re-upload your materials. The skill defines how the LLM reasons from materials, not how it remembers them.
- **Citations are only as precise as your host's extraction.** If your host returns page-number metadata, citations include pages. If it doesn't, citations fall back to filenames. The skill is honest about its limits and it won't fabricate page numbers.
- **It's a methodology, not a database.** The skill doesn't know your course better than your materials.

## Contributing

Issues and PRs welcome. If you've used the skill on a real course and found cases where it falls down like bad citation behavior, missed routing, awkward phrasing, etc. just open an issue with the prompt and a sanitized snippet of the materials, and I'll iterate.

If you've ported it to a non-Claude host and had to tweak anything, share what changed. The goal is keeping the core skill genuinely portable to all LLM's.
