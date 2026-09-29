---
name: threads-crosspost-adapter
description: Rewrite an X (Twitter), LinkedIn, Instagram or Facebook post into a Threads-native post under 500 characters, then publish or schedule it with the PostOnce Threads MCP. Use when the user asks to crosspost to Threads, repurpose a tweet or LinkedIn post for Threads, adapt a caption for Threads, or post the same thing on Threads and other platforms.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# Threads crosspost adapter

Pasting the same post everywhere reads as pasted. This skill keeps the idea and rewrites the delivery for Threads, then publishes it with the `postonce` skill.

## Before rewriting

Get the source post and where it came from. Ask whether the user wants the Threads version to go out at the same time as the original (one `create_post` with several targets) or on its own schedule. Keep every fact from the source; don't add claims it didn't make.

## What to change, by source

| Source | Usually needs |
| --- | --- |
| X (Twitter) post | Little. Drop X-only habits: @handles that don't exist on Threads, "RT", hashtag strings. Loosen the tone slightly; add a reply prompt if it fits. |
| X thread | Can't be published as a Threads reply chain here. Pull the single strongest point into one post, or carry the steps on carousel images. |
| LinkedIn post | Cut hard. Keep the one idea and the stance; drop the setup lines, the "Here's what I learned" framing, the bullet lists and the hashtags. 3,000 characters becomes 500 at most. |
| Instagram caption | Drop "link in bio" and the hashtag block. If the post relied on the image, reuse the image, or write a line that works without it. |
| Facebook post | Tighten, drop page-voice phrasing, keep the human part. |

Threads-native checklist:
- The point is in the first line.
- It sounds like a person, not a brand channel.
- It fits in 500 characters with room to spare. Text over 500 is cut off.
- It ends with something easy to reply to, when that fits.
- No hashtag strings; this server can't set a Threads topic tag.
- Links only if the link is the point.

## Media

Reuse the source's images or video when they still make sense. Threads takes JPEG or PNG up to 8 MB, MP4 or MOV up to 5 minutes, and carousels of up to 10 items. GIFs aren't supported.

## Posting to several platforms at once

To send one post to Threads and other platforms together, use one `create_post` with each account as a target, the shared text as `content`, and the Threads version in that target's `content_override`. Check each platform's own limits; for example, Instagram needs media.

For ongoing crossposting of future posts from one account to Threads, the `postonce` skill can set up a workflow with `create_workflow`. That copies posts as they are; this skill is for rewriting.

## Output

Show the source and the Threads version side by side with the Threads character count, and one line on what you changed. Offer to publish or schedule with the `postonce` skill; confirm the Threads account and the time before calling `create_post`.
