# Naming System

A methodology for evaluating and generating company, product, and project names. Treats naming as a strategic act: a name either does work for the buyer or forces the brand to constantly explain itself. Humans provide judgment, taste, and approval. AI handles analysis, structure, and candidate generation.

---

## 1. Core Concepts

### 1.1 What the System Does

Most naming processes produce a shopping list: thirty options with no criteria, evaluated by gut feel, chosen by sentiment. The result is a name the founder likes rather than a name the buyer trusts.

The naming system inverts this. It:

1. **Locks in context first.** Vision, ICP, voice direction, and competitive landscape before a single name is evaluated or generated.
2. **Validates what exists.** Most founders already have a working name and want an honest read before they consider alternatives.
3. **Generates against criteria.** Alternatives are grounded in the company's own words and constrained by the six dimensions. Not a brainstorm -- a structured search.
4. **Recommends, not reports.** The output is a clear verdict and a single recommendation, not a neutral list the founder has to sort through themselves.

### 1.2 The Three Skills

| Skill | Role | When used |
|-------|------|-----------|
| `name-recommend` | Routes the engagement based on what the founder has and what they need | Entry point when the path isn't clear |
| `name-validate` | Evaluates an existing name across the six dimensions | When the founder has a working name and needs an honest assessment |
| `name-generate` | Generates ranked alternatives grounded in company context | After validation reveals problems, or when starting without a name |

Skills are invoked independently. A typical engagement runs validate → generate (if needed). A founder without any name goes directly to generate.

### 1.3 The Three Verdicts

Every engagement with an existing name ends in one of three verdicts:

| Verdict | Meaning | When to recommend |
|---------|---------|-------------------|
| **Replace** | The name fails on multiple axes and scaffolding cannot close the gap | Two or more dimension scores of 1-2, especially Strategic Signal or ICP Register |
| **Keep with scaffolding** | The name works but needs brand work to compensate for specific weaknesses | Clear strengths on 3+ dimensions, but weak spots that copy, domain, or visuals can address |
| **Keep with execution** | The name is fine; the problem is under-execution, not the name itself | Name scores well but presentation (domain, wordmark, copy) is letting it down |

Scaffolding has a permanent cost. If every new surface has to do translation work the name can't do on its own, the tax compounds. Always cost the scaffolding before recommending keep.

---

## 2. The Six Dimensions

Naming quality is assessed across six dimensions. Each dimension answers a core question. Scores are 1-5.

| # | Dimension | Core question |
|---|-----------|--------------|
| 1 | Strategic Signal | Does the name communicate what matters to the buyer without explanation? |
| 2 | ICP Register | Does the name belong in the buyer's mental neighborhood? |
| 3 | Voice Coherence | Is the name coherent with how the company sounds and wants to sound? |
| 4 | Linguistic Accessibility | Can it be said, spelled, heard, and explained by everyone who matters? |
| 5 | Competitive Space | Does it claim original territory and avoid overused vocabulary? |
| 6 | Operational Viability | Can the company own it across the surfaces that matter? |

### Scoring

| Score | Meaning |
|-------|---------|
| **5** | Actively works for the brand on this dimension -- adds value beyond neutrality |
| **4** | Strong; no meaningful friction or cost |
| **3** | Mixed or neutral; brand scaffolding can compensate |
| **2** | Creates friction; brand must actively work against it |
| **1** | Active liability; cannot be remedied without changing the name |

### 2.1 Dimension Descriptions

**Dim 1: Strategic Signal**

Does the name do work for the brand by signaling what matters to the buyer? A name that names the outcome the customer buys beats a name that describes how the mechanism works internally.

The key distinction: naming after internal architecture (what you built), naming after the category (what the space is called), or naming for the buyer's experience (what they get). The third is almost always strongest.

Watch for: names that are clever to insiders but invisible to the ICP. Cleverness is only an asset when the buyer is positioned to appreciate it.

**Dim 2: ICP Register**

Names live in neighborhoods. "Array," "Vercel," "Fly" belong in one neighborhood; "Canva," "Notion," "Linear" belong in another. The ICP has a mental neighborhood built from the tools, brands, and language they already use -- and the name either fits that neighborhood or it doesn't.

A name can be objectively good and wrong for a specific buyer. Evaluate the name against the stated ICP, not in the abstract.

