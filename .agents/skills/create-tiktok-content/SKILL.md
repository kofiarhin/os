---
name: create-tiktok-content
description: Create TikTok video concepts, scripts, hooks, captions, shot lists, on-screen text, calls to action, and hashtags. Use whenever the user asks for TikTok content or short-form video ideas.
---

# Create TikTok Content

## Required Context

Before creating TikTok or short-form video content, read:

- `CONTEXT/PERSONAL_PROFILE.md`
- `CONTEXT/MEMORY.md`
- `CONTEXT/BRANDS/KOFI.md`

If any required context file is unavailable, stop and ask one focused question for the missing path or brand context. Do not generate content from memory alone.

## Workflow

1. Identify the topic, audience, goal, platform format, and any supplied facts or media.
2. Generate three distinct hooks that are short, specific, and easy to say aloud.
3. Select the strongest hook and briefly state why it is the best fit.
4. Write a spoken script using UK English. Keep it concise, practical, conversational, and easy to record.
5. Create a shot list with simple, recordable visual beats.
6. Write on-screen text that is short enough to work as overlays.
7. Provide a caption, a natural call to action, and up to five relevant hashtags.

## Output Format

Use this structure by default:

```markdown
**Hooks**
1. ...
2. ...
3. ...

**Selected Hook**
...

**Spoken Script**
...

**Shot List**
- ...

**On-Screen Text**
- ...

**Caption**
...

**Call To Action**
...

**Hashtags**
#tag #tag #tag
```

## Save Completed Results

Save every completed TikTok result by default.

1. Create `_output/tiktok/` if it does not already exist.
2. Save the complete platform output, including every section required by this skill, as a Markdown file in `_output/tiktok/`.
3. Name the file `YYYY-MM-DD-topic-slug.md`, using the current date and the original topic.
4. Build `topic-slug` from the topic by lowercasing it, keeping only lowercase letters and numbers, replacing spaces with hyphens, removing unsafe filename characters, collapsing repeated hyphens, trimming leading or trailing hyphens, and keeping the result concise and descriptive.
5. Never overwrite an existing file. If the target filename exists, append `-2`, then `-3`, and continue incrementing until an unused filename is found.
6. Write the saved file with this structure:

```markdown
---
platform: tiktok
topic: The original topic
created: YYYY-MM-DD
---

# Title

Complete generated content
```

Replace `The original topic`, `YYYY-MM-DD`, `Title`, and `Complete generated content` with the actual topic, date, concise content title, and complete TikTok output.

After saving, return a short completion summary, the exact saved file path, and any validation limitations. If filesystem writing is unavailable, return the complete generated content in the response, clearly state that the file was not saved, and do not claim that saving succeeded.

## Voice And Content Rules

Write in UK English. Keep the tone:

- concise
- practical
- conversational
- direct
- confident
- easy to record without sounding scripted

Avoid:

- fake personal stories
- invented achievements, clients, statistics, testimonials, partnerships, or results
- exaggerated claims
- engagement bait
- corporate jargon
- filler phrases
- excessive hashtags

If useful details are missing, either write from the available facts or ask one focused question when the missing detail materially affects accuracy.
