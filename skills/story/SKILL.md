---
name: story
description: Refines ONE backlog story with acceptance criteria, explicit business rules, and a minimal implementation plan for approval. Writes no code; implementation is /pair's job.
disable-model-invocation: true
---

# Story

We refine a single story, right before building it. You propose and I decide.

## Steps

1. **Read the story** I give you (pasted text, GitHub issue, Jira ticket, etc.). Inspect only the relevant code and project instructions (`CLAUDE.md` or `AGENTS.md`, when present) to understand existing behavior and conventions.
2. **Acceptance criteria.** Prefer 2–3 in Given/When/Then format; use up to 5 when justified. Describe observable outcomes, including relevant failure cases, never implementation details.
3. **Business rules.** Identify the confirmed domain constraints this story must respect: permissions, calculations, limits, conditions, exceptions, and invariants. State each as a clear, testable rule (`BR-01`, `BR-02`, ...). Keep rules separate from acceptance criteria and avoid repeating them verbatim. If none apply, write `No additional business rules identified.` If a required rule is missing or ambiguous, ask rather than invent it.
4. **Check the story's size.** Do not split merely because there are more than 3 criteria or several business rules. Propose a split only for independently deliverable behavior, unrelated responsibilities, or work that cannot be implemented and verified as one focused change. Show the proposed stories in backlog format (`As a…, I want…, so that…`) and any real dependencies; wait for approval before refining the first one.
5. **Mini plan.** 5 bullets max, no code. Describe the smallest change across the relevant parts of the existing system. Mention specific existing modules only when confirmed in the repository; do not invent components or architecture.
6. **Wait for my approval.** We adjust until I say yes. Do not implement.

## Rules

- **Don't invent requirements or business rules.** Confirm them from the story, its referenced context, or existing behavior. Ask when a missing decision would change the result.
- **Acceptance criteria and business rules serve different purposes.** Criteria describe what must happen; rules define constraints that must always hold. Both must be testable and consistent with each other.
- **Preserve existing behavior** unless the story explicitly calls for a change. Surface conflicts between the story, business rules, and existing behavior instead of resolving them silently.
- **Split vertically, not technically.** Each proposed story must deliver a meaningful outcome, not just a database, API, or UI slice. Do not continue with a split without approval.
- **The simplest thing that meets the criteria and business rules.** No abstractions, layers, configuration, defensive architecture, or patterns "for the future".
- **Suggest, don't decide.** Mention an optional pattern or refactor under "Suggestions" only if a concrete signal in the code justifies it, and explain why.
- **Don't write code or change project files.** Implementation belongs to `/pair`.

## Output format

A block ready to paste into the issue. `/pair` uses the acceptance criteria **and** business rules as input. Omit "Dependencies" and "Suggestions" when they do not apply.

```markdown
## Story
As a <actor>, I want <action>, so that <benefit>.

## Acceptance Criteria
- [ ] Given <context>, when <action>, then <result>.
- [ ] ...

## Business Rules
- BR-01: <confirmed business constraint>
- BR-02: <applicable calculation, condition, permission, or invariant>

## Plan
- <minimal implementation step>
- ...

## Dependencies
- <actual prerequisite, if any>

## Out of Scope
- <what is explicitly excluded from this story>

## Suggestions (your call)
- <optional suggestion backed by the existing code>
```

If no additional business rules apply, replace the example `BR-XX` entries with `No additional business rules identified.` Never create rules just to fill the template.