Key discovery questions:
- Which tools are this buyer's defaults today?
- What adjacent tools do they use (Canva, Figma, Notion, Jira)?
- What's their AI literacy? Do they know what "agent" means?

**Dim 3: Voice Coherence**

A name is a brand's first word. If the brand is warm and direct, a cold technical name creates dissonance on every surface where the two appear together. If voice work exists (from voice-please or equivalent), use it as a direct input.

Without voice artifacts: evaluate whether the name's energy, formality, and register match the company's content direction.

**Dim 4: Linguistic Accessibility**

A name that fails in audio is broken regardless of how it looks in a deck. Test:
- **Say it.** Is it pronounceable on first try for a non-native English speaker?
- **Spell it.** If someone hears the name, can they find it?
- **Explain it.** Can a founder explain it to someone's mom in one sentence?
- **Translate it.** If international markets matter, does the name hold up? Does it accidentally mean something in a key market's language?

**Dim 5: Competitive Space**

Two failure modes: (1) too generic to be remembered, (2) too similar to an existing player in the space. Both are avoidable.

The banned vocabulary list (see Section 4) captures the most common failure mode: using AI/tech default vocabulary that positions the company inside an already-crowded cluster of names. Avoid these unless there is a very specific reason.

**Dim 6: Operational Viability**

Domain and trademark are part of the name, not packaging applied after. A great name with a broken domain is a broken name.

Evaluate:
- **Domain:** Is the base .com (or context-appropriate TLD) available or achievable? Does the required workaround (use-, get-, try- prefix; odd TLD) create brand friction?
- **Trademark:** Are there obvious conflicts in the company's category? (Flag for founder to verify -- not legal advice.)
- **Search:** Is the name ownable in organic search, or is it a generic term that will always compete with noise?
- **Confusion:** Could a buyer mistake the name for a competitor or adjacent tool?

---

## 3. Opinionated Principles

These are the working rules the system enforces. Each emerged from real naming work -- they're not theoretical.

### 3.1 Validate before generating

Founders reaching out for naming help almost always already have a working name they're attached to. If you skip validation and go straight to alternatives, you produce a list they compare against sentiment. Validate first: it gives alternatives real criteria to compete against, and it gives the founder permission to move on.

### 3.2 Evaluate against the buyer, not in general

Every naming question resolves to: "Is this a good name **for the buyer we're chasing**?" That reframe takes the judgment off the founder's taste and puts it on their stated strategy. A name can be objectively fine and wrong for a specific ICP. Never evaluate in isolation.

### 3.3 Commit to registers before generating

Instead of brainstorming 30 names, commit to 3-5 naming registers grounded in the founder's own words (their metaphor, their value prop, their promise, their emotional goal). Generate within each register. Ungrounded generation produces predictable output. Register-constrained generation produces candidates that feel like they came from the company's actual thinking.

### 3.4 Generate semantic and coined names in parallel

Semantic names (Cadence, Chorus, Current) do explaining work upfront and need less scaffolding. Coined names (Vela, Finora, Aerin) are harder to own conceptually but easier to own legally, and often more international. A shortlist with only one type is incomplete. Produce both and merge.

Craft rules for coined names:
- Two syllables preferred; sometimes three; rarely more
- Open vowels (a, e, i, o) over closed; avoid clusters of hard consonants
- Soft endings (-a, -o, -ia, -ora, -en) land better than hard ones (-k, -x, -t)
- Every candidate must be sayable by a non-native English speaker on first try
- Avoid X/Z/K unless the sound is genuinely natural -- stylized consonants read as try-hard
- Whisper of meaning is optional; pure sound candidates earn their place on phonetics alone

### 3.5 Three finalists, not thirty

More than three finalists becomes a shopping list. Founders don't commit to shopping lists. Cut aggressively to a small set with real per-candidate reasoning, and name the cuts. The cut list is as valuable as the shortlist -- it shows the space was explored.

**Deliverable format:** 3 finalists + 1 backup + a brief cut list. Every finalist gets full analysis. Every cut gets a one-line reason.

### 3.6 Copy-test every candidate

For every candidate, draft a one-line tagline or copy snippet using the name. If a clean line can't be written in under ten seconds, the name isn't doing work. Candidates that write their own copy are candidates worth keeping.

