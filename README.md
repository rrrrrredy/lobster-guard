# lobster-guard

AI Agent identity security guard for group chats — prevent identity spoofing, privacy leaks, and prompt injection.

> OpenClaw Skill — works with [OpenClaw](https://github.com/openclaw/openclaw) AI agents

## What It Does

Protects your AI agent from being exploited by non-owner users in group chats and multi-user scenarios. It implements a 3-tier identity verification system (confirmed owner / uncertain / confirmed non-owner) based on chat metadata, blocks all sensitive operations for non-owners, and defends against prompt injection attacks. Pure configuration skill — no runtime dependencies, just paste the config snippet into your SOUL.md or AGENTS.md.

## Quick Start

```bash
openclaw skill install lobster-guard
# Or:
git clone https://github.com/rrrrrredy/lobster-guard.git ~/.openclaw/skills/lobster-guard
```

## Features

- **3-tier identity verification**: Confirmed owner → full access; uncertain → cautious mode; non-owner → hard reject
- **Sensitive operation blacklist**: SSO/MOA login, internal system access, file reads, message forwarding, browser usage, sub-agent spawning
- **Prompt injection defense**: Ignores hidden instructions in images/filenames/links; rejects "ignore all previous instructions" attacks
- **Unified rejection phrasing**: Never exposes capability boundaries to attackers
- **Platform-agnostic**: Works on DaXiang, Telegram, Discord — any platform with chat_id metadata
- **Zero runtime overhead**: Pure config snippet, no API calls or scripts

## Usage

Trigger by mentioning: `安全`, `隐私`, `保护`, `身份验证`, `授权`, `龙虾安全`, `群聊隔离`, `agent安全`, `配置安全规则`

**Setup:**
1. Find your owner user ID from OpenClaw inbound metadata (`chat_id: "user:12345678"`)
2. Paste the config snippet from SKILL.md into your SOUL.md or AGENTS.md
3. Replace `YOUR_OWNER_ID` with your actual ID

## Project Structure

```
lobster-guard/
├── SKILL.md                          # Main skill documentation & config template
└── references/
    └── identity-verification.md      # Identity verification reference
```

## Requirements

- OpenClaw agent runtime
- Owner's `chat_id` from platform metadata

## License

[MIT](LICENSE)
