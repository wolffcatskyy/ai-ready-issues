# Contributing to [PROJECT NAME]

Welcome! We're thrilled you're interested in contributing. This guide is designed for **everyone** — whether you're contributing your first line of code, using AI tools to help, or simply reporting ideas. No prior open source experience required.

## Table of Contents

- [Ways to Contribute](#ways-to-contribute)
- [First-Time Contributors](#first-time-contributors)
- [Using AI to Contribute](#using-ai-to-contribute)
- [Development Setup](#development-setup)
- [Making Changes](#making-changes)
- [Submitting Pull Requests](#submitting-pull-requests)
- [Code of Conduct](#code-of-conduct)
- [Getting Help](#getting-help)

---

## Ways to Contribute

Contributions aren't limited to code. Here are ways you can help:

### Bug Reports & Issues
- Found something broken? [Open an issue](../../issues)
- Unexpected behavior? Let us know
- Include steps to reproduce, expected vs actual behavior

### Documentation
- Improved installation instructions
- Clearer explanations of features
- Troubleshooting guides based on your experience

### Features & Enhancements
- New features and integrations
- Better error messages
- Performance improvements

### Testing & Quality
- Test on your setup and report results
- Report edge cases or compatibility issues
- Help build automated tests

### Community
- Answer questions from other users
- Share your deployment stories
- Help improve this documentation

---

## First-Time Contributors

Never contributed to open source before? Perfect. This project is a great place to start.

### Step 1: Fork the Repository

Click the **Fork** button at the top of the [repository page](../../). You now have your own copy to experiment with safely.

### Step 2: Clone Your Fork

```bash
git clone https://github.com/YOUR-USERNAME/[PROJECT-NAME].git
cd [PROJECT-NAME]
```

### Step 3: Create a Branch

```bash
git checkout -b fix/my-fix-name
# or for features:
git checkout -b feature/my-feature-name
```

**Branch naming conventions:**
- `fix/` — bug fixes
- `feature/` — new features
- `docs/` — documentation
- `test/` — testing improvements

### Step 4: Make Your Changes

See [Making Changes](#making-changes) below.

### Step 5: Commit and Push

```bash
git add .
git commit -m "Fix: describe what you fixed"
git push origin fix/my-fix-name
```

### Step 6: Open a Pull Request

1. Go to the original repository
2. Click **Pull Requests** > **New Pull Request**
3. Select your branch
4. Fill out the PR template
5. Submit!

---

## Using AI to Contribute

We **welcome and encourage** AI-assisted contributions. AI tools (Claude, ChatGPT, GitHub Copilot, etc.) can help you generate code, write tests, improve documentation, and debug issues.

### Architecture Context for AI

Paste this into your AI assistant along with the issue you want to work on:

```
I want to contribute to [PROJECT NAME]. Here's the project context:

[REPLACE WITH YOUR PROJECT'S ARCHITECTURE SUMMARY]
- Main files and their purposes
- Key classes/functions
- Dependencies
- Config approach (env vars, config files, etc.)
- Important design constraints

The issue I want to work on is: [paste issue title and body here]
```

Then paste the relevant source code and ask your AI to implement the fix/feature.

### Guidelines for AI-Assisted Work

**You are always responsible for your contribution.**

#### Required

1. **Review everything before submitting** — read every line, understand what it does
2. **Disclose AI assistance in your PR:**
   ```
   **AI Assistance:** Generated using [tool] with prompts focusing on [specific area]
   **Validation:** Tested in [your setup], verified [specific test cases]
   **Changes Made:** Manually reviewed and adjusted [list specific changes]
   ```
3. **Test thoroughly** — run the code locally, test error conditions
4. **Validate against project standards** — follows code style, doesn't break existing features

#### What We Won't Accept

- Unreviewed or untested AI output ("AI slop")
- Code you don't understand
- Changes that don't address a specific issue
- Low-quality generic "improvements"

---

## Development Setup

```bash
# [REPLACE WITH YOUR PROJECT'S SETUP STEPS]
git clone https://github.com/YOUR-USERNAME/[PROJECT-NAME].git
cd [PROJECT-NAME]
# Install dependencies
# Configure environment
# Run locally
```

---

## Making Changes

### Code Style

[REPLACE WITH YOUR PROJECT'S CODE STYLE GUIDELINES]

### Key Constraints

[REPLACE WITH YOUR PROJECT'S CONSTRAINTS]

### Pre-Submission Checklist

- [ ] Changes work locally
- [ ] Error messages are clear
- [ ] No debug code left in commits
- [ ] Documentation updated if needed

---

## Submitting Pull Requests

### PR Template

```markdown
## Description
Brief summary of what this PR does.

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Performance improvement

## Problem It Solves
Which issue does this address? (Link: #123)

## How Was This Tested?
- Environment: [your setup]
- Scenarios verified: [list]

## Checklist
- [ ] I've tested this locally
- [ ] I've updated documentation if needed
- [ ] My code follows the project style
- [ ] No debug code or secrets in commits

## AI Assistance (if applicable)
**Tools Used:** Claude / ChatGPT / GitHub Copilot
**Scope:** Generated [specific part], reviewed and validated [changes made]
**Validation:** Tested in [environment], verified [specific test cases]
```

---

## Code of Conduct

- **Be respectful** to all contributors
- **Welcome diverse perspectives** and experiences
- **Ask questions** rather than make assumptions
- **Assume good intent** in interactions

---

## Getting Help

**"I'm not a programmer, can I still contribute?"**
Absolutely! Documentation, testing, and reporting issues are huge helps.

**"Can I use AI tools?"**
Yes! See [Using AI to Contribute](#using-ai-to-contribute). Just review and test everything.

**"How long until my PR is reviewed?"**
We aim for a few days. If it's been a week, ping us politely.

**"What if my PR is rejected?"**
That's okay! We'll explain why and suggest improvements. You can revise and resubmit.

---

**Ready to contribute? Pick an issue from the [issues page](../../issues) and get started!**