### 3.7 Ask for gut feel before final verdict

After presenting the shortlist, ask for the founder's gut reaction before analysis gets the final word. Gut feel captures what analysis doesn't: whether the founder can live with a name long enough to make it real. A strong gut negative on an analytically good name is a real signal.

### 3.8 Recommend, don't report

The output is a recommendation, not a neutral ranking. Name which one, and say why. A ranked shortlist without a recommendation is a tax on the founder.

### 3.9 Domain is part of the naming decision

The domain is not packaging. A name with an unavailable .com and a use- workaround is a weaker name. When evaluating a working name, always ask: "Would this name work with a different domain?" -- because sometimes the issue is the domain, not the name.

Three outcomes: Replace / Keep with scaffolding / Keep with execution. Present all three as possible verdicts.

### 3.10 Brand scaffolding is a permanent tax

Yes, a weak name can be rescued by a great tagline, an above-the-fold explainer, and disciplined vocabulary. But every new surface pays that tax. Always cost the scaffolding. A better name removes the tax permanently.

---

## 4. Banned Vocabulary

Names containing these words or patterns are rejected before evaluation begins unless there is a specific, compelling reason. These are the stock vocabulary of AI-era startups; using them makes differentiation impossible.

### AI / cognition cluster
AI, OS, Autonomous, Agentic, Intelligence, Brain, Mind, Sense, Cognitive, Neural, Synapse, Cortex, Logic, Reason

### Generic SaaS structure words
Core, Hub, Center, Platform, Framework, Stack, Suite, Engine, Solution, System

### "We make things" suffixes
Labs, Works, Factory, Forge (close call -- allowed if there's a specific reason), Studio (allowed for creative-facing brands)

### Overused tempo / connection words
Flow, Pulse, Sync, Link, Loop, Stream, Signal, Connect, Bridge

### Occupied registers
Pilot, Copilot, Navigator, Commander (GitHub Copilot has consumed this entire register)

### Domain patterns that signal "couldn't get the base"
`use-` prefix, `get-` prefix, `try-` prefix on the base domain. The .dev TLD for non-developer audiences.

---

## 5. Discovery Questions

These questions sharpen the ICP in ways the founder's self-description usually doesn't. Ask all three before generating alternatives.

**1. "Which tools are your ideal customers using today, and which have they tried and turned away from?"**
Separates vague "non-technical" from "Lovable refugee" vs. "Vercel refugee." The answer changes which names land.

**2. "What adjacent tools do your ideal customers use -- Canva, Figma, Miro, Notion, or Jira, Salesforce, SAP?"**
This tells you which brand aesthetics the customer is comfortable with. Canva/Figma/Linear buyers respond to crafted, human brands. Jira/Confluence/SAP buyers respond to structured, enterprise brands. The naming register has to match the aesthetic neighborhood.

**3. "What's your ideal customer's AI literacy? When they hear the word 'agent,' do they know what it means?"**
Decisive for AI-native startups. "Non-technical" can mean anything from "never used ChatGPT" to "uses Claude daily but can't code." The vocabulary load in the name has to match. If AI literacy is low, the name cannot contain or imply agents, orchestration, pipelines.

---

## 6. Integrations

### voice-please
The tightest integration. If voice-please artifacts exist for a company (voice-profile.md, conventions.md), they are direct inputs to name-please. The name's tone, energy, and register are evaluated against the voice system. The name should feel like it was chosen by the company voice-please describes.

When voice-please work is complete and the company is ready to name: run name-validate or name-generate with the voice artifacts in context.

### strategy-please
Naming in an ICP vacuum is astrology. If the company hasn't done ICP and positioning work, naming should wait -- or the naming engagement should start with enough discovery to establish a working ICP. strategy-please provides that context.

### prd-please
When naming a product (not the company), the PRD's audience and positioning sections are direct inputs. Product names are evaluated against the PRD's defined buyer and use case.

---

## 7. File conventions

### naming-brief.md
The context document that any skill can consume. Created during intake or collected from existing company documents. Lives at the project level.

### name-assessment.md
Output of name-validate. The analysis of the working name: dimension scores, verdict, scaffolding brief if keeping.

### name-candidates.md
Output of name-generate. The shortlist with per-candidate analysis, cut list, and recommendation.
