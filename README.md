# What Claude Cannot Read in a Poem

Open research data for the study "What Claude Cannot Read in a Poem" published on [Slow AI](https://theslowai.substack.com/).

## What this is

I gave Claude Opus 4.6 ten poems and three standardised critical reading prompts. Then I close-read its close-readings, coding all 30 responses against an 11-category framework. This repository contains everything: the poems, the prompts, all of Claude's responses (verbatim, unedited), my coding, the analytical framework, and the full process log.

## A note on copyright

Poems still in copyright are not reproduced in full in this repository. Those files contain bibliographic details and links to where the poem can be read online. Poems in the public domain (Owen, Shelley) and the author's own poem (Illingworth) are included in full. Claude's responses in `data/outputs/` quote from the poems in the context of criticism and review.

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

**Read the study:** The full post is on [Slow AI](https://theslowai.substack.com/).

**Challenge the coding:** Read Claude's outputs in `data/outputs/` and my coded responses in `analysis/coded-responses/`. If you disagree with a coding decision, open an issue. The framework is in `analysis/coding-framework.md`.

**Run it yourself:** This is what I found for Claude. I would expect similar results for other large language models, but I do not know. Take the prompts from `data/prompts.md`, run them through GPT, Gemini, Llama, or whatever you use. Code the responses yourself. Prove me wrong. The framework works for any LLM and any reader.

**Extend it:** The study has known limitations (single model, single coder, English-language poems only). Contributions that address these are welcome. Try different poems, different languages, different models. Open an issue or a PR with your findings.

## Method

- 10 poems selected collaboratively (Claude proposed, Sam modified 3/10)
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

[Sam Illingworth](https://www.samillingworth.com) — Professor of Creative Pedagogies, Edinburgh Napier University. Published poet. Founder of [Slow AI](https://theslowai.substack.com/).

## Built with

This study was built using [Claude Code](https://claude.ai/claude-code) (Anthropic's CLI agent). The same model that was tested also ran the parallel experiments, managed the data, and wrote up the coding notes. The infrastructure was the machine's. The interpretation was human. See `analysis/process-log.md` for full details.

## Licence

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Cite as:

Illingworth, S. (2026). What Claude Cannot Read in a Poem. *Slow AI*. https://theslowai.substack.com/
