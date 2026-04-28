# Setup Guide

This guide walks you through creating a company profile so name-please can give you grounded naming work. Claude follows this flow during your first conversation.

The whole process takes 5-10 minutes.

---

## How onboarding works

### Step 1: Check for existing context

Ask the user:

> "Do you have any existing company or product documents you can share? A pitch deck, a one-pager, a website, or a brief description of what you're building and who it's for?"

If they provide something:
- Read and extract: what the company does, who the buyer is, what stage they're at, any voice direction
- Note what's covered and what's missing
- Move to Step 2 to fill gaps

If they provide a URL, use WebFetch to retrieve and read it.

If they don't have anything, move straight to Step 2.

### Step 2: Fill gaps conversationally

Based on what's missing from Step 1, ask about:

**What they're building and for whom**
- What does the company (or product) do, in plain language?
- Who is the buyer -- the person who actually makes the purchase decision?
- Which tools is that buyer using every day?
- What's their AI literacy -- would they know what "agent" means?

**The naming situation**
- Do you have a working name?
- How did the name come about?
- Is there any feedback you've heard about it -- from customers, advisors, investors?
- What's the domain situation?

**Voice direction**
- How do you want the company to sound? (A few words, or a reference brand whose tone resonates)
- Who do you definitely NOT want to sound like?

**Competitive landscape**
- Who else is in the space? What are the main competitors called?
- Any vocabulary in your category that feels already used up?

Don't ask all of these as a list. Have a conversation. Skip questions where the answer is already clear from Step 1. Follow up on interesting answers.

### Step 3: Write the profile

Once you have enough context, generate `config/profile.md` using the template from `config/_template.md`.

Before saving:
1. Show the user the complete profile
2. Ask if anything needs adjusting
3. Save only after confirmation

A useful profile beats a complete one. Mark missing fields as "Unknown" or "Not discussed" rather than guessing. The most important fields are: what the company does, who the buyer is, what tools the buyer uses, and what the working name (if any) is.

### Step 4: Route to the right skill

After the profile is saved:

- **If they have a working name:** Suggest running `name-validate` first. "Let me give you an honest read on [name] against your buyer before we look at alternatives."
- **If they want to validate and potentially replace:** "We'll validate first, then generate alternatives if the assessment says to replace."
- **If they have no name at all:** Go directly to `name-generate`.
- **If they're not sure where to start:** Run `name-recommend` to orient.

---

## Notes for Claude

- The ICP is the most important thing to get right. Naming in an ICP vacuum is astrology. If the buyer is vague, press for specifics -- not "small businesses" but "non-technical founders running Lovable who've never written a line of code."
- The three discovery questions (which tools do they use, which adjacent tools, what's their AI literacy) are worth asking even when the profile has an ICP section. They sharpen it.
- If the user clearly knows what they want and doesn't need a profile, skip onboarding and go straight to the skill.
- Keep the conversation natural. This is getting-to-know-you, not a form.
