---
name: name-validate
description: >
  Evaluate an existing name against the six naming dimensions and produce a clear verdict:
  Replace, Keep with scaffolding, or Keep with execution. Always runs before name-generate
  when a working name exists -- validation gives alternatives real criteria to compete against.
  Trigger when the user says things like "is [name] a good name?", "should we keep [name]?",
  "what do you think of our name?", "I have a name, can you check it?", or "evaluate our name."
system: naming
integrations:
  required: []
  optional:
    - voice-please voice-profile.md
    - strategy-please outputs
    - prd-please ICP sections
---

# Skill: name-validate

**Purpose:** Evaluate a working name across the six naming dimensions and produce a verdict -- Replace, Keep with scaffolding, or Keep with execution. Output is `naming/name-assessment.md`.

---

## Why This Skill Exists

Most naming conversations start with "give me alternatives" but what the founder actually needs is an honest read on the name they already have. Without validation, alternatives are evaluated against sentiment. With validation, alternatives compete against real criteria.

The skill produces specificity: not "Array isn't great" but "Array fails on ICP Register because it sits in the developer tool neighborhood while your stated ICP lives in the Canva/Notion neighborhood -- and that's a translation tax on every surface." That specificity is what makes the founder ready to choose something different.

---

## When to Use vs. Skip

**Use name-validate when:**
- The user has a working name, even if they're not attached to it
- The user is asking whether to keep or replace
- About to run name-generate -- validate first, even briefly

**Skip name-validate when:**
- The user genuinely has no name at all (go to name-generate directly)
- An assessment has already been produced and the user wants to generate alternatives without re-running

---

## Workflow

### Phase 1: Confirm Context

Before evaluating, establish:

1. **The name to evaluate** -- the working name or names
2. **The ICP** -- who is the buyer? If profile.md exists, read it. If not, ask:
   - What does the company do, in plain language?
   - Who is the buyer? (Role, context, what they care about)
   - Which tools does this buyer currently use and trust? (This is the most important ICP question for naming)
   - What's the buyer's AI literacy -- do they know what "agent" means?
3. **The voice direction** -- how does the company want to sound? If voice-please artifacts exist, read them. If not: direct, warm, formal, playful, precise?
4. **The domain situation** -- what domain does the company have or is considering?
5. **Competitive context** -- who else is in the space and what are they called?

Don't ask all of these if profile.md has the answers. Fill only the gaps.

---

### Phase 2: Apply the Banned Vocabulary Filter

Before dimension scoring, apply the banned vocabulary list from `systems/naming/SYSTEM.md`.

If the name contains a banned term:
- Flag it explicitly with the category (e.g., "AI / cognition cluster" or "occupied registers")
- Note the specific reason it matters for this company's context
- This doesn't automatically produce a "Replace" verdict -- but it's strong negative signal on Dim 5

---

### Phase 3: Score the Six Dimensions

Score each dimension 1-5 using the rubric from SYSTEM.md. For each dimension, provide:

