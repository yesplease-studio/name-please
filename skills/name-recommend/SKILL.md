---
name: name-recommend
description: >
  Entry point skill. Collects context, assesses the founder's naming situation, and routes to
  the right skill with a clear rationale. Use this when the user describes a naming problem
  but isn't sure where to start. Trigger on phrases like "help with naming", "we need a name",
  "I'm not happy with our name", "where do we start?", or similar.
system: naming
integrations:
  required: []
  optional: []
---

# Skill: name-recommend

**Purpose:** Understand the founder's naming situation and route to the right skill. Not a skill that produces an artifact -- it produces a recommendation and hands off.

---

## When to Use vs. Skip

**Use name-recommend when:**
- The user doesn't know whether they need validation, generation, or something else
- The user's first message is a general statement about a naming problem

**Skip name-recommend when:**
- The user's intent is clear: "evaluate our name" → go to name-validate; "give us alternatives" → go to name-generate
- The profile already has enough context to route directly

---

## Workflow

### Phase 1: Establish the Situation

Ask 2-3 questions to understand where they are. Don't ask all of these -- read what they've already shared and fill only the gaps:

1. Do you have a working name, or are you starting from scratch?
2. Who is the buyer -- the person who makes the purchase decision?
3. What do you already know about whether the name is working? Any specific feedback, or is it more of a gut feeling?

Have a conversation, not a form. Skip questions where the answer is obvious.

### Phase 2: Assess and Route

Based on what you've learned:

**Route to name-validate when:**
- They have a working name and want an honest read
- They're unsure about keeping or replacing
- They have feedback suggesting the name isn't landing

**Route to name-generate when:**
- They have no name and need to start from scratch
- They've already decided to replace and want options
- Note: even in this case, if a working name exists, briefly validate it first

**Route to name-generate directly when:**
- They've explicitly said the name isn't working and they want alternatives
- A validation has already been done and the verdict was Replace

### Phase 3: Explain the Route

Tell the user which skill you're recommending and why. Be specific:

> "Given that you have a working name and aren't sure whether to keep it, I'd start with name-validate -- it'll give you a clear read on where the name falls down and whether brand work can rescue it, or whether you need something different. If we get to Replace, we'll run name-generate immediately after."

Then run the skill.

---

## Notes

Keep this skill brief. The goal is to get oriented and move. Don't spend more time routing than the routing decision deserves.
