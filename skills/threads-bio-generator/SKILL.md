---
name: threads-bio-generator
description: Write Threads bio options (150 characters) that say who the account is and why to follow, for a person or brand profile. Use when the user asks for a Threads bio, Threads bio ideas, or to rewrite their Threads profile text.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# Threads bio generator

Write profile text the user pastes into Threads themselves. This MCP publishes posts; it doesn't edit profiles.

## Before writing

Get or infer: who the account is, what they post about, who should follow, what makes their take different, and whether there's a link to point to. Threads profiles are often linked to Instagram, so ask if the user wants the Threads bio to match their Instagram bio or to sound more conversational. Never invent credentials or numbers.

## How to write it

The bio limit is 150 characters. Use it for three things:
- What you post about, in plain words: "Notes on building a bakery from scratch."
- Why listen: a real credential, a point of view or where you are in the journey.
- Optional next step: "DMs open for collabs", "newsletter ↓", or a pointer to the link.

Rules:
- Threads is conversational, so the bio can be too. First person is fine.
- Topics beat titles: "writing about pricing and churn" says more than "SaaS founder".
- One or two emojis at most, only if the user uses them.
- No hashtags, no buzzwords ("passionate", "visionary", "thought leader").
- Don't cram in every role and interest. Pick what a new follower needs to decide.

## Examples of the shape

| Direction | Example |
| --- | --- |
| Plain and clear | "Building a bakery in public. Pricing, hiring, and what broke this week." |
| Personality-led | "Ex-lawyer, now baking bread for a living. Mostly honest about it." |
| Topic-led | "Small business money: pricing, margins, cash flow. Real numbers from my shop." |

Use these for shape only; write the user's own.

## Output

Give 3 options in different directions (plain and clear, personality-led, topic-led), each with its character count, and mark the one you'd pick in one line. Tell the user to paste it in the Threads app under Edit profile. If they want an intro post to go with a new bio, write it with the `threads-post-writer` skill and offer to publish it with the `postonce` skill.