- **Score**
- **Evidence** -- what specifically about the name produces this score
- **Mechanism** -- the exact failure or success mode (don't just say "wrong register" -- say what the wrong register costs)

#### Dim 1: Strategic Signal (1-5)
Does the name communicate what matters to the buyer without explanation?

Ask: Does the name name the outcome the customer buys? Or does it name the mechanism, the category, or the internal architecture?

Watch for: names that are clever to insiders (the founding team, the technical community) but invisible to the ICP.

#### Dim 2: ICP Register (1-5)
Does the name belong in the buyer's mental neighborhood?

The test: name five tools and brands this buyer uses daily. Does the name feel like it belongs next to them -- or does it feel like it walked in from a different neighborhood?

This is often the decisive dimension. A name in the wrong register creates a translation tax that compounds across every customer touchpoint.

#### Dim 3: Voice Coherence (1-5)
Is the name coherent with the company's voice direction?

If voice artifacts exist: evaluate the name's energy, formality, and register against the defined voice profile. A warm, direct brand with a cold technical name creates dissonance.

If no voice artifacts: assess whether the name's implied personality matches the company's content direction.

#### Dim 4: Linguistic Accessibility (1-5)
Can it be said, spelled, heard, and explained by everyone who matters?

Run all four tests:
- **Say it** -- pronounceable on first try for a non-native English speaker?
- **Spell it** -- if someone hears it, can they search for it?
- **Explain it** -- can it be explained to someone outside the founder's bubble in one sentence?
- **Translate it** -- if international markets matter, does it hold up? Any accidental meanings?

#### Dim 5: Competitive Space (1-5)
Does it claim original territory and avoid overused vocabulary?

Two failure modes: too generic to be remembered; too close to an existing player. The banned vocabulary list captures the most common generic failure.

For the "too close" failure: name the specific player the name could be confused with and explain the confusion mechanism.

#### Dim 6: Operational Viability (1-5)
Can the company own it across the surfaces that matter?

Evaluate:
- Domain: is the base .com available? Does the required workaround (use- prefix, odd TLD) create brand friction?
- Trademark: any obvious conflicts in the category? (Flag for founder to verify -- not legal advice)
- Search: is the name ownable organically, or is it a generic term competing with noise?
- Confusion: could a buyer mistake the name for a competitor?

Note: for domain, always ask "would this name work with a different domain?" A weak domain can make a good name look bad.

---

### Phase 4: Produce the Verdict

Based on the dimension scores, assign one of three verdicts:

**Replace** -- when:
- Two or more dimensions score 1-2
- Either Dim 1 (Strategic Signal) or Dim 2 (ICP Register) scores 1
- The failure modes compound rather than cancel each other

**Keep with scaffolding** -- when:
- Majority of dimensions score 3+
- Specific weak spots that brand work (copy, domain, visuals) can address
- The scaffolding has a defined and manageable cost

**Keep with execution** -- when:
- The name scores well overall (majority 4-5)
- The presenting problem is under-execution: wrong domain, weak wordmark, thin copy
- The name itself doesn't need to change -- the presentation does

#### Decision framing section

After the verdict, write a "how to frame this for the founder" section. This is not in the artifact -- it's guidance for the person having the conversation. Cover:

- The strongest argument for the verdict
- The likely objection (sunk cost, personal attachment, domain cost)
- The one-sentence reframe that makes the verdict land ("The question isn't whether Array is a good name -- it's whether Array is a good name for the non-technical SMB founder you said was your ICP")

---

### Phase 5: Scaffolding Brief (if verdict is Keep)

If the verdict is Keep with scaffolding or Keep with execution, produce a specific scaffolding brief:

For **Keep with scaffolding:**
- Tagline direction (what copy needs to do that the name can't)
- Domain recommendation (if current domain is part of the problem)
- Vocabulary rules (words the company should avoid to compensate for register issues)
- Visual direction note (if the name creates tone mismatches that design should address)

For **Keep with execution:**
- Specific execution gaps (which domain, wordmark, or copy choices are letting the name down)
- Concrete next steps to close the execution gap

---

### Phase 6: Produce name-assessment.md

Write the output artifact using the template at `templates/name-assessment.md`. The structure:

1. **Context** -- who, what was asked, the ICP, what this doc is for
2. **Dimension scores** -- table with scores, evidence per dimension
3. **Verdict** -- Replace / Keep with scaffolding / Keep with execution
4. **Scaffolding brief** -- only if verdict is Keep
5. **Open questions** -- what information would change the assessment
6. **Next steps** -- what happens after this

Present the draft to the user before saving. After confirmation, save to `naming/name-assessment.md`.

If the verdict is Replace, offer to run `name-generate` immediately.

---

## Quality Standards

A good name-assessment.md:

- **Names the specific mechanism of every failure.** Not "wrong audience fit" -- "the dev-register vocabulary in Array (sits next to Vercel, Railway, Fly) creates a translation tax for a buyer who lives in the Canva/Notion neighborhood."
- **Is honest about the verdict even when the founder is attached.** The skill's job is the honest read. Softening the verdict to protect feelings produces a bad name.
- **Costs the scaffolding.** If recommending Keep with scaffolding, make the permanent tax visible.
- **Includes open questions.** A good assessment knows what it doesn't know. "If the founder discovers array.com is available, this assessment changes -- here's how."
- **Ends with a clear next step.** Replace → offer to run name-generate. Keep → specify exactly what the founder should do next.
