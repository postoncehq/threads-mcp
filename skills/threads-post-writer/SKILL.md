---
name: threads-post-writer
description: Write Threads posts (up to 500 characters, text, images, video or carousel) that sound conversational and get replies, ready to publish with the PostOnce Threads MCP. Use when the user asks to write a Threads post, Threads ideas, something to post on Threads, or to turn an update, opinion, article or notes into a Threads post.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# Threads post writer

Write one Threads post that reads like a person talking, then hand it to the `postonce` skill if the user wants it published or scheduled.

## Before writing

Get or infer: who's posting (person or brand), who they want to talk to, the one idea or opinion, and any real detail that makes it specific. If the source is long, pick one idea. Never invent numbers, customers or quotes.

## What works on Threads

Threads rewards conversation. Posts that start replies travel further than posts that broadcast. Write for that:

| Pattern | Shape |
| --- | --- |
| Hot take | A clear opinion in one or two lines. "Most onboarding emails should be one sentence." |
| Honest moment | Something that happened, told plainly. "Shipped a bug to 400 people today. Here's what I told them." |
| Ask the room | A specific question people can answer from experience. "What's the one tool you'd pay for twice?" |
| Small lesson | "Took me 3 years to learn this:" then the lesson in a sentence or two. |
| Show the work | A photo or screen recording with one line of context. |

Rules:
- Lead with the point. The first line is the whole post for most readers.
- Short and loose: one to three sentences suits most posts. The hard limit is 500 characters, and text over it gets cut off.
- Write like a text to a smart friend. Lowercase-casual is fine if it's the user's voice. No corporate tone, no "we're thrilled to announce".
- End with something easy to reply to, when it fits: a question, a take people will argue with, or an invitation to share theirs.
- No hashtag strings. This server can't set a Threads topic tag, so don't rely on tags for reach.
- One link at most, and only when it's the point of the post.

## Longer ideas

This server can't publish a multi-post thread (a reply chain). If the idea won't fit in 500 characters:
- Cut it to the one sharpest point and publish that.
- Or put the detail in images and publish a carousel (up to 10 images or videos) with a short post on top.
- Or give the user the follow-up posts to add as replies themselves in the Threads app after the first one goes live.

## Media

An image or short video usually beats text alone for brand accounts. Images: JPEG or PNG up to 8 MB. Video: MP4 or MOV, up to 5 minutes. GIFs aren't supported.

## Output

Give the post exactly as it will appear with its character count, plus one alternate opening line. Suggest a visual if it would help. Offer to publish or schedule it with the `postonce` skill; confirm the Threads account and the time before calling `create_post`.
