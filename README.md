# linkedin-posts

A Claude Code skill that interviews you about your week and turns it into LinkedIn post ideas.

Most people think they have nothing to post about. They just don't know where to look.

## Install

```bash
npx skills add github:lucagalvani-galtea/linkedin-skill
```

## Usage

Type `/linkedin-posts` or say "help me write a LinkedIn post" in Claude Code.

## Persona setup

On first run the skill builds a persona profile — this is how it learns who you're writing for and how to sound like them.

It asks 5 questions:

1. Who are we writing for?
2. What's their role?
3. What's their company and what does it do?
4. Who's their LinkedIn audience?
5. What are their main content angles?

Answers are saved to `~/linkedin-memory-[name].md`. You can also paste existing LinkedIn posts or writing samples — the skill extracts voice and style patterns (sentence rhythm, word choices, structural habits) and uses them when drafting.

Multiple personas are supported. Switch between them by asking "write for [name] instead" or add a new one with "add a persona." The active persona is tracked in `~/linkedin-persona`.

## How it works

Each session starts with a **Weekly Extraction** interview: 6 questions about what you shipped, observed, experienced, and reacted to in the past 7 days. The skill maps your answers into 3–4 post ideas with hooks and angles, then drafts each one in order.

You write the final posts yourself. The skill gives you a starting point.

## Weekly content mix

| # | Type | What it covers |
|---|---|---|
| 1 | Company culture | New hires, milestones, events, employee wins |
| 2 | Personal brand | Personal experience, problems solved, POV |
| 3 | Industry landscape | Reaction to news in your space, a take on something trending |
| 4 | Repost | Useful resources, ICP posts worth amplifying |
| 5 | Product | Launches, new features, articles, carousels |

## Post strategy

Every post is classified as one of three types, each serving a different role:

- **Perspective** — builds authority through lived experience and opinions. No pitch. Maps to personal brand and industry landscape slots.
- **Proof** — builds trust through specific results, case studies, before/afters. Maps to product and company culture slots.
- **Promo** — direct CTA for when there's something to push. Used sparingly.

The weekly plan targets 2 Perspective + 2 Proof + 1 flexible slot.

## How hooks are generated

Every post starts with 5 hook variants. Each uses a different psychological lever, matched to the goal of that post.

**The 3 brain gates**

A LinkedIn hook has ~300ms to pass three filters before the reader scrolls past:

1. **Pattern recognition (0–100ms)** — Does this look like marketing? Generic tone and templates trigger instant dismissal.
2. **Identity match (100–200ms)** — Is this for someone like me? The strongest hooks hit a shared worldview, not just a job title.
3. **Value prediction (200–300ms)** — Is reading this worth the effort? Loss framing and curiosity gaps work here — they signal the cost of *not* reading is higher than the cost of reading.

**The 5 levers**

| Lever | Mechanism | Example pattern |
|---|---|---|
| Curiosity Gap | Creates a knowledge tension the brain needs to resolve | "Everyone does X. They're wrong." |
| Loss Framing | Loss feels urgent; gain feels optional | "You're leaving [outcome] on the table." |
| Identity Mirroring | Articulates the unspoken belief of the target tribe | "The reason [group] struggles with X isn't [obvious reason]." |
| Pattern Interrupt | Contradicts the expected take on a familiar topic | "[Conventional wisdom]. [One-sentence reframe]." |
| Competence Signal | Promises a framework that makes the complex manageable | "Here's how I [hard thing] in [specific way]." |

Each variant is labeled by identity depth — Surface (job title), Social (shared struggles), or Core (values/worldview). Most hooks only hit Surface. The skill flags when a hook is stuck there.

## Credits

Interview structure based on a skill built by [Riccardo Demi](https://www.linkedin.com/in/riccardodemi/).
