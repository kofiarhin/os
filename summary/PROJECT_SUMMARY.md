# Project Summary

## Last Task

Updated local Instagram and TikTok project skills so completed generated content is saved by default.

## Progress

- Moved `create-instagram-post` into `.agents/skills/` while preserving its existing workflow.
- Added `create-tiktok-content` with required repository context reads and short-form video output guidance.
- Added instruction-based default saving to `_output/instagram/` and `_output/tiktok/`, including filename sanitisation, non-overwrite numbering, Markdown frontmatter, and filesystem-write fallback behavior.
- Both project skills validated successfully with the skill creator validator after running it with temporary PyYAML availability.

## Files

- `.agents/skills/create-instagram-post/SKILL.md`
- `.agents/skills/create-instagram-post/agents/openai.yaml`
- `.agents/skills/create-tiktok-content/SKILL.md`
- `.agents/skills/create-tiktok-content/agents/openai.yaml`
- `_output/instagram/`
- `_output/tiktok/`
