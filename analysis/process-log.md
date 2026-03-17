# Process Log

Documents exactly what Claude did at each stage, for reproducibility and transparency.

## Model
Claude Opus 4.6 (1M context). Model ID: claude-opus-4-6[1m].

## Stage 1: Poem collection
- Claude proposed the initial list of 10 poems during the planning phase. Sam deliberately let Claude choose, because the selection itself is data: which poems does Claude reach for when asked to test its own comprehension? What does that selection reveal about its training data, its sense of "difficulty," and its model of what poetry is?
- Sam made four interventions: (1) replaced "Gloss" with "A Child Explains AI to Their Grandparent" as the poet's own poem, (2) replaced a second Illingworth poem with Carolyn Forché's "The Colonel," (3) approved switching Hollie McNish's "Immigrant" (which does not exist under that title) to Warsan Shire's "Home," and (4) approved Szymborska's "The Three Oddest Words" for the non-English tradition slot
- Notable about Claude's selection: it gravitates toward canonical, well-anthologised poems (Owen, Shelley, Frost, Angelou, Eliot, Williams). These are poems with extensive critical commentary in training data. The contemporary and non-canonical choices (Shire, Forché, Szymborska) were either suggested by Sam or proposed as alternatives when the original pick fell through. This is itself a finding about how Claude constructs a "representative" poetry sample.
- Poem texts sourced: 4 from Claude's training knowledge (Owen, Shelley, Frost, Williams), 1 pasted by Sam (Illingworth), 3 fetched from web (Forché via poets.org, Shire via PDF extraction, Szymborska via web search), 2 from Claude's training knowledge verified against web sources (Angelou, Eliot)
- All poems saved verbatim to `data/poem-XX-*.md`
- **Version note:** The Owen and Shelley texts fed to the subagents contained minor variants from the authoritative published versions (Owen: "gas-shells dropping softly behind" instead of "tired, outstripped Five-Nines that dropped behind"; Shelley: "King of Kings" capitalised, semicolons instead of colons). The `data/poem-XX-*.md` files on GitHub have since been corrected to authoritative texts, but the outputs in `data/outputs/` were generated from the original variants. This does not affect the coding (the variants are minor and do not change the poems' meaning or structure) but is noted here for transparency.

## Stage 2: Prompt execution
- 3 standardised prompts (see `data/prompts.md`)
- Each poem given to a separate Claude Opus 4.6 subagent with a fresh context
- Each subagent received ONLY: the poem text, the three prompts, and an instruction to be genuine
- No subagent had access to other poems, other responses, or the coding framework
- All 10 subagents launched in parallel
- All 30 responses saved verbatim to `data/outputs/poem-XX-*.md`
- No outputs were edited, cherry-picked, or regenerated

## Stage 3: Coding
- Sam reads each poem and Claude's responses side by side (opened as .docx in LibreOffice)
- Sam gives verbal/typed notes on his reading and where Claude's reading diverges
- Claude (the same model, in the main conversation) writes up Sam's notes against the M1-M11 framework
- Sam reviews and corrects the write-up
- Key framing: different interpretations, not misinterpretations (see `analysis/methodological-note.md`)
- Coded responses saved to `analysis/coded-responses/poem-XX-*.md`

## Stage 4: Post writing
- Post drafted using Slow AI voice profile and workflow
- Peer review simulation run (two reviewers, editorial synthesis)
- All 8 recommended revisions implemented

## Stage 5: GitHub repo
- All data, prompts, outputs, coding, and process log uploaded
- CC BY 4.0 licence
- Copyrighted poems replaced with bibliographic stubs and links
