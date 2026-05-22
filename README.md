# linkedin-weekly-planner

A Claude Code skill that interviews you about your week and turns it into LinkedIn post ideas.

Most people think they have nothing to post about. They just don't know where to look.

## Install

```bash
npx skills add github:lucagalvani-galtea/linkedin-weekly-planner
```

## Usage

Type `/linkedin-weekly-planner` or say "help me brainstorm my LinkedIn week" in Claude Code.

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

### Step 1 — The interview

The skill asks you 6 questions about the past 7 days: what you shipped, any team news, a work challenge, something from outside work, a reaction to something in your industry, and anything worth reposting. One question at a time. It probes for specifics — generic answers produce generic posts.

### Step 2 — Content ideas

From your answers it generates 5 structured content ideas. For each one it identifies:

- **Content type** — Contrarian Take, Case Study, Tactical How-To, Personal/Vulnerable, Curation, or Observation
- **Weekly slot** — which of the 5 post types it fits (company culture, personal brand, industry landscape, repost, product)
- **Post strategy** — whether the post should build authority (Perspective), demonstrate results (Proof), or drive action (Promo)
- **Content goal** — thought leadership, audience growth, engagement, or save-worthy

These four dimensions together determine what kind of hook will work and how the post should be written. The skill then picks the best 3–4 ideas and proposes a week plan.

### Step 3 — Hook generation and drafting

For each post in the plan, the skill generates 5 hook variants — one per psychological lever — matched to the post's content goal. You pick the hook, then the skill drafts the full post (hook + body + close) in the persona's voice.

You write the final posts yourself. The skill gives you the starting point.

## The 5 weekly slots

| # | Type | What it covers |
|---|---|---|
| 1 | Company culture | New hires, milestones, events, employee wins |
| 2 | Personal brand | Personal experience, problems solved, POV |
| 3 | Industry landscape | Reaction to news in your space, a take on something trending |
| 4 | Repost | Useful resources, ICP posts worth amplifying |
| 5 | Product | Launches, new features, articles, carousels |

## The 5 psychological levers

Every hook must pass 3 brain gates in the first 300ms of reading — pattern recognition, identity match, and value prediction. The 5 levers are the mechanisms for clearing them:

| Lever | Mechanism | Example pattern |
|---|---|---|
| Curiosity Gap | Creates a knowledge tension the brain needs to resolve | "Everyone does X. They're wrong." |
| Loss Framing | Loss feels urgent; gain feels optional | "You're leaving [outcome] on the table." |
| Identity Mirroring | Articulates the unspoken belief of the target tribe | "The reason [group] struggles with X isn't [obvious reason]." |
| Pattern Interrupt | Contradicts the expected take on a familiar topic | "[Conventional wisdom]. [One-sentence reframe]." |
| Competence Signal | Promises a framework that makes the complex manageable | "Here's how I [hard thing] in [specific way]." |

Each variant is labeled by identity depth — Surface (job title), Social (shared struggles), or Core (values/worldview). The skill flags when a hook is stuck at Surface.

## Credits

Interview structure based on a skill built by [Riccardo Demi](https://www.linkedin.com/in/riccardodemi/).
