# omnimay skills

> Omnimay sales AI assistant skill kits — AE / CSM / EDM role experts + foundation data capabilities. An AI assistant for individual salespeople: you speak, the AI sales experts get it done.

Omnimay distills the daily work of sales roles (AE/CSM/EDM) into AI-callable skill kits, covering the full sales cycle from prospecting and signing to renewal and expansion. Every skill follows the standard `SKILL.md` format and works with any AI tool that supports Agent Skills; they are also packaged as plugins for one-click install in Claude Code.

Each skill is a folder (`SKILL.md` + reference material). Once installed into your AI tool, the AI automatically loads the playbook in matching sales scenarios — no prompt writing required.

## What's inside

This repository is a marketplace (`.claude-plugin/marketplace.json`) containing 4 plugins, one per sales-role expert:

| Plugin | Role | What it covers |
|---|---|---|
| [`omnimay-ae-expert`](ae/) | AE (Account Executive) | Deal qualification, visit proposals, contract signing, negotiation & pricing, deal progression |
| [`omnimay-csm-expert`](csm/) | CSM (Customer Success) | Business reviews, renewals, expansion, referrals, churn recovery, advocacy management |
| [`omnimay-edm-expert`](edm/) | EDM (cold outreach) | ICP calibration, company search, lead enrichment, cold email writing, account-entry research |
| [`omnimay-foundation`](foundation/) | Foundation data | DealCenter customer-record lookup & write-back (requires MCP) |

4 plugins, 17 skills in total.

## Installation

### Option 1: Claude Code (plugin install)

```bash
# Run inside Claude Code
/plugin marketplace add omnimay/skills

# Pick the plugins you want
/plugin install omnimay-ae-expert
/plugin install omnimay-csm-expert
/plugin install omnimay-edm-expert
/plugin install omnimay-foundation
```

### Option 2: Universal (any AI tool that supports SKILL.md)

```bash
git clone https://github.com/omnimay/skills.git
```

Copy the `<plugin>/skills/<skill>/` folders you need into your tool's skills directory. Claude Code users can also install locally: run `/plugin marketplace add .` inside the repo, then `/plugin install omnimay-ae-expert`.

> The flat `skills/<name>/` folders at the repo root are plain SKILL.md copies of all 17 skills (for `npx skills add` and tools that read SKILL.md directly); `<plugin>/skills/<name>/` is the plugin packaging. Both are identical in content. Use Option 1 to install plugins, or copy individual skills from `skills/<name>/`.

After installation, each skill registers automatically via its `SKILL.md` `description`, and the AI invokes it in matching scenarios.

## MCP enhancement (optional)

The `dealcenter` skill in the `foundation` plugin depends on an external MCP. Configure it in your tool's MCP connectors page before use:

| Plugin | MCP | Purpose |
|---|---|---|
| `foundation` | OmniMay MCP (DealCenter) | Customer-record lookup & write-back |

Without the MCP configured, the skill degrades gracefully (no errors, no blocking).

## License & notices

MIT — see [LICENSE](LICENSE). Some skills reference methodologies from third-party open-source projects; sources and copyright notices are listed in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

**Disclaimer**: This repository provides sales methodology references, not legal advice. For scenarios involving data acquisition and outbound reach-out (prospect list building, email enrichment, cold email, etc.), users are responsible for data compliance and personal-information protection (e.g. PIPL, advertising law, and target-platform terms of service). Third-party services mentioned (e.g. Qichacha MCP, DealCenter MCP) require users' own accounts and authorization and are unaffiliated with this repository.

## Feedback

Feel free to open an [Issue](https://github.com/omnimay/skills/issues) for problems or suggestions, or submit a PR to contribute a skill.
