# Contributor Guide: Using AI to Contribute to Open Source

This guide walks you through using AI assistants (Claude, ChatGPT, GitHub Copilot, etc.) to make meaningful open source contributions.

## Before You Start

### You Don't Need To Be an Expert

You don't need to understand the entire codebase. You need to understand:
- What the issue is asking for
- What the code you're changing does
- How to test your changes

AI handles the boilerplate. You handle the thinking.

### You ARE Responsible

AI-assisted doesn't mean AI-authored. You're submitting this code under your name. That means:
- You reviewed every line
- You understand what it does
- You tested it
- You'd be comfortable explaining it

## The Workflow

### Step 1: Find an AI-Ready Issue

Look for issues labeled `ai-ready` in the project's issue tracker. These are specifically written with enough context for AI-assisted solving.

### Step 2: Gather Context

You need three things:

1. **The issue body** — copy the full text
2. **The AI context block** — from the project's CONTRIBUTING.md (under "Using AI to Contribute")
3. **The relevant source code** — the files mentioned in "Where in the Code"

### Step 3: Prompt Your AI

Paste all three into your AI assistant. A good prompt looks like:

```
I want to contribute to [project]. Here's the project context:

[paste AI context block from CONTRIBUTING.md]

The issue I want to work on is:

[paste full issue body]

The relevant code is:

[paste the source file(s)]

Please implement this while:
- Following the project's existing code style
- Respecting the constraints listed in the issue
- Including appropriate error handling
- Not adding new dependencies
```

### Step 4: Review the Output

This is the most important step. Do NOT blindly copy-paste AI output into a PR.

**Check for:**

- [ ] Does it actually solve the issue?
- [ ] Does it match the project's code style?
- [ ] Does it handle errors properly?
- [ ] Does it respect the constraints?
- [ ] Are there any obvious bugs?
- [ ] Would you be comfortable explaining this code?

**Common AI mistakes to watch for:**
- Importing libraries that aren't in the project's dependencies
- Using patterns that don't match the existing code
- Handling the happy path but ignoring errors
- Over-engineering simple solutions
- Adding features not asked for in the issue

### Step 5: Test Locally

Follow the project's development setup to run and test your changes:

```bash
# Clone your fork
git clone https://github.com/YOUR-USERNAME/project.git
cd project

# Set up the development environment
# (follow the project's CONTRIBUTING.md)

# Test your changes
# Run the project, trigger the scenario from the issue
# Verify the acceptance criteria are met
```

### Step 6: Submit Your PR

Create a PR with:
- Clear description of what changed
- Which issue it addresses
- How you tested it
- **AI disclosure** — what tool you used, what it generated, what you changed

**Example AI disclosure:**

```
## AI Assistance
**Tools Used:** Claude
**Scope:** Generated initial retry logic implementation
**Changes Made:** Adjusted backoff timing, fixed edge case where
  401 errors were incorrectly retried, matched existing log format
**Validation:** Tested with simulated 502 responses, verified
  backoff timing with LOG_LEVEL=DEBUG
```

## Tips

### Iterate With Your AI

Don't expect the first output to be perfect. Common follow-ups:

- "This doesn't match the project's logging style — they use `log.info()` not `print()`"
- "The issue says no new dependencies but you imported `tenacity`"
- "Can you simplify this? The project keeps things minimal"
- "The error handling needs to catch `requests.ConnectionError` specifically, not bare `Exception`"

### Start Small

Your first contribution doesn't need to be a major feature. Documentation fixes, error message improvements, and small bug fixes are great starting points.

### Ask Questions

If the issue is unclear, comment on it and ask. Maintainers would rather answer questions upfront than review a misguided PR.

### Don't Take Rejection Personally

PR feedback isn't criticism of you. It's collaboration. Maintainers might ask for changes — that's normal and means they're engaged with your contribution.

## What Not to Do

- **Don't submit code you haven't read** — "my AI wrote it" isn't a defense
- **Don't submit without testing** — "it compiled" isn't testing
- **Don't hide AI usage** — disclosure builds trust
- **Don't spam PRs** — quality over quantity
- **Don't argue with maintainers about AI** — their project, their rules

## FAQ

**"Is using AI cheating?"**
No. Using a compiler isn't cheating. Using Stack Overflow isn't cheating. AI is a tool. What matters is whether the output is correct and you understand it.

**"What if the maintainer doesn't want AI contributions?"**
Respect their choice. Not every project is on board yet.

**"Which AI should I use?"**
Whichever you're comfortable with. Claude, ChatGPT, and GitHub Copilot all work. The important thing is reviewing the output, not which tool generated it.

**"I'm not a developer — can I still do this?"**
Yes, especially for documentation, configuration examples, and simple bug fixes. Start with `good first issue` + `ai-ready` labeled issues.
