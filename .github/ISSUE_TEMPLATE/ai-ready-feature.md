---
name: "AI-Ready Feature Request"
about: "Request a feature with enough context for AI-assisted implementation"
title: "[Feature]: "
labels: ["enhancement", "ai-ready"]
assignees: ""
---

## What

[One sentence describing the desired feature]

## Why

[Context on why this matters — what problem does it solve?]

## Proposed Behavior

[Describe how the feature should work from the user's perspective]

## Where in the Code

[File, class, method, or section where this should be implemented]

## Acceptance Criteria

- [ ] [Specific testable requirement]
- [ ] [Another requirement]
- [ ] [Edge case handling]

## Constraints

- Must not break: [existing features]
- Must be configurable via: [env var / config file / etc.]
- Must degrade gracefully if: [not configured / service unavailable]
- No new dependencies unless: [justified]

## Design Notes (optional)

[Any thoughts on implementation approach, API design, data structures, etc.]

## AI Prompt Template (optional)

```
I'm adding a feature to [project]. Here's the context:

[Paste the project's AI context block from CONTRIBUTING.md]

The feature request is: [paste this issue]

The relevant code is:
[paste the file/function mentioned in "Where in the Code"]

Please implement this feature while:
- Following the project's existing patterns
- Adding appropriate error handling
- Making it configurable via environment variable with a sensible default
- Ensuring graceful degradation if not configured
```
