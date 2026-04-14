# lobster-guard

AI Agent identity security guard — prevents non-owner identity spoofing, privacy leaks, and prompt injection in group chats.

An [OpenClaw](https://github.com/openclaw/openclaw) Skill for protecting AI agents in multi-user/group-chat scenarios.

## Installation

### Option A: OpenClaw (recommended)
```bash
# Clone to OpenClaw skills directory
git clone https://github.com/rrrrrredy/lobster-guard ~/.openclaw/skills/lobster-guard
```

### Option B: Standalone
```bash
git clone https://github.com/rrrrrredy/lobster-guard
cd lobster-guard
```

## Dependencies

No additional dependencies. This is a configuration-only skill — it provides a security policy template to paste into your agent's SOUL.md or AGENTS.md.

## Usage

1. **Find your owner user ID** from OpenClaw inbound metadata (`chat_id` field)
2. **Paste the security config** from SKILL.md into your SOUL.md or AGENTS.md
3. **Replace `YOUR_OWNER_ID`** with your actual user ID
4. Done — the agent now enforces identity verification on every message

### Key Features
- **Three-level identity verification**: confirmed owner / uncertain / confirmed non-owner
- **Sensitive operation blocklist**: SSO login, internal system access, file reading, message sending
- **Anti-prompt-injection**: ignores hidden instructions in images/filenames/links
- **Unified rejection phrasing**: doesn't reveal capability boundaries

## Project Structure

```
lobster-guard/
├── SKILL.md                           # Main skill definition + config template
├── references/
│   └── identity-verification.md       # Detailed identity verification guide
└── README.md
```

## License

MIT
