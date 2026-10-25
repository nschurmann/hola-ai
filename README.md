# hola-ai

Agent skills for building software with AI **without letting go of the wheel**. Inspired by Extreme Programming: vertical user stories, acceptance criteria, test-first, pair programming, simple design.

The AI splits, proposes and writes code in small steps. You decide.

## The flow

```
/backlog  →  /story  →  /pair
  what       what exactly   how
```

| Skill | What it does | What it never does |
|---|---|---|
| [`/backlog`](skills/backlog/SKILL.md) | Turns an idea into a short backlog of vertical, one-line user stories. | Invent requirements, technical stories, estimates. |
| [`/story`](skills/story/SKILL.md) | Refines **one** story with Given/When/Then acceptance criteria, explicit business rules, and a mini plan (≤5 bullets). | Write code, invent rules, or split stories only because they have more than 3 criteria. |
| [`/pair`](skills/pair/SKILL.md) | Pair programming: test acceptance criteria and business rules, then one test → red → minimum code → green at a time. | Commit, edit tests to make them pass, add things you didn't ask for. |

Each skill's output is the next one's input, as blocks ready to paste into your tracker.

## Principles

- **Don't invent.** Missing information gets asked, not filled in.
- **The simplest thing that works.** No abstractions "for the future".
- **Slice vertically and small.** Stories cross every layer; steps are one test and ~50 lines.
- **Suggest, don't decide.** Patterns, refactors and commits are your call.
- **Explicit checkpoints.** Every phase ends waiting for your approval.

## Install

Copy the skill folders into your Claude Code skills directory:

```bash
git clone https://github.com/nschurmann/hola-ai.git
cp -r hola-ai/skills/* ~/.claude/skills/        # all projects
# or
cp -r hola-ai/skills/* <your-project>/.claude/skills/   # one project
```

The skills are only invoked manually (`/backlog`, `/story`, `/pair`), never automatically.

Or ask your agent to install these skills!

---

By Hola Mundo.
