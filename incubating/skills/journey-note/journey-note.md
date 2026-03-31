Generate a journey session summary as a narrative memo capturing the intellectual arc of this working session.

## Output Location

Save to the journey notes directory for this project. Check for existing notes in these locations (in order): `docs/journey-notes/`, `journey-notes/`, `docs/`. Use whichever exists, or default to `docs/journey-notes/` and create it.

If a note already exists for today (`YYYY-MM-DD-*.md`), ask the user: append to the existing note or create a new one with a different slug?

Filename: `YYYY-MM-DD-[title-slug].md`

## Required Structure

### Header
```markdown
# Session Memo: [Evocative Title Capturing the Journey]

**Date:** YYYY-MM-DD
**Project:** [repo/project name]
**Branch:** `branch-name`
**Commits:** N across session
```

### The Journey
Opening paragraph setting the scene. Where did we start? What was the initial ask? Then: "But this session took an unexpected path..."

### Acts (3-6 acts typical)
Each act represents a major inflection point or realization:

```markdown
### Act I: [Evocative Act Title]

[Narrative of what happened, including key quotes from the user if memorable]

**Key insight:** [One-sentence crystallization of what was learned]
```

Acts should show progression—each builds on the previous. Look for:
- Moments where the conversation pivoted
- Questions that changed the direction
- Realizations that unlocked new understanding
- External references that reshaped thinking

### The Arc
A one-line visualization of the session's trajectory:

```markdown
## The Arc

```
Starting point → Inflection 1 → Inflection 2 → ... → Ending insight
```
```

### Artifacts Created
Table of documents created or modified:

```markdown
## Artifacts Created

| Document | Purpose |
|----------|---------|
| `path/to/file.md` | Brief description |
```

### The Thesis, Refined
Blockquote capturing the refined understanding:

```markdown
## The Thesis, Refined

> **[Core insight in bold.]** [Elaboration in regular text.]
```

### Closing
A memorable sign-off line, often a callback or quote from the session.

### Session Ledger

After the narrative, append a semantically dense, machine-optimized accounting of the session. No prose. No filler. Every token carries signal.

```markdown
## Session Ledger

**Intent:** [One sentence. Why did this session happen?]

**Decisions:**
- [DECIDED] [precise statement of what was chosen and why, in fewest words]
- [DECIDED] ...

**Discoveries:**
- [FOUND] [thing learned that wasn't known before — include specifics]
- [FOUND] ...

**Actions:**
- [CREATED|MODIFIED|DELETED] `path/to/file` — [what and why, <10 words]
- ...

**State Change:**
- [BEFORE] [project state entering session]
- [AFTER] [project state exiting session]

**Open Threads:**
- [NEXT] [concrete next action with enough context to resume cold]
- [BLOCKED] [anything waiting on external input]
- [QUESTION] [unresolved question surfaced during session]

**Dependencies Introduced:**
- [DEP] [any new tool, service, assumption, or external dependency added]

**Tags:** [3-7 semantic tags for retrieval, e.g. `#architecture`, `#data-pipeline`, `#api-design`]
```

Rules for the Session Ledger:
- **Semantic density**: Every line must be self-contained and meaningful without the narrative above
- **Resumability**: Someone reading only the ledger should be able to pick up work tomorrow
- **Precision over completeness**: Omit rather than be vague
- **Stable vocabulary**: Use DECIDED/FOUND/CREATED/MODIFIED/DELETED/NEXT/BLOCKED/QUESTION/DEP consistently
- **No duplication**: Don't repeat the Artifacts table — the ledger captures intent and state, artifacts captures files

---

## Tone Guidelines

- **Narrative, not procedural**: "Then the question that changed everything" not "User asked about X"
- **Show intellectual progression**: The reader should feel the journey
- **Quote memorable user phrases**: These become blog gold
- **Name the insights**: Each act ends with a crystallized learning
- **Arc as map**: Someone should understand the session from the arc alone
- **Project-agnostic**: This skill works across any repo — adapt language to the project's domain

## Anti-patterns

- Don't list tasks completed (that's a status note)
- Don't focus on implementation details over ideas
- Don't enumerate commits or PRs
- Don't be dry or clinical
- Don't skip the "why" for the "what"

---

Now generate the journey note based on this session's full conversation history.
