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
| [`/story`](skills/story/SKILL.md) | Takes **one** story, adds 2–3 Given/When/Then acceptance criteria and a mini plan (≤5 bullets) for your approval. | Write code. If it needs more than 3 criteria, it proposes splitting the story. |
| [`/pair`](skills/pair/SKILL.md) | Pair programming: the AI drives, you navigate. One test → red → minimum code → green, then it stops and waits. | Commit, edit tests to make them pass, add things you didn't ask for. |

Each skill's output is the next one's input, as blocks ready to paste into your tracker.

## Principles

- **Don't invent.** Missing information gets asked, not filled in.
- **The simplest thing that works.** No abstractions "for the future".
- **Slice vertically and small.** Stories cross every layer; steps are one test and ~50 lines.
- **Suggest, don't decide.** Patterns, refactors and commits are your call.
- **Explicit checkpoints.** Every phase ends waiting for your approval.

## Install

### Claude Code

Copy the skill folders into your Claude Code skills directory:

```bash
git clone https://github.com/nschurmann/hola-ai.git
cp -r hola-ai/skills/* ~/.claude/skills/        # all projects
# or
cp -r hola-ai/skills/* <your-project>/.claude/skills/   # one project
```

### OpenCode

Copy the skills and the commands into your OpenCode config:

```bash
git clone https://github.com/nschurmann/hola-ai.git

# all projects
mkdir -p ~/.config/opencode/skills ~/.config/opencode/commands
cp -r hola-ai/skills/* ~/.config/opencode/skills/
cp hola-ai/opencode/commands/*.md ~/.config/opencode/commands/

# one project
mkdir -p <your-project>/.opencode/skills <your-project>/.opencode/commands
cp -r hola-ai/skills/* <your-project>/.opencode/skills/
cp hola-ai/opencode/commands/*.md <your-project>/.opencode/commands/
```

In both harnesses the skills are only invoked manually (`/backlog`, `/story`, `/pair`), never automatically.

Or ask your agent to install these skills!

---

By Hola Mundo.
