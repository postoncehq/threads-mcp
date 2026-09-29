---
name: threads-content-calendar
description: Plan 1–4 weeks of Threads posts from the user's goals and topics, or repurpose a blog post, video, newsletter or transcript, draft every post under 500 characters, and schedule them with the PostOnce Threads MCP. Use when the user asks for a Threads content calendar, a Threads posting schedule, Threads post ideas, or to turn one piece of content into a week of Threads posts.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# Threads content calendar

Plan a run of Threads posts, draft each one, and schedule them once the user approves.

## Before planning

Get or infer:
- Goal: followers, replies and conversation, traffic, or staying visible between launches.
- 3 to 4 topics the account wants to be known for.
- How many weeks (1 to 4) and posts per day or week. Threads suits frequent, light posting; once a day is a solid default, more if the user has the ideas.
- Timezone and any fixed dates.
- Or a source to repurpose: a blog URL, video, podcast transcript or newsletter. Pull out every standalone opinion, lesson, number and story; each becomes one post.

## Build the plan

Mix post types across the week so the feed isn't one note:

| Type | Shape |
| --- | --- |
| Hot take | A clear opinion on one of the topics |
| Question | A specific question the audience can answer from experience |
| Lesson | One thing learned, told in two or three sentences |
| Behind the scenes | A photo or short video with one line of context |
| Carousel | Up to 10 images or videos for steps, before/after or a list |
| Share | A link to the user's own work, with the reason to click |

Keep links to a minority of posts. Give the plan as a table: date and time, topic, type, first line, media needed, status. Post times: use the user's own best times if they know them; otherwise pick consistent times and say they're a starting point to test.

## Draft each slot

Write every post with the `threads-post-writer` rules: point first, conversational, under 500 characters (text over 500 is cut off), no hashtag strings. Show the character count for each.

Multi-post threads (reply chains) can't be published through this server. If an idea needs several posts, schedule the lead post and give the user the follow-ups to add as replies in the app, or turn it into a carousel.

## Schedule

- Text-only posts can be scheduled right away: `create_post` with `publish_at` (ISO timestamp with the user's timezone offset).
- Posts with media: upload with `create_upload_url` first, then pass the URLs in order as `media`.
- Posts still waiting on media or approval: save with `create_draft`.
- To send a slot to other platforms too, add their accounts as targets and use `content_override` per platform (the `threads-crosspost-adapter` skill covers the rewrite).

## Output

Return the calendar table, then each post's draft. Ask for approval before scheduling anything. After approval, confirm the Threads account, create the posts, then list each post ID with its scheduled time from `get_post`. Scheduled posts can be changed with `update_post` or cancelled with `cancel_post` until they go out.
