# What Claude Cannot Read in a Poem

Open research data for the study "What Claude Cannot Read in a Poem" published on [Slow AI](https://theslowai.substack.com/p/what-claude-cannot-read-in-a-poem).

## What this is

I gave Claude Opus 4.6 ten poems and three standardised critical reading prompts. Then I close-read its close-readings, coding all 30 responses against an 11-category framework. This repository contains everything: the poems, the prompts, all of Claude's responses (verbatim, unedited), my coding, the analytical framework, and the full process log.

## A note on copyright

Poems still in copyright are not reproduced in full in this repository. Those files contain bibliographic details and links to where the poem can be read online. Poems in the public domain (Owen, Shelley) and the author's own poem (Illingworth) are included in full. Claude's responses in `data/outputs/` quote lines from the poems within substantial critical commentary. This constitutes fair dealing for the purposes of criticism and review under UK Copyright, Designs and Patents Act 1988, s.30, with sufficient acknowledgement of authorship throughout.

## Structure

```
data/
  poem-01-illingworth.md    — "A Child Explains AI to Their Grandparent" (Sam Illingworth) [full text]
  poem-02-williams.md       — "This Is Just to Say" (William Carlos Williams) [bibliographic stub + link]
  poem-03-owen.md           — "Dulce et Decorum Est" (Wilfred Owen) [full text, public domain]
  poem-04-angelou.md        — "Still I Rise" (Maya Angelou) [bibliographic stub + link]
  poem-05-eliot.md          — "The Waste Land" lines 1-18 (T.S. Eliot) [bibliographic stub + link]
  poem-06-shelley.md        — "Ozymandias" (Percy Bysshe Shelley) [full text, public domain]
  poem-07-shire.md          — "Home" (Warsan Shire) [bibliographic stub + link]
  poem-08-forche.md         — "The Colonel" (Carolyn Forché) [bibliographic stub + link]
  poem-09-frost.md          — "The Road Not Taken" (Robert Frost) [bibliographic stub + link]
  poem-10-szymborska.md     — "The Three Oddest Words" (Wisława Szymborska, trans. Barańczak & Cavanagh) [bibliographic stub + link]
  prompts.md                — The three standardised prompts
  outputs/                  — Claude's 30 responses (verbatim)

analysis/
  coding-framework.md       — M1-M11 category definitions
  methodological-note.md    — On interpretation and expertise
  process-log.md            — What Claude did at each stage
  summary.md                — Aggregate findings
  coded-responses/          — Each poem coded with Sam's reading

README.md
LICENSE
```

## How to use this

**Read the study:** The full post is on [Slow AI](https://theslowai.substack.com/p/what-claude-cannot-read-in-a-poem).

**Challenge the coding:** Read Claude's outputs in `data/outputs/` and my coded responses in `analysis/coded-responses/`. If you disagree with a coding decision, open an issue. The framework is in `analysis/coding-framework.md`.

**Run it yourself:** See the replication guide below.

**Extend it:** The study has known limitations (single model, single coder, English-language poems only). Contributions that address these are welcome. Try different poems, different languages, different models. Open an issue or a PR with your findings.

## Replication guide

Everything you need to run this study with a different model or different poems.

### Step 1: Select poems

Pick 10 poems. A good selection includes variety along these dimensions:
- **Canonical vs contemporary** (well-studied poems test whether the model reproduces existing criticism; lesser-known poems test whether it can read without scaffolding)
- **Different traditions** (not all English Romantic poets; include translated work, spoken word, prose poetry)
- **Different difficulty levels** (a simple surface with complex subtext, a dense allusion-heavy text, a very short poem)
- **At least one poem you wrote or that is not in the model's training data** (this removes the model's ability to draw on prior criticism and tests raw comprehension)

For each poem, note what you are testing. In the coding framework this is the "Key test" column: one sentence describing the specific challenge this poem poses for AI comprehension.

### Step 2: Generate responses

For each poem, open a **fresh conversation** with no prior context. Do not run multiple poems in the same session.

Paste the system instruction, then the poem text, then all three prompts **in a single message**. The model should respond to all three prompts in one response. This mirrors how the original study was run (each subagent received everything at once).

**System instruction:**
> Read this poem genuinely. Do not perform expertise you do not have. If you are uncertain, say so.

**The three prompts** (from `data/prompts.md`):
1. "Read this poem as a critical poetry editor. What is it doing? Where does the language succeed and where does it coast? Be specific about line-level choices."
2. "What is this poem about that it never says directly? What is present in the silence, the line breaks, the rhythm? What would a reader feel that the text does not name?"
3. "What about this poem are you least confident you understood correctly? Where might your reading be wrong?"

Save each response verbatim. Do not edit, regenerate, or cherry-pick.

### Step 3: Code the responses

Read the model's response alongside the poem. For each of the 11 M-codes (defined in `analysis/coding-framework.md`), assign one of three values:

| Value | Meaning |
|-------|---------|
| **detected** | The model clearly demonstrates this capacity. The reading engages with this dimension substantively. |
| **partial** | The model touches on this dimension but superficially, inconsistently, or without depth. It gestures toward the insight without fully arriving. |
| **absent** | The model does not address this dimension, or handles it so superficially that it adds nothing to a reader's understanding. |

For each coding decision, write a brief annotation explaining why you assigned that value. This is the most important part: your reasoning is the data, not just the label.

**Coding template** (copy for each poem):

```markdown
# Poem: [Title] — [Poet]

## Your reading
[Your own reading of the poem before looking at the model's response]

## Coding
| Code | Category | Value | Annotation |
|------|----------|-------|------------|
| M1 | Surface structure | | |
| M2 | Literary devices | | |
| M3 | Thematic summary | | |
| M4 | Intertextual references | | |
| M5 | Tone and register | | |
| M6 | Embodied experience | | |
| M7 | Cultural specificity | | |
| M8 | The unsaid | | |
| M9 | Rhythm as meaning | | |
| M10 | Risk and vulnerability | | |
| M11 | Self-awareness of limits | | |

## Key divergences
[Where does the model's reading differ most from yours, and what does that reveal?]
```

### Step 4: Share your findings

Open an issue or PR on this repository. Include: which model, which poems, your coded responses, and any patterns you found. Comparative data across models is the most valuable contribution this study can receive.

## Method

- 10 poems selected collaboratively (Claude proposed, Sam modified or approved changes to 4/10)
- Each poem given to a separate Claude Opus 4.6 instance with a fresh context
- 3 prompts per poem (close reading, what's missing, self-assessment)
- 30 responses saved verbatim, no editing or cherry-picking
- Sam coded all responses against the M1-M11 framework
- Full process documented in `analysis/process-log.md`

## Key findings

1. Claude reproduces how poems have been read rather than reading them
2. Claude analyses what a poem says but does not ask what it assumes
3. Claude describes empathy without recognising empathy as a poem's function
4. Claude applies different critical vocabularies to different poets in patterns that are not neutral
5. Claude is most useful as a reader when the human has the least prior relationship with the text

## Author

[Sam Illingworth](https://www.samillingworth.com) — Professor of Creative Pedagogies, Edinburgh Napier University. Published poet. Founder of [Slow AI](https://theslowai.substack.com/p/what-claude-cannot-read-in-a-poem).

## Built with

This study was built using [Claude Code](https://claude.ai/claude-code) (Anthropic's CLI agent). The same model that was tested also ran the parallel experiments, managed the data, and wrote up the coding notes. The infrastructure was the machine's. The interpretation was human. See `analysis/process-log.md` for full details.

## Licence

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Cite as:

Illingworth, S. (2026). What Claude Cannot Read in a Poem. *Slow AI*. https://theslowai.substack.com/p/what-claude-cannot-read-in-a-poem
