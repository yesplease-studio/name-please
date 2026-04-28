---
name: name-generate
description: >
  Generate grounded naming alternatives by committing to naming registers from the company's
  own context before producing candidates. Generates two parallel tracks (semantic and coined),
  merges into a ranked shortlist of 3 finalists + 1 backup + cut list, and delivers a clear
  recommendation. Trigger when the user says things like "give me alternatives", "we need new
  name options", "come up with something", or when name-validate returns a Replace verdict.
  Always run name-validate first when a working name exists.
system: naming
integrations:
  required: []
  optional:
    - voice-please voice-profile.md
    - strategy-please outputs
    - prd-please ICP sections
    - naming/name-assessment.md
---

# Skill: name-generate

**Purpose:** Generate naming alternatives grounded in the company's ICP, voice direction, and competitive context. Produce a ranked shortlist with per-candidate analysis, a cut list, and a single clear recommendation. Output is `naming/name-candidates.md`.

---

## Why This Skill Exists

Ungrounded brainstorming produces predictable output: a list of generic, stock-vocabulary names that could have come from anywhere. name-generate works differently -- it commits to registers before generating, forces each candidate through copy-testing and dimension scoring, and ends with a recommendation rather than a list.

The canonical failure mode: thirty names, no criteria, evaluated by gut feel, chosen by sentiment. This skill eliminates that failure by making the criteria explicit before any name is written.

---

## When to Use vs. Skip

**Use name-generate when:**
- name-validate returned a Replace verdict
- The user has no existing name and needs to start from scratch
- The user explicitly wants alternatives (but still run brief validation first if a working name exists)

**Skip name-generate when:**
- The validation verdict is Keep -- the name isn't the problem
- A complete candidates doc already exists and the user wants to review rather than regenerate

---

## Workflow

### Phase 1: Confirm Context

Read `config/profile.md`. If a name-assessment.md exists, read it -- the dimension failure modes are direct inputs to the register selection.

Confirm:
1. **The ICP** -- who is the buyer? Role, context, the three discovery questions (tools they use, adjacent tools, AI literacy)
2. **The voice direction** -- if voice artifacts exist, read them; if not, get a working sense of the tone and register the company is building
3. **Competitive landscape** -- what names exist in the space? What's the vocabulary the category has already used up?
4. **The failure modes from validation** -- if assessment exists, which dimensions failed? What specifically should the alternatives avoid?
5. **Narrative context** -- does the founder have prior work, a previous company, a metaphor they use consistently? Narrative continuity is free brand equity.

Ask only what's missing. Don't re-interview if the profile covers it.

---

### Phase 2: Commit to Naming Registers

Before writing a single name, extract and commit to 3-5 naming registers grounded in the founder's own words.

