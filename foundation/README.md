# Foundation Data

Provides customer-record lookup and write-back for the other expert kits — when a record is found, answers get sharper; when not found, silently continue. Support, never the star.

## Capabilities

- Customer (company) record lookup: search + full-stack detail
- Query and write-back for contacts / deals / activities / documents
- Self-service connector guidance when the channel is blocked (not installed / not authorized)
- Write-side information quality gate (redacted / incomplete / inferred data is never written)

## Skills

| Skill | Description |
|---|---|
| DealCenter customer records | Look up and write back customer (company/deal/contact/activity/document) background; silently continue when not found, write only on explicit user confirmation |

## MCP enhancement

- **OmniMay MCP (DealCenter)**: provides tools such as `dealcenter.account.*` / `dealcenter.contact.*` / `dealcenter.deal.*` / `dealcenter.activity.*` / `dealcenter.doc.*`. Configure it on the Claude Code connectors page (see [SKILL.md](dealcenter/SKILL.md)).
