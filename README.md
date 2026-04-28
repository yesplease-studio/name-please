# name-please

An open-source, AI-native framework for validating and generating company and product names.

Takes vision, ICP, voice direction, and competitive context as raw material. Evaluates names across six dimensions, delivers a clear verdict (replace, keep with scaffolding, or keep with execution), and generates grounded alternatives when needed. Built to be used with [Claude Code](https://claude.ai/code).

Part of the [please family](https://github.com/yesplease-studio) of open-source frameworks from [Yes Please Studio](https://yesplease.studio).

---

## How it works

Most naming processes produce a shopping list: thirty options with no criteria, evaluated by gut feel, chosen by sentiment. name-please works differently.

The framework has a strong opinion: **naming is a strategic act, not a creative sprint.** A good name lands the company's vision into the emotional register of its ICP. A bad name forces the brand to constantly explain itself. The gap in the market isn't more name ideas -- it's a workflow that pulls in vision, positioning, ICP, and voice context to evaluate and generate names that actually work for a specific company and audience.

Three phases:

1. **Validate.** Nine times out of ten, the founder already has a name and needs an honest read. name-validate evaluates the working name across six dimensions and delivers a verdict: Replace, Keep with scaffolding, or Keep with execution.

2. **Generate.** When validation reveals problems (or when starting without a name), name-generate commits to naming registers grounded in the founder's own words before producing a single candidate. Two parallel tracks -- semantic and coined -- merge into a shortlist of three finalists, a backup, and a cut list.

3. **Recommend.** The output is a clear recommendation, not a neutral ranking. Name which one, and say why.

## Who this is for

- **Founders** who have a working name and want an honest read before they commit to it
- **Founders starting from scratch** who want structured generation rather than a brainstorm
- **Consultants and advisors** who help companies with naming and want a repeatable framework
- **Anyone who's gotten burned by generic AI naming output** and wants something grounded in real buyer context

## Quickstart

1. Open this repo in [Claude Code](https://claude.ai/code)
2. Claude will detect `CLAUDE.md.template` and load the system
3. Say **"help me with naming"** or **"is [name] the right name for us?"** and Claude will orient
4. If this is your first time, Claude will walk you through creating a company profile

Or skip setup and go straight to a skill: **"validate [name] for a [buyer type] audience"**

## The six dimensions

name-please evaluates every name across six dimensions. Each answers a core question.

| # | Dimension | Core question |
|---|-----------|--------------|
| 1 | Strategic Signal | Does the name communicate what matters to the buyer without explanation? |
| 2 | ICP Register | Does the name belong in the buyer's mental neighborhood? |
| 3 | Voice Coherence | Is the name coherent with how the company sounds and wants to sound? |
| 4 | Linguistic Accessibility | Can it be said, spelled, heard, and explained by everyone who matters? |
| 5 | Competitive Space | Does it claim original territory and avoid overused vocabulary? |
| 6 | Operational Viability | Can the company own it across the surfaces that matter? |

Scores run 1-5. A score of 1 or 2 on Dim 1 or Dim 2 is almost always a Replace.

## Skills

| Skill | What it does | When to use |
|-------|-------------|-------------|
| `name-recommend` | Routes the engagement based on what the founder has | "Where do we start?" |
| `name-validate` | Evaluates a working name across the six dimensions | "Is [name] the right choice?" |
| `name-generate` | Generates grounded alternatives with a ranked shortlist | After a Replace verdict, or starting from scratch |

## Naming artifacts

Skills produce structured artifacts that live in `naming/`:

| Artifact | What it contains |
|----------|-----------------|
| `naming-brief.md` | Context: company, ICP, voice direction, competitive landscape, current name situation |
| `name-assessment.md` | Validation output: dimension scores, verdict, scaffolding brief if keeping |
| `name-candidates.md` | Generation output: registers, shortlist, cut list, gut-feel checkpoint, recommendation |

## The three verdicts

Every validation ends in one of three verdicts:

| Verdict | Meaning |
|---------|---------|
| **Replace** | The name fails on multiple axes and brand work can't close the gap |
| **Keep with scaffolding** | The name works but needs copy, domain, or visual fixes |
| **Keep with execution** | The name is fine; the problem is under-execution, not the name |

Scaffolding has a permanent cost. Every new surface pays the tax. Always cost the scaffolding before recommending keep.

## Opinionated principles

name-please enforces a set of principles that emerged from real naming work:

- **Validate first, generate second.** Even when the founder asks for alternatives directly.
- **Evaluate against the buyer, not in general.** "Is this a good name for the non-technical SMB founder you said was your ICP?"
- **Commit to registers before generating.** 3-5 naming registers grounded in the founder's own words before a single candidate is written.
- **Generate semantic and coined names in parallel.** A shortlist with only one type is incomplete.
- **Three finalists, not thirty.** Founders don't commit to shopping lists.
- **Copy-test every candidate.** If a clean line can't be written in ten seconds, the candidate is cut.
- **Ask for gut feel before final verdict.** Gut feel captures whether the founder can live with a name long enough to make it real.
- **Recommend, don't report.** Name which one, and say why.
- **Domain is part of the naming decision.** A great name with a broken domain is a broken name.

## Directory structure

```
name-please/
├── CLAUDE.md.template     # How Claude operates in this system
├── SETUP.md               # Onboarding flow
├── README.md              # This file
├── config/
│   └── _template.md       # Company profile template
├── systems/
│   └── naming/
│       └── SYSTEM.md      # Core methodology (dimensions, principles, banned vocabulary)
├── skills/
│   ├── name-recommend/    # Entry point and routing
│   ├── name-validate/     # Name evaluation
│   └── name-generate/     # Alternative generation
├── templates/             # Output artifact templates
│   ├── naming-brief.md
│   ├── name-assessment.md
│   └── name-candidates.md
├── workflows/             # Composed skill sequences
│   ├── new-name.yaml      # Full: validate → generate if needed
│   └── validate-only.yaml # Just evaluate the working name
├── tracking/              # Effectiveness tracking
└── examples/              # Walkthroughs
```

## The please family

name-please is one of six open-source frameworks from Yes Please Studio:

| Framework | What it does | Core question |
|-----------|-------------|---------------|
| [strategy-please](https://github.com/yesplease-studio/strategy-please) | Strategic workshop recommendation engine | "Where should we focus?" |
| [prd-please](https://github.com/yesplease-studio/prd-please) | Product requirements authoring and validation | "How do we build it reliably?" |
| [sales-please](https://github.com/yesplease-studio/sales-please) | Deal qualification and pipeline management | "Is this deal worth pursuing?" |
| [voice-please](https://github.com/yesplease-studio/voice-please) | Voice system definition and encoding | "What should we sound like?" |
| [design-please](https://github.com/yesplease-studio/design-please) | Design direction and encoding | "What should it look, feel, and act like?" |
| **name-please** | Name validation and generation | "Is this the right name?" |

name-please integrates tightly with voice-please (voice direction is a direct input to naming) and hands off naturally to design-please (name and visual identity should be developed together).

## Self-serve vs. facilitated

Every skill in name-please produces useful output when run independently. You don't need a consultant to use this.

That said, the ICP Register dimension (Dim 2) and the gut-feel checkpoint benefit significantly from having an experienced naming practitioner in the room. The framework is honest about this: `systems/naming/SYSTEM.md` documents where facilitation adds the most value.

## License

MIT
