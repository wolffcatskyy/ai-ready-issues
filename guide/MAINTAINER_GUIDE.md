# Maintainer Guide: Writing AI-Ready Issues

This guide helps maintainers write issues that contributors (with or without AI) can actually solve.

## When to Use (and Not Use) This Standard

The AI-ready format has a cost: writing a good issue takes 10-20 minutes of structured thinking. That investment only pays off when the issue is the right size.

### Write an AI-ready issue when:

- **The fix requires codebase knowledge you have but the contributor doesn't** — you know exactly which file and function to change, but explaining it unlocks someone who'd otherwise never attempt it
- **You'd accept a PR but nobody's picking it up** — the barrier to entry is too high, not the work itself
- **The change is self-contained** — 1-3 files, clear boundaries, testable in isolation
- **The issue writing is an investment** — 15 minutes now saves someone else hours of onboarding

### Just fix it yourself when:

- **You can solve it faster than you can describe it** — a two-line fix doesn't need a structured prompt. Writing the context, implementation guide, and acceptance criteria would take 10x longer than the fix
- **The context needed to explain it IS the work** — sometimes articulating the problem to a stranger is harder than solving it. That's not an AI-ready issue. That's just your job
- **It requires deep architectural judgment** — if the "right" answer depends on tradeoffs only you can evaluate, no amount of template will help

### The sweet spot:

**A single, well-bounded change that requires real codebase knowledge to implement but not to understand.**

Think: adding a new API endpoint behind a clear interface, implementing a feature where the design is settled but the contributor needs to know where things live, fixing a bug where you know the root cause but the fix touches code a newcomer wouldn't find on their own.

---

## Why Structure Matters

The #1 reason people don't contribute to open source isn't skill — it's context. They don't know:
- Where in the codebase the problem lives
- What constraints to respect
- How to test their fix
- What "done" looks like

AI-Ready issues answer all of these upfront.

## The Template

Every AI-Ready issue should have:

### 1. What (one sentence)

Clear, specific outcome. Not "improve error handling" but "Return descriptive error message when API key is invalid instead of generic 500."

### 2. Why (context)

Why does this matter? What user pain does it solve? This helps contributors (and their AI) understand intent, not just mechanics.

### 3. Where in the Code

Be specific:
- File name and path
- Class or function name
- Line numbers if helpful
- Related files that might need changes

This is the single most valuable thing you can provide. Without it, contributors spend 80% of their time just finding where to start.

### 4. Current vs Expected Behavior

| | Current | Expected |
|---|---------|----------|
| Input | `API_KEY=""` | `API_KEY=""` |
| Output | `500 Internal Server Error` | `Error: API_KEY is required` |

Concrete examples beat abstract descriptions.

### 5. Acceptance Criteria

Checkboxes. Specific. Testable.

- [ ] Returns HTTP 400 with message "API key is required" when key is empty
- [ ] Logs the error at WARNING level
- [ ] Does not crash the main loop
- [ ] Existing tests still pass

### 6. Constraints

What NOT to do:
- Don't add new dependencies
- Don't change the config format
- Don't break backward compatibility
- Keep it in the single file

### 7. AI Prompt Template (optional but powerful)

Pre-written prompt the contributor can paste directly into their AI:

```
I'm fixing [issue] in [project]. Context:
[project summary]

The relevant code is:
[paste code here]

Please fix this while following the project's patterns.
```

## Tips for Writing Good AI-Ready Issues

### Do

- **Be specific about file locations** — "in `bouncer.py`, the `UniFiClient._request()` method around line 340"
- **Include example input/output** — concrete beats abstract
- **List what to preserve** — "must still work when SKIP_TLS_VERIFY=true"
- **Use checkboxes for acceptance criteria** — makes review binary
- **Label with `ai-ready`** — so contributors can filter for them

### Don't

- **Don't be vague** — "improve performance" is not actionable
- **Don't assume context** — the contributor (and their AI) may never have seen your code
- **Don't skip constraints** — "don't add dependencies" prevents a lot of bad PRs
- **Don't write the solution** — describe the outcome, let the contributor figure out how

## Labeling

Use these labels:
- `ai-ready` — structured for AI-assisted contribution
- `good first issue` — suitable for newcomers
- `help wanted` — actively seeking contributors

Combine them: an issue can be `ai-ready` + `good first issue` + `help wanted`.

## Reviewing AI-Assisted PRs

When a PR discloses AI assistance:

1. **Read more carefully** — AI can produce plausible-looking but subtly wrong code
2. **Check edge cases** — AI often handles the happy path but misses errors
3. **Verify it matches your patterns** — AI may use different conventions
4. **Test the claimed scenarios** — don't assume the contributor tested thoroughly
5. **Be encouraging** — they're learning by doing, which is the whole point

## Example: Good vs Bad Issues

### Bad

> **Title:** Add retry logic
> **Body:** We should retry failed requests.

### Good

> **Title:** [Feature]: Add exponential backoff retry for API 502/503 errors
>
> **What:** Retry failed API requests with exponential backoff when the server returns 502, 503, or 504.
>
> **Why:** The server sometimes returns transient 502 errors during updates or high load. Currently the client crashes and needs manual restart.
>
> **Where:** `client.py`, `Client._request()` method (line ~340). This method handles all API calls.
>
> **Acceptance criteria:**
> - [ ] Retries on HTTP 502, 503, 504
> - [ ] Exponential backoff: 1s, 2s, 4s (max 3 retries)
> - [ ] Logs each retry at WARNING level
> - [ ] Raises the original exception after max retries
> - [ ] Does not retry on 401 (auth failure) or 404 (not found)
>
> **Constraints:**
> - No new dependencies (use time.sleep)
> - Must not affect the existing 401 re-auth logic
> - Keep in single file
