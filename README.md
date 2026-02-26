# Deep Research Skill

Turn a one-liner into an expert research prompt. Ask your coding agent what you need researched, get a structured, context-aware prompt on your clipboard, paste into your preferred deep research tool.

## Why not just ask directly?

You can — but you'll write something like:

> "best payment provider for my app"

And get a generic listicle. This skill takes that same request, pulls in your project context (React + Node, already using Stripe for subscriptions, need marketplace payouts, PCI compliance matters), and generates this:

<details>
<summary><strong>See generated prompt</strong></summary>

> ## Objective
> Research the current landscape of payment processing solutions suitable for a marketplace web application that already uses Stripe for subscription billing and now needs to add multi-seller payouts.
>
> ## Context
> The application is built with React and Node.js. Stripe is integrated for recurring subscription billing. The platform needs to onboard 50-200 sellers and process $50K-500K/month in gross merchandise volume. PCI compliance is a hard requirement. The team prefers solutions with strong Node.js SDKs.
>
> ## Investigate
> 1. Extending Stripe Connect vs. adopting a dedicated marketplace payment platform (Paypal for Marketplaces, Adyen for Platforms, Mangopay, Trolley) — onboarding complexity, payout flexibility, fraud handling, PCI implications for each
> 2. Hybrid setups where subscriptions stay on Stripe but payouts go through another provider — feasibility and trade-offs
> 3. Pricing models and fee structures at the described transaction volume — percentage-based vs. flat-fee tiers
> 4. Developer experience — SDK quality for Node.js, webhook reliability, sandbox environments, documentation
> 5. Regulatory considerations for marketplace payments in the US and EU — money transmission licensing, KYC/AML, and which providers handle this on your behalf
>
> ## Output Format
> Structured markdown report with a recommendation matrix comparing the top 5 options across all dimensions above. Include API examples where relevant and link to official docs. Conclude with a ranked recommendation for this use case.
>
> ## Constraints
> Exclude solutions that require migrating existing Stripe subscription billing. Focus on providers with production-ready Node.js SDKs.

</details>

That prompt gets a deep research tool to produce a report tailored to your exact situation, not a generic overview.

## Install

```bash
npx skills add mayrsascha/deep-research-skill
```

Works with Claude Code, Cursor, GitHub Copilot, Cline, and [18+ other agents](https://skills.sh).

### Manual install (Claude Code)

Copy `skills/deep-research/SKILL.md` to `~/.claude/skills/deep-research/SKILL.md`.

## How it works

1. You describe what you need researched
2. The skill reads your project context — tech stack, frameworks, constraints, what you're building
3. It crafts a structured prompt with objectives, context, investigation angles, and output format
4. The prompt is copied to your clipboard (macOS, Linux, Windows/WSL)
5. You paste into your preferred tool — Gemini Deep Research, Perplexity, ChatGPT, or any deep research mode

Ask to refine and it adjusts the previous prompt without regenerating from scratch.

If no clipboard tool is available, it prints the prompt to stdout for manual copying.

## Requirements

- A deep research tool: [Gemini](https://gemini.google.com), [Perplexity](https://perplexity.ai), [ChatGPT](https://chatgpt.com), or similar

## License

MIT
