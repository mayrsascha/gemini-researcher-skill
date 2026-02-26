# Gemini Deep Research Skill

Turn a one-liner into an expert research prompt. Ask your coding agent what you need researched, get a structured prompt on your clipboard, paste into Gemini, get results grounded in your actual project.

## Why not just ask Gemini directly?

You can — but you'll write something like:

> "best payment provider for my app"

And get a generic listicle. This skill takes that same request, pulls in your project context (React + Node, already using Stripe for subscriptions, need marketplace payouts, PCI compliance matters), and generates this:

<details>
<summary><strong>See generated prompt</strong></summary>

> Research the current landscape of payment processing solutions suitable for a web application with the following technical context: the application is built with React and Node.js, already integrates Stripe for subscription billing, and now needs to add marketplace-style payouts to multiple sellers.
>
> Investigate the following angles:
>
> 1. Extending Stripe Connect vs. adopting a dedicated marketplace payment platform (e.g., Paypal for Marketplaces, Adyen for Platforms, Mangopay, Trolley). For each, cover: onboarding complexity for sellers, payout flexibility (scheduling, currency, method), fraud and dispute handling, and PCI compliance implications.
> 2. Evaluate solutions that can coexist with an existing Stripe subscription integration without requiring a full migration — hybrid setups where subscriptions stay on Stripe but payouts go through another provider.
> 3. Pricing models and fee structures for a marketplace processing $50K-500K/month in gross merchandise volume across 50-200 sellers. Include both percentage-based and flat-fee tiers.
> 4. Developer experience: quality of SDKs and APIs for Node.js, webhook reliability, sandbox/testing environments, and documentation quality.
> 5. Regulatory considerations for marketplace payments in the US and EU — money transmission licensing, KYC/AML requirements, and which providers handle this on your behalf vs. requiring you to manage it.
>
> Deliver the output as a structured markdown report with a recommendation matrix comparing the top 5 options across the dimensions above. Include specific API endpoint examples where relevant and link to official documentation. Conclude with a ranked recommendation based on the described use case.

</details>

That prompt gets Gemini to produce a 15-page report tailored to your exact situation, not a generic overview.

## Install

```bash
npx skills add mayrsascha/gemini-researcher-skill
```

Works with Claude Code, Cursor, GitHub Copilot, Cline, and [18+ other agents](https://skills.sh).

### Manual install (Claude Code)

Copy `skills/gemini-researcher/SKILL.md` to `~/.claude/skills/gemini-researcher/SKILL.md`.

## How it works

1. You describe what you need researched
2. The skill reads your project context — tech stack, frameworks, constraints, what you're building
3. It crafts a detailed Deep Research prompt with clear objectives, investigation angles, and output format
4. The prompt is copied to your clipboard (macOS, Linux, Windows/WSL)
5. You paste into [gemini.google.com](https://gemini.google.com) and hit "Deep Research"

If no clipboard tool is available, it prints the prompt to stdout for manual copying.

## Requirements

- [Gemini Deep Research](https://gemini.google.com) access

## License

MIT
