# GitHub Copilot: From “AI is cool” to useful work

**Target length:** 15 minutes  
**Audience:** Engineers using terminal tools, IntelliJ, or VS Code  
**Deck:** `copilot-presentation.pptx`

## Delivery notes

This is a practical introduction, not a feature tour. Keep the pace conversational
and let the hook breathe. The central message is:

> Copilot is most useful when the engineer provides context, sets boundaries,
> makes a focused request, and verifies the result.

The deck uses a dark terminal theme. The hook slide is intentionally animated
one click at a time.

---

## Slide 1 — From “AI is cool” to useful work

**Time:** 0:00–0:45

“Thanks, everyone. This is a quick introduction to using GitHub Copilot in the
tools we already use: the terminal, IntelliJ, and VS Code.

I am not going to cover every feature or promise that Copilot can do the work
for us. Instead, we are going to look at one repeatable engineering loop:
provide context, state the intent, make a focused change, and prove that the
result is correct.

The goal is to leave with something you can try on a small task today.”

**Transition:** “Before we talk about useful work, let’s talk about why AI gets
our attention in the first place.”

---

## Slide 2 — Two words. Infinite interpretations.

**Time:** 0:45–2:30  
**Animation:** All elements are on-click.

### Click 1 — Original image

“This is a picture of me with my first largemouth bass. Nothing particularly
unusual: just a guy, a fish, and a suspiciously large fish scale.”

### Click 2 — “Kind of ridiculous” label

“I gave Nano Banana this prompt:

> I’m going to be giving a quick 15-minute overview of how to use Copilot CLI
> for work. I’m going to open with an ‘AI is cool…’ bit. Can you take this
> picture of me with my very first largemouth bass and turn it into something
> kind of ridiculous?

That gives the tool context, the audience, the purpose, and a general
direction.”

### Click 3 — Kind-of-ridiculous image

“And this is what it came up with. It is already a little ridiculous, but it
still has a recognizable relationship to the original request.”

### Click 4 — First prompt

“The request is not perfectly precise, but it gives the model something to work
with. There is a subject, a use case, and a desired level of change.”

### Click 5 — “More ridiculous” label

“Then I asked it to go further.”

### Click 6 — More-ridiculous image

“This is where the model became extremely enthusiastic. It added more screens,
more hardware, more creatures, more visual noise, and generally more of
everything.”

### Click 7 — Second prompt

“And this was the entire follow-up prompt.”

### Click 8 — First takeaway

“The first prompt had context. The second prompt had almost none.”

### Click 9 — Final takeaway

“What does ‘more ridiculous’ mean to me? What does it mean to you? What does it
mean to the model?

If we are not explicit with these tools, they will confidently fill in the
gaps. They will turn the entropy up to 11 and leave us—the engineers in the
real world—holding the bag.

That is the real lesson behind the joke. AI can generate something impressive.
Useful work needs context and boundaries. Trustworthy work needs review and
validation.”

**Transition:** “So the useful question is not what AI can do in general. It is
what it can help us do today.”

---

## Slide 3 — The useful question is not “what can AI do?”

**Time:** 2:30–3:45

“We all know AI can generate images, write stories, summarize meetings, and
answer questions. That is the fun part, and it is a good way to get our
attention.

The useful question is:

> What can it help me do today that I already need to get done?

For engineering work, that might be explaining an unfamiliar class, finding
where a behavior is implemented, drafting a focused test, or helping diagnose
an error.

Copilot can help with those activities, but it does not own the requirement,
the tradeoffs, or the final decision. The engineer still owns the result.”

**Transition:** “The good news is that Copilot is available in the places where
we already do this work.”

---

## Slide 4 — Start in the tool already in front of you

**Time:** 3:45–5:00

“Use the interface that matches the work.

In the terminal, Copilot CLI is useful for repository exploration, scripts,
commands, and changes that need to be reviewed in a worktree.

In IntelliJ, it can help explain classes and collaborators, suggest focused
tests, and work alongside compiler errors and IDE inspections.

In VS Code, it is useful for polyglot repositories, configuration, scripts,
documentation, and the integrated terminal.

The interface changes, but the discipline does not. Start with a small task,
provide the relevant context, inspect the result, and run the normal checks.”

**Transition:** “That discipline can be reduced to four steps.”

---

## Slide 5 — Context → intent → change → proof

**Time:** 5:00–6:45

“This is the loop I recommend for almost every Copilot task.

First: **context**. Give it the relevant file, symbol, error, test, command
output, version, and constraints. Do not assume it knows which part of the
system matters.

Second: **intent**. State the desired behavior and the boundaries. Say what may
change, what must not change, and whether editing is allowed.

Third: **change**. Ask for one focused, reviewable improvement. Broad prompts
produce broad diffs.

Fourth: **proof**. Inspect the diff and run the smallest relevant test, lint,
build, or type check.