Source material for registers:
- Their metaphor for what the product does ("it's like having a team behind you")
- Their value proposition (the outcome, not the mechanism)
- Their promise to the buyer ("you ship faster, you look better")
- Their visual brief or emotional goal ("warm, handmade, not dev-ops")
- Adjacent category vocabulary the ICP already trusts (if the ICP uses Notion/Linear, they're comfortable with precise, calm brand names)

**Format for each register:**

```
Register: [Name]
Grounded in: [The founder's exact phrase or context that justifies this register]
What names in this register feel like: [Energy, tone, example real-world companies that live here]
Examples of the type: [2-3 words that capture the register, not necessarily name candidates yet]
```

Present the registers to the user and confirm before generating names. If a register doesn't feel right to the founder, replace it. The registers are the quality gate -- time spent here saves time in the shortlist.

---

### Phase 3: Generate in Two Tracks

Generate candidates in two parallel tracks: **semantic** and **coined**.

#### Track A: Semantic names

Semantic names carry meaning. They do explaining work upfront. They need less brand scaffolding but are harder to own (trademark, domain) and less distinctive.

Generate 3-5 candidates per register. For each:
- The name
- The register it came from
- What it communicates directly to the buyer

The best semantic candidates feel inevitable -- the buyer reads the name and immediately understands what the company is promising.

#### Track B: Coined names

Coined names are made or adapted. They require the brand to build meaning from scratch, but they're easier to own legally, often more international, and can be more distinctive.

Apply the craft rules from SYSTEM.md:
- Two syllables preferred; sometimes three; rarely more
- Open vowels (a, e, i, o) over closed ones; avoid clusters of hard consonants
- Soft endings (-a, -o, -ia, -ora, -en) land better than hard ones (-k, -x, -t)
- Every candidate must be sayable by a non-native English speaker on first try
- Avoid X/Z/K unless the sound is genuinely natural
- Whisper of meaning is optional -- pure sound candidates earn their place on phonetics alone

Generate 3-5 coined candidates. For each:
- The name
- Phonetic quality notes (why it works sonically)
- Optional meaning or resonance (if any)

---

### Phase 4: Apply Filters

Before moving to shortlist, run every candidate through:

**1. Banned vocabulary filter**
Any name matching the banned vocabulary list in SYSTEM.md is cut unless there is a specific, compelling reason. Name the reason or cut the candidate.

**2. Dimension pre-check**
Quick assessment against the six dimensions. Candidates that fail on ICP Register (Dim 2) or Strategic Signal (Dim 1) should be cut before the shortlist unless they're significantly stronger on every other dimension.

**3. Copy test**
For every surviving candidate: draft a one-line tagline or copy snippet using the name. If a clean line can't be written in ten seconds, the name isn't doing work -- cut it.

Format: `"[Tagline that uses the name]"` followed by a one-sentence note on whether it works.

---

### Phase 5: Build the Shortlist

Merge Track A and Track B into a single final shortlist. Target: **3 finalists + 1 backup**.

A good shortlist is mixed: not all semantic or all coined, not all from the same register.

**Per-candidate format:**

```
## [Name]

**Type:** Semantic / Coined
**Register:** [Which register this came from]

**Why it works:** [The specific case for this candidate -- what it communicates, how it lands with the ICP, what it does for the brand]

**Copy example:** "[One-line tagline or sentence using the name]"

**Risks:** [Specific failure modes -- what this name costs, where it's weak]

**Domain signal:** [What domain situation looks like -- note if founder should verify availability]

**Verdict:** Finalist / Backup
```

**The cut list:**

After the finalists, include a table of candidates that were generated and cut:

| Name | Track | Cut reason |
|------|-------|------------|
| [Name] | Semantic | [One-line reason] |

The cut list shows the space was explored and gives the founder confidence the shortlist is the best of the generation, not just a random sample.

---

### Phase 6: Ask for Gut Feel

Before delivering the final recommendation, present the shortlist and explicitly ask for the founder's gut reaction:

> "Before I recommend one -- what's your immediate gut response to these? First instinct, before the analysis."

Document the response. A strong gut negative on an analytically strong candidate is a real signal and should influence the recommendation. A gut positive on the backup can move it up. Protect the signal -- don't argue the founder out of it unless the analysis has very specific evidence.

---

### Phase 7: Deliver the Recommendation

After gut feel is gathered, deliver the recommendation:

**Format:**
1. The recommendation -- name the one, and say why
2. The runner-up -- and why it's second
3. Dependencies -- what information would change the ranking (domain availability being the most common)
4. Next steps

This is a recommendation, not a neutral ranking. Be direct. The founder asked for help deciding, not for more options.

---

### Phase 8: Produce name-candidates.md

Write the output artifact using the template at `templates/name-candidates.md`. The structure:

1. **Context** -- company, ICP, what validation found (if applicable), what this engagement was for
2. **Naming registers** -- the 3-5 registers and their grounding
3. **Finalists** -- 3 finalists with full per-candidate analysis
4. **Backup** -- 1 backup with briefer analysis
5. **Cut list** -- table format
6. **Recommendation** -- clear, single, defensible, with rationale
7. **Dependencies** -- what would change the ranking
8. **Next steps** -- handoff to voice-please, design-please, or the relevant domain/trademark work

Present the draft to the user before saving. After confirmation, save to `naming/name-candidates.md`.

---

## Quality Standards

A good name-candidates.md:

- **Every finalist includes a copy example.** Not optional. If the copy is weak, the candidate is weak.
- **The cut list is as long as the shortlist.** More cuts signal more rigorous generation; fewer cuts signal the space wasn't explored.
- **The recommendation is explicit.** Not "Cadence and Chorus both have merit" -- "Lead with Cadence. Here's why."
- **The gut-feel checkpoint is documented.** Whatever the founder said is in the artifact, because it will matter when they revisit this in three months.
- **Dependencies are named.** "This ranking changes if array.com is available" is more useful than "check domain availability."
- **The semantic and coined tracks are both represented.** A all-semantic or all-coined shortlist is incomplete.
