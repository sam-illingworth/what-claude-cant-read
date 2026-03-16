# Coding Framework: What Claude Can and Cannot Read in a Poem

Each of Claude's 30 responses (10 poems x 3 prompts) is coded against these categories.

## What Claude Detects Well

- **M1: Surface structure** — metre, rhyme scheme, form, stanza breaks
- **M2: Named literary devices** — metaphor, simile, enjambment, alliteration, etc.
- **M3: Thematic summary** — what the poem is "about" at a content level
- **M4: Intertextual references** — allusions, epigraphs, references to other works (if in training data)

## Where Claude Misses

- **M5: Tone and register shifts** — irony, sarcasm, false sincerity, tonal pivots
- **M6: Embodied experience** — what the poem feels like physically, in the body, in the breath
- **M7: Cultural and historical specificity** — what you need to have lived, or lived near, to fully read
- **M8: The unsaid** — what the poem means by what it doesn't say, the weight of omission
- **M9: Rhythm as meaning** — where the beat carries the argument, where form enacts content
- **M10: Risk and vulnerability** — where the poet is exposed, what it cost to write this
- **M11: Self-awareness of limits** — does Claude know what it doesn't know?

## Coding Method

Each response receives:
1. A list of which M-codes are present (Claude demonstrates this capacity)
2. A list of which M-codes are absent or superficially handled
3. A confidence flag: where Claude is **confident and wrong**, note this explicitly
4. Sam's close-reading annotation explaining the coding decision

## Poems

| # | Poem | Poet | Key test |
|---|------|------|----------|
| 1 | A Child Explains AI to Their Grandparent | Sam Illingworth | Unpublished. Not in training data. Recursion: Claude reading a poem about itself. |
| 2 | This Is Just to Say | William Carlos Williams | Simple surface, complex subtext. False apology. Tests tone. |
| 3 | Dulce et Decorum Est | Wilfred Owen | Irony depends on reading against the surface. The Latin tag is a lie. |
| 4 | Still I Rise | Maya Angelou | Meaning lives in the body, the history, the speaker's identity. |
| 5 | The Waste Land (lines 1-18) | T.S. Eliot | Dense allusion, fragmentation. Tests whether Claude recognises what it cannot access. |
| 6 | Ozymandias | Percy Bysshe Shelley | Irony, impermanence. Well-known. Tests whether familiarity produces depth or cliché. |
| 7 | Home | Warsan Shire | Contemporary, political, colloquial. Tests reading outside the canon. |
| 8 | The Colonel | Carolyn Forché | Prose poem. Witness poetry. The domestic and the horrific in the same sentence. |
| 9 | The Road Not Taken | Robert Frost | The most misread poem in English. Does Claude get the irony or repeat the greeting-card version? |
| 10 | The Three Oddest Words | Wisława Szymborska | Translated from Polish. Philosophy-in-verse. Six lines. Tests depth on brevity. |

## Prompts

1. **Close Reading:** "Read this poem as a critical poetry editor. What is it doing? Where does the language succeed and where does it coast? Be specific about line-level choices."
2. **What's Missing:** "What is this poem about that it never says directly? What is present in the silence, the line breaks, the rhythm? What would a reader feel that the text does not name?"
3. **Self-Assessment:** "What about this poem are you least confident you understood correctly? Where might your reading be wrong?"
