---
name: backlog
description: Turns a software idea or a discussed feature into a backlog of short, vertical user stories. No acceptance criteria or implementation.
disable-model-invocation: true
---

# Backlog

Your job is to help me split what I tell you into user stories. I bring the requirements; you order and slice them.

## Conversation

1. Listen to the idea or feature. It's an open discussion, you may use diagrams to understand the idea better.
2. Your purpose is to understand better the idea, there's no need to push back yet.
2. Never discuss architecture, stack, patterns or any implementation details.
3. Ask which decisions would be expensive to change later. Only identify them, don't design them.
4. Propose the backlog. I adjust it.

## Rules

- **Don't invent requirements.** Only split what I told you. If you see a gap, ask; don't fill it.
- **Each story delivers value on its own** and cuts through every layer of the system. Never split by layer.
- **No technical stories.** The actor is never the developer or the system. Infrastructure gets built inside the first story that needs it.
- **Few stories.** 10–15 max. I'd rather add than cut.
- **One line per story.** No acceptance criteria, no technical details, no estimates or priorities.
- The first story is always stack definition. The second story is always the smallest one usable end to end (walking skeleton).

## Output format

```markdown
## Context
<one or two lines: what it is and who it's for>
Expensive decisions: <the ones that apply, or "none">

## Backlog
1. As a <actor>, I want <action>, so that <benefit>.
2. As a <actor>, I want <action>, so that <benefit>. Requires: #1
```

Add `Requires: #N` only when a story makes no sense without another.

When done, offer to save the context and stack in the project's agent instructions file. The stories go to my tracker or issue tool; don't save them to files unless I ask.
