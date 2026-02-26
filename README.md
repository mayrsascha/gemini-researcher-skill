# Gemini Deep Research Skill

An agent skill that generates optimized prompts for [Google Gemini Deep Research](https://gemini.google.com) and copies them to your clipboard. It reads your project context (tech stack, frameworks, open files) and crafts a structured, context-aware prompt designed to get the most out of Gemini's Deep Research mode.

## How it works

1. You describe a research topic to your AI agent
2. The skill pulls in relevant project context (tech stack, constraints, what you're building)
3. It transforms your request into a detailed, context-aware Deep Research prompt
4. The prompt is copied to your clipboard
5. You paste it into Gemini web and run Deep Research

This bridges the gap between your coding agent and Gemini's deep research capabilities — letting you stay in your terminal while offloading heavy research to Gemini. Because the prompt includes your project context, the research output is directly applicable to what you're actually building.

## Install

```bash
npx skills add mayrsascha/gemini-researcher-skill
```

Or install for a specific agent:

```bash
npx skills add mayrsascha/gemini-researcher-skill -a claude-code
```

### Manual install (Claude Code)

Copy `skills/gemini-researcher/SKILL.md` to `~/.claude/skills/gemini-researcher/SKILL.md`.

## Requirements

- **macOS, Linux, or Windows/WSL** — auto-detects clipboard command (`pbcopy`, `xclip`, `wl-copy`, or `clip.exe`)
- **Gemini Deep Research** access at [gemini.google.com](https://gemini.google.com)

## Example

> "Research the current state of WebAssembly for server-side applications — performance benchmarks, production adoption, and comparison with native binaries"

The skill generates a ~200 word structured prompt with clear objectives, specific investigation angles, and output format requirements, then copies it to your clipboard ready to paste into Gemini.

## Compatible agents

Works with any agent that supports the [agent skills](https://skills.sh) standard, including Claude Code, Cursor, GitHub Copilot, Cline, and others.

## License

MIT
