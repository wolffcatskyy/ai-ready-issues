# AI-Ready Issues

A standard for writing open source issues that AI assistants can help solve.

Most people want to contribute to projects they use but don't know where to start. The codebase is unfamiliar, the setup is complex, and who has time to learn a whole project just to fix one thing?

AI-Ready Issues solve this by giving contributors everything they need — context, requirements, expected behavior — formatted so they can paste it into Claude, ChatGPT, or any AI assistant and get working code back.

## The Standard

An AI-Ready issue includes:

1. **Context** — what the project does, relevant files, architecture
2. **Current behavior** — what happens now
3. **Expected behavior** — what should happen
4. **Acceptance criteria** — specific, testable requirements
5. **Constraints** — what not to break
6. **Prompt template** (optional) — starting point for the AI

## The Workflow

```
Maintainer writes AI-ready issue
        |
        v
Contributor copies it into Claude/ChatGPT/Copilot
        |
        v
Contributor reviews output, tests it, learns from it
        |
        v
Contributor submits PR with AI disclosure
        |
        v
Maintainer reviews and merges
```

## What This Is

- Lowering the barrier to open source participation
- AI handles boilerplate, humans handle thinking
- Turning "I wish this had feature X" into "I'll just add it"
- Distributed development using distributed compute

## What This Isn't

- Dumping untested AI garbage
- Submitting code you don't understand
- Replacing real developers

## Quick Start

### For Maintainers

1. Copy the [issue templates](.github/ISSUE_TEMPLATE/) into your repo
2. Adapt the [CONTRIBUTING.md template](templates/CONTRIBUTING.md) for your project
3. Write issues using the AI-Ready format
4. Label them `ai-ready` so contributors can find them

### For Contributors

1. Find an issue labeled `ai-ready`
2. Copy the issue body + the project's AI context block (from CONTRIBUTING.md)
3. Paste into your AI assistant
4. Review every line of output — understand it before submitting
5. Test locally
6. Submit a PR with AI disclosure

## Templates Included

| File | Purpose |
|------|---------|
| [templates/CONTRIBUTING.md](templates/CONTRIBUTING.md) | Drop-in CONTRIBUTING.md with AI contribution guidelines |
| [.github/ISSUE_TEMPLATE/ai-ready-bug.md](.github/ISSUE_TEMPLATE/ai-ready-bug.md) | Bug report formatted for AI consumption |
| [.github/ISSUE_TEMPLATE/ai-ready-feature.md](.github/ISSUE_TEMPLATE/ai-ready-feature.md) | Feature request formatted for AI consumption |
| [templates/PR_TEMPLATE.md](templates/PR_TEMPLATE.md) | Pull request template with AI disclosure section |
| [guide/MAINTAINER_GUIDE.md](guide/MAINTAINER_GUIDE.md) | How to write effective AI-ready issues |
| [guide/CONTRIBUTOR_GUIDE.md](guide/CONTRIBUTOR_GUIDE.md) | How to use AI responsibly for contributions |

## Projects Using This Standard

- [crowdsec-blocklist-import](https://github.com/wolffcatskyy/crowdsec-blocklist-import) — 147 stars, 12 open issues
- [crowdsec-unifi-bouncer](https://github.com/wolffcatskyy/crowdsec-unifi-bouncer) — 13 stars, 10 open issues
- [emby-playback-guardian](https://github.com/wolffcatskyy/emby-playback-guardian) — Playback protection for Emby/Jellyfin
- [wordpress-mcp](https://github.com/wolffcatskyy/wordpress-mcp) — WordPress MCP server for Claude

*Using this standard? Open a PR to add your project here.*

## Background

Inspired by [Fedora's 2025 policy on AI-assisted contributions](https://communityblog.fedoraproject.org/council-policy-proposal-policy-on-ai-assisted-contributions/) which established that AI-assisted contributions are welcome when contributors take responsibility for the output.

This standard takes that a step further: instead of just *allowing* AI contributions, we actively *optimize* for them by structuring issues so AI tools can be maximally effective.

## Philosophy

The bottleneck in open source isn't talent — it's context. A skilled developer can fix most bugs in most projects, but they'd need hours just to understand the codebase enough to attempt it.

AI assistants are good at taking structured context and producing working code. Humans are good at reviewing, testing, and understanding intent. AI-Ready Issues combine both strengths.

The contributor still needs to:
- Understand what the code does
- Test it in their environment
- Take responsibility for what they submit
- Disclose that AI was used

The AI just gets them past the blank-page problem.

## Contributing

This standard itself is open for contributions. If you have ideas for improving the templates, workflow, or documentation, open an issue or PR.

## License

MIT — use these templates in any project, commercial or open source.
