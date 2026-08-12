---
platform: tiktok
topic: Three mistakes new React developers make
created: 2026-08-12
---

# Three React Mistakes New Developers Make

**Hooks**
1. Three React mistakes that make your code harder than it needs to be.
2. If you're new to React, stop doing these three things.
3. Your React app might work, but these habits will slow you down.

**Selected Hook**
Hook 2 is the strongest fit because it is direct, easy to say aloud, and immediately signals a practical list for beginners.

**Spoken Script**
If you're new to React, stop doing these three things.

First: storing everything in state. If a value can be calculated from existing props or state, calculate it during render. Don't create extra state you then have to keep in sync.

Second: putting API logic straight into your component. Keep the component focused on the UI, and move fetching or mutation logic into a separate function, hook, or service.

Third: using `useEffect` for everything. `useEffect` is for syncing with things outside React, like an API, browser event, or timer. It is not the default place for normal calculations.

Small rule: before adding state or an effect, ask, "Can React already derive this?"

**Shot List**
- Face to camera, quick opening line.
- Cut to screen recording showing unnecessary `useState`.
- Show the cleaner derived value version.
- Cut to messy component with API call inline.
- Show API logic moved into a small hook or service.
- Show a `useEffect` example crossed out, then the simpler render-time calculation.
- End face to camera with the final rule.

**On-Screen Text**
- Stop these React habits
- 1. Too much state
- Derive values when you can
- 2. API logic in UI
- Keep components focused
- 3. `useEffect` for everything
- Ask: can React derive this?

**Caption**
New React developers often make React feel harder by adding state and effects too early. Keep components focused, derive what you can, and reach for `useEffect` only when you actually need to sync with something outside React.

**Call To Action**
Save this for your next React refactor.

**Hashtags**
#ReactJS #WebDevelopment #FrontendDevelopment #LearnToCode #JavaScript
