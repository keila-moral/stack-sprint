---
title: My editor shouldn't talk while I think
subtitle: Why I went back to Vim, and how I still use AI without letting it into my train of thought.
date: 2026-11-19
tags: [tools, vim, ai, workflow]
---

A while ago I gave VS Code a fair try. Proper setup, the popular extensions,
Copilot switched on. I lasted a few weeks before going back to Vim.

It wasn't that the tools were bad. They were *loud*. GitLens put the author and
commit message of every line right next to my cursor, and I kept catching
myself reading who wrote what and why instead of writing the thing I had
opened the file for. Copilot was worse: every time I paused to think, a grey
block of code appeared to finish my sentence. Sometimes it was right. Often it
was almost right. Either way, my train of thought was gone, replaced by a
review of someone else's guess.

## The laptop that couldn't run an IDE

I learned Vim during my PhD, mostly out of necessity. My work laptop had so
little capacity that the terminal was nearly the only thing it could run
comfortably. An IDE was out of the question. So it was Vim, a shell, and me.

In that setup I wrote my first analysis framework. It was awful. And it taught
me more than almost anything I've written since:

- **How to build a library**, not a pile of scripts: packaging, dependencies,
  and what happens when one of them changes under you.
- **How to debug properly**, because there was nothing to suggest a fix. I had
  to read the traceback, form a hypothesis, and test it.
- **How to document**, because the first person who tried to use it was
  confused, and the second one was me, six months later.
- **How to think about legacy.** Code is read by other people far more often
  than it is written. Writing for them is part of the job.
- **How to respect the machine.** The data was large and the hardware was
  small, so I had to learn parallelisation and think about memory and CPU
  instead of assuming they were free.

None of those lessons came from getting the code right the first time. They
came from getting it wrong, noticing, and fixing it myself. The friction *was*
the teacher.

## Autocomplete answers the question you haven't finished asking

Writing code is a thinking process that happens to produce text. When I pause
mid-line, I'm usually not stuck on syntax. I'm deciding something: what this
function should own, what the data looks like at this point, what will break
if I do it this way.

Inline suggestions treat that pause as a gap to fill. They answer before I've
finished forming the question, and evaluating an answer is a different mental
mode than producing one. Do that switch a hundred times a day and you rarely
reach the deep focus where the hard problems actually get solved. Research on
developer interruptions has been saying this for years: getting back into a
complex task after a break is expensive, and small interruptions add up.

## I still use AI, just not in my editor

This isn't an anti-AI post. These days a big part of my work is reorganising
the architecture of a whole library. I spend more time on design and
optimisation than on individual features, and that's where an AI assistant
genuinely helps me. I use Claude to keep the wider picture in view: talking
through trade-offs, checking how a change ripples through modules, keeping
track of decisions I'd otherwise lose.

The difference is *when* and *where*. I go to the assistant when I want a
second opinion. It doesn't come to me ten times a minute while I'm typing.
One deliberate conversation is help. Ten pop-ups on your desk is noise.

## What works for me

My setup now is deliberately boring:

- **Vim in a minimal terminal.** No sidebars, no inline blame, no ghost text.
  It keeps me calm and focused, and that is what makes or breaks my flow.
- **Keyboard only.** Not reaching for the mouse sounds minor, but it keeps my
  hands, and my thinking, in one place.
- **AI in a separate window, on purpose.** I open it for architecture, review
  and the boring bits. I close it when I'm writing the code I need to
  understand.
- **A clear view of the machine.** In a terminal it's natural to keep an eye on
  processes, memory and cores, which matters when your code is the thing
  eating them.

If you're early in your career, I'd add one more: write some awful code by
yourself, without suggestions, and debug it. It's slower. It's also how you
learn what the suggestions are getting wrong.

## Further reading

- [Measuring the impact of early-2025 AI on experienced open-source developer productivity](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/) (METR). Experienced developers expected AI to speed them up, but in this study it made them slower.
- [The Impact of Generative AI on Critical Thinking](https://www.microsoft.com/en-us/research/publication/the-impact-of-generative-ai-on-critical-thinking-self-reported-reductions-in-cognitive-effort-and-confidence-effects-from-a-survey-of-knowledge-workers/) (Microsoft Research, CHI 2025). A survey on how relying on AI changes how much we think things through.
- [Programmer, Interrupted](https://blog.ninlabs.com/2013/01/programmer-interrupted/) (Chris Parnin). A classic on the cost of interruptions for developers.
- [Maker's Schedule, Manager's Schedule](https://www.paulgraham.com/makersschedule.html) (Paul Graham). Why makers need long, unbroken blocks of time.
- *Deep Work* by Cal Newport. The case for protecting focused time.
- *Practical Vim* by Drew Neil, and `vimtutor` (already on your machine, just type it in a terminal). The best ways I know to get comfortable in Vim.
- [Configuring GitHub Copilot in your environment](https://docs.github.com/en/copilot/configuring-github-copilot/configuring-github-copilot-in-your-environment). If you want to keep Copilot but turn off inline suggestions and call it up only when you ask.
