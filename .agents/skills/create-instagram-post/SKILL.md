---
name: create-instagram-post
description: Create Instagram posts, captions, carousels, Reel concepts, hooks, hashtags, and visual direction. Use whenever the user asks for Instagram content.
---

# Create Instagram Post

## Required Context

Before writing any Instagram copy, read `~/.codex/context/PERSONAL_PROFILE.md`.

If that file is unavailable, stop and ask the user for the correct profile path or brand context. Do not generate the post from memory alone.

Use the profile as brand guidance, especially for:

- voice and tone
- target audience
- positioning
- creative and technical interests
- factual boundaries
- visual direction when relevant

## Workflow

1. Identify the post type: photo, Reel, carousel, technical content, photography post, product post, behind-the-scenes content, or mixed format.
2. Inspect any attached or referenced image/video/content when available.
3. Extract only the facts the user provided or that are visible in supplied media.
4. Choose the most relevant audience and angle from the profile.
5. Write platform-ready Instagram copy with:
   - an Instagram title or opening hook
   - a caption
   - a natural call to action
   - 8-15 relevant hashtags
6. Keep the output concise unless the user asks for multiple options or a longer caption.

## Output Format

Use this structure by default:

```markdown
**Hook**
...

**Caption**
...

**Call To Action**
...

**Hashtags**
#tag #tag #tag
```

For carousels, add a short slide-by-slide structure only when the user asks for carousel copy or when the supplied content clearly needs it.

For Reels, include on-screen text beats only when helpful. Keep them short enough to work as actual overlays.

## Save Completed Results

Save every completed Instagram result by default.

1. Create `_output/instagram/` if it does not already exist.
2. Save the complete platform output, including every section required by this skill, as a Markdown file in `_output/instagram/`.
3. Name the file `YYYY-MM-DD-topic-slug.md`, using the current date and the original topic.
4. Build `topic-slug` from the topic by lowercasing it, keeping only lowercase letters and numbers, replacing spaces with hyphens, removing unsafe filename characters, collapsing repeated hyphens, trimming leading or trailing hyphens, and keeping the result concise and descriptive.
5. Never overwrite an existing file. If the target filename exists, append `-2`, then `-3`, and continue incrementing until an unused filename is found.
6. Write the saved file with this structure:

```markdown
---
platform: instagram
topic: The original topic
created: YYYY-MM-DD
---

# Title

Complete generated content
```

Replace `The original topic`, `YYYY-MM-DD`, `Title`, and `Complete generated content` with the actual topic, date, concise content title, and complete Instagram output.

After saving, return a short completion summary, the exact saved file path, and any validation limitations. If filesystem writing is unavailable, return the complete generated content in the response, clearly state that the file was not saved, and do not claim that saving succeeded.

## Voice Rules

Write in a voice that is:

- direct
- practical
- confident
- intelligent without sounding academic
- creative without becoming vague
- conversational without becoming careless
- clear about the value or idea behind the post

Avoid:

- corporate jargon
- empty motivational language
- engagement bait
- exaggerated claims
- manufactured controversy
- excessive emojis
- fake vulnerability
- generic captions

## Factual Boundaries

Do not invent:

- personal stories
- achievements
- statistics
- clients
- testimonials
- partnerships
- results
- credentials
- private personal details

If useful details are missing, either write from the available facts or ask one focused question when the missing detail materially affects the post.

## Hashtag Rules

Provide 8-15 hashtags.

Use hashtags that are relevant to the post type, topic, and audience. Mix broad and specific tags where appropriate. Do not use unrelated viral tags.
