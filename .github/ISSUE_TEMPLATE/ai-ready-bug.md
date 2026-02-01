---
name: "AI-Ready Bug Report"
about: "Report a bug with enough context for AI-assisted fixing"
title: "[Bug]: "
labels: ["bug", "ai-ready"]
assignees: ""
---

## What

[One sentence describing the bug]

## Current Behavior

[What happens now — be specific]

## Expected Behavior

[What should happen instead]

## Steps to Reproduce

1. [First step]
2. [Second step]
3. [What you observe]

## Environment

- OS: [e.g., Ubuntu 22.04, macOS 14, Synology DSM 7.3]
- Version: [project version or commit hash]
- Runtime: [e.g., Python 3.11, Node 20, Docker 24]
- Related services: [e.g., CrowdSec 1.6, UniFi 8.x]

## Logs / Error Output

```
[Paste relevant logs here]
```

## Where in the Code

[File, class, method, or line range where the bug likely lives]

## Acceptance Criteria

- [ ] [Specific testable requirement]
- [ ] [Another requirement]
- [ ] [Edge case]

## Constraints

- Must not break: [existing behavior to preserve]
- Must work with: [specific configurations or environments]
- Cannot add: [new dependencies, new files, etc.]

## AI Prompt Template (optional)

```
I'm fixing a bug in [project]. Here's the context:

[Paste the project's AI context block from CONTRIBUTING.md]

The bug is: [paste this issue]

The relevant code is:
[paste the file/function mentioned in "Where in the Code"]

Please fix this bug while:
- Preserving existing behavior
- Following the project's code style
- Adding appropriate error handling
```
