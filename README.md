# metatext

A skill for AI coding agents (Claude Code, and compatible harnesses) that makes any deliverable read as a standalone artifact for its real audience — free of *metatext*: the leakage where the output talks about itself, the request, the options it considered, or the person who asked, instead of just being the thing.

A report, email, contract, essay, slide, or function should read as if a competent professional made it for its real reader and handed it over with no chat around it. Metatext is every trace of the prompt-and-AI situation that leaks into the artifact instead — option menus left in, reflexive disclaimers, eyebrow labels ("ELEVATOR PITCH"), signposting ("Here is the short version"), addressing the requester instead of the audience, and content a real instance of that artifact would never carry.

## What's here

- **`SKILL.md`** — the skill itself: the core test, the two layers (sentence-level and artifact-level), the causal model, and a two-move procedure (register the true ask, then produce-and-strip), plus an adversarial audit mode.
- **`reference/taxonomy.md`** — the worked catalogue: every pattern with before/after fixes. Used as an audit checklist.
- **`reference/grounding.md`** — the published research behind the causal model (length bias, sycophancy, over-caution, ambiguity under-resolution, format/persona leakage), with citations.

## The core idea

Most metatext is not bad prose — it is failing to register the real job. Before producing, register four things: the **artifact** (the real-world object, not the prompt category), the **audience** (who receives it, not who asked), the **intended nature** (what the object is *for* — persuade, instruct, bind, document, execute — and whether the content actually does that), and the **exemplar** (what a real instance contains, and what it never contains). Get that right and most metatext never appears. Then strip whatever remains.

The test: *Could this be handed to its real audience exactly as is, with zero surrounding explanation — and would a human expert in this genre have written it the same way?* If not, something is leaking. Cut until yes.

## Install

Skills are auto-discovered from the skills directory. Drop this folder in:

```
~/.claude/skills/metatext/
```

The agent loads it on demand when a task involves producing or auditing an audience-facing deliverable, or on explicit triggers like "check for metatext" or "make this a standalone document."

## Scope

`metatext` handles scope, self-reference, and intent registration. It composes with, but is distinct from, tone-and-restraint skills (for high-stakes correspondence) and sentence-level de-AI-ing skills (for rhythm and word-choice tells). Run `metatext` first: does this artifact exist for the right reader, in the right shape, at all?
