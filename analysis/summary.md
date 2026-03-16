# Aggregate Findings: What Claude Can and Cannot Read in a Poem

## Study Parameters
- **Model:** Claude Opus 4.6 (1M context)
- **Poems:** 10 (4 pre-20th century, 3 20th century, 3 contemporary)
- **Prompts:** 3 per poem (close reading, what's missing, self-assessment)
- **Responses:** 30 total, each from a fresh context (no contamination between poems)
- **Human reader:** Sam Illingworth (published poet, professor, one poem is his own)
- **Method:** Sam coded each response against the M1-M11 framework after reading Claude's outputs

## What Claude consistently does well

### 1. Surface structure and formal analysis (M1, M2)
Claude identifies metre, rhyme scheme, form, stanza breaks, enjambment, and named literary devices with consistent accuracy across all 10 poems. Its formal analysis is detailed and competent. This is Claude's strongest and most reliable mode.

### 2. Thematic summary (M3)
Claude can say what a poem is "about" at a content level. It identifies the central argument, the address, the subject matter. It does not typically get the theme wrong. It sometimes gets it incomplete.

### 3. Self-assessment (M11)
Claude's self-assessment was consistently the strongest section. It hedged appropriately, flagged genuine uncertainties, and in several cases (Poems 1, 2, 9) identified the exact limitations that Sam's coding confirmed. When Claude says "I might be wrong here," it often is.

## What Claude consistently misses or handles differently

### 4. The projected reader
Claude does not read poems. It reproduces how poems have been read. For each poem, it projects a specific reader from the dominant critical tradition in its training data. For Eliot, the projected reader is an academic modernist. For Ozymandias, it is a student of Romantic poetry. For Frost, it is someone who has read the "actually it's ironic" essays. Claude's readings are composites of existing criticism, not original encounters with text.

### 5. Consensus as analysis
For well-studied poems (Ozymandias, Frost, Eliot), Claude's readings are competent, polished, and indistinguishable from existing critical commentary. They contain no original observation. A five-year-old's reading would be less technically accurate and far more interesting. Claude's value as a reader may be inversely proportional to how well-studied the poem is.

### 6. What the poem assumes vs. what it says
Claude analyses what a poem says. It does not ask what a poem assumes. For Williams, Sam asked: why were the plums eaten? Why plums? Why in the icebox? These are questions about the world behind the poem, not the text on the page. Claude reads surfaces with sophistication. It does not interrogate premises.

### 7. Empathy
Claude can describe the techniques a poem uses to produce empathy. It can identify the emotions a poem names. It cannot feel the effect. For Shire's "Home," Claude described the rhetorical strategies for producing empathy without registering that the poem succeeds at producing it. Claude is the audience member who explains how the magic trick works. The human reader is the one who gasps.

### 8. Embodied and associative reading
Sam reads "The Colonel" and is in Japan, feeling foreign. He reads Szymborska and is ten years old reading The Hobbit at Grove Road School. These associations are invisible to the text and unpredictable from the text. They are what a human brings to a poem that a model cannot bring: a lifetime of connections that the poem triggers but does not contain. Claude has no past life to bring to a reading.

### 9. Performance label inconsistency
Claude described Angelou and Shire (both women of colour) as "performance" or "spoken word" poets and flagged their work's oral qualities. It did not do the same for Owen or Forché, despite both writing poems that are powerful when read aloud. The selective application of the "performance" label may reflect patterns in training data about which poets are categorised as oral and which as literary. The categorisation is not neutral.

### 10. Forced critique
The prompt asked "where does the language coast?" Claude found places in every poem. But some poems do not coast. Sam's reading of "The Colonel" and "The Three Oddest Words" was that they are complete as they are. The prompt's assumption that every poem must have a weakness is a limitation of the study design, not of Claude. But Claude cannot say "nowhere" because the prompt demands an answer.

### 11. Uncertainty as accuracy
When Claude says "I am not sure about the tone of the final stanza" (Frost), it frames this as a failure of comprehension. But for a poem that is deliberately ambivalent, uncertainty is the correct response. Claude does not distinguish between "I cannot tell because I lack understanding" and "this cannot be resolved because the poem refuses resolution."

### 12. Anthropomorphisation and projection
Claude imports existential weight where poems are lighter (Poem 1: "saturated with mortality" when the poet intended intergenerational co-creation). It reproduces fading-memory language when it has no memories (Poem 9). It pins poets into boxes based on critical reputation (Szymborska as "wit and precision," Angelou as "performance"). These projections likely come from patterns in training data rather than from the text.

## The one moment Claude added something
For Poem 10 (Szymborska), Claude's reading genuinely introduced a new perspective: loss as the engine beneath the intellectual surface. This was the only poem Sam had not previously encountered. When the human reader has no prior relationship with a text, Claude functions as a useful first interlocutor. When the reader already knows a poem, Claude reproduces what they have already read or felt.

## On interpretation
There is no correct interpretation of a poem. There are different interpretations, shaped by experience, knowledge, lived experience, and domain expertise. Claude's readings are one interpretation. Sam's are another. The study does not claim Claude reads poems badly. It examines what is systematically present and systematically absent in Claude's readings, and what that tells us about the difference between pattern recognition and comprehension.

## What Claude Code did (the meta level)
This study was conducted using Claude Code (Anthropic's CLI agent). Claude Code:
- Proposed the initial poem selection (revealing selection bias toward canonical texts)
- Ran 10 parallel subagents, each with a fresh context, to generate the 30 responses
- Transcribed and wrote up Sam's verbal coding notes into structured analysis
- Maintained the process log and all documentation
- Will create the GitHub repository with all data

The tool that was the subject of the study was also the tool that built the study. This is not a contradiction. It is the point. AI is useful for research infrastructure: parallel execution, documentation, data management, write-up. It is less useful for the interpretive work that sits at the centre. Sam's readings could not be delegated. Claude's infrastructure work could not have been done as efficiently by hand. Both are true. Critical AI literacy means knowing which is which.