This is not bureaucracy added around AI. It is the normal engineering process
made explicit enough for another participant—whether human or model—to follow.”

**Transition:** “The most important part is often the wording of the boundary.”

---

## Slide 6 — Say what you mean—and what you do not mean

**Time:** 6:45–8:15

“Here is a prompt with a useful boundary:

> Explain how this request flows through the repository. Identify the relevant
> files and tests. Do not edit anything yet.

That prompt gives Copilot a job, a scope, an expected output, and a permission
boundary. It can explore without silently changing the worktree.

Useful phrases include:

> Explain this; do not edit files.

> Change only this behavior; do not refactor unrelated code.

> Preserve the public API and existing error handling.

> List assumptions and open questions before implementing.

> Run the smallest relevant check and report exactly what it verified.

The point is not to write a giant prompt every time. The point is to make the
important constraints visible.”

**Transition:** “There is another choice we make before or during a task:
which model to use.”

---

## Slide 7 — Model choice is a tradeoff, not a leaderboard

**Time:** 8:15–9:30

“When organizational credits are shared, model selection is a resource
decision.

Use a fast, economical model for explanations, navigation, boilerplate,
formatting, small edits, and routine tests.

Move to a more capable model when the task involves unfamiliar architecture,
multiple files, difficult debugging, or competing constraints.

The strongest model is not automatically the best choice. A high-cost model
cannot compensate for a vague requirement. Give the model complete, relevant
context first, and use more capability when the task genuinely needs it.

The goal is not always choosing the strongest model. The goal is successful
outcomes per credit.”

**Transition:** “Regardless of the model, there are some guardrails we should
not outsource.”

---

## Slide 8 — Fluent does not mean correct

**Time:** 9:30–10:45

“Copilot can sound certain while being wrong. Fluency is not proof.

Verify APIs, assumptions, edge cases, and whether generated tests actually prove
the requirement.

Keep the scope small enough that you can review the diff. Broad prompts can
produce broad changes that are difficult to understand.

Never paste secrets, tokens, customer data, or unnecessary proprietary content.

Review generated terminal commands before running them, especially commands that
delete, overwrite, migrate, or modify shared resources.

And do not let Copilot silently decide architecture, product requirements, or
security policy. Those decisions need accountable human ownership.”

**Transition:** “Let’s apply the loop to a small live example instead of
watching a giant repository scan.”

---

## Slide 9 — A small demo beats a giant repository tour

**Time:** 10:45–13:45

“For the demonstration, I am going to use one bounded slice of the repository.
The objective is to orient Copilot, choose one small documentation improvement,
make only that change, and verify it.

First, I ask:

> Give me a concise map of this repository for a new engineer. Focus on the
> main services, entry points, and how to find the tests. Cite specific files.
> Do not edit anything. Call out anything you are uncertain about.

Notice that I asked for citations and explicitly prohibited edits. That makes
the answer easier to check.

Next:

> Based on that map, find one existing documentation gap that can be fixed
> without changing application code. Propose the smallest change first. Do not
> edit until I approve the proposed file and wording.

Again, I am separating exploration from permission to change.

Once I approve the file and wording, I ask:

> Make only the approved documentation change. Preserve the existing style. Do
> not modify source code, dependencies, generated files, or unrelated
> documentation. Show me a concise summary of the diff when finished.

Now I review the diff. I am checking whether it touched only the approved file,
whether it invented commands or behavior, and whether the wording matches the
repository.

Finally:

> Verify this documentation change using the smallest appropriate check. If
> there is no documentation-specific check, inspect the diff for broken
> Markdown, incorrect paths, and unsupported claims. Report exactly what you
> verified and what remains uncertain.

That is the entire pattern: context, intent, change, proof. It is small enough
to finish, and the result is reviewable.”

**If the live demo is slow or unavailable:**

“The important part of this demonstration is the method, not the latency of the
tool. I would rather show a bounded workflow and explain each decision than
spend the session waiting for a broad scan.”

**Transition:** “The same method applies whether the interface is a terminal,
an IDE, or an editor.”

---

## Slide 10 — Keep the power. Supply the context.

**Time:** 13:45–15:00

“The takeaway is simple:

Start small.

State the boundaries.

Review the result.

Run the checks.

Copilot is an engineer’s second set of eyes across a complicated system. It is
not the person responsible for the result.

If you remember only one loop, remember:

> Context → intent → change → proof.

Start with the tool already open in front of you and a small task you already
need to complete. That is the fastest way to turn ‘AI is cool’ into useful,
repeatable work.

Thank you. Questions?”

---

## Quick rehearsal checklist

- Keep the hook under two minutes, including audience reaction.
- Pause before revealing the bare `more ridiculous` prompt.
- Do not read every bullet on slides 3, 4, or 8; use them as visual anchors.
- Rehearse the live demo with a known fallback explanation.
- Keep the final loop visible during questions.
