# opencode-discord-notification

OpenCode plugin that sends Discord notifications on session completion and permission requests.

![Example Notification](screenshots/example.png)

## Features

- ✅ **Completion Notifications:** Get a Discord message when OpenCode finishes a long task.
- 📊 **Context Stats:** Includes context usage percentage and total tokens.
- 🤖 **Model Info:** Shows which model was used for the response.
- ⚠️ **Permission Alerts:** Real-time notifications when OpenCode is blocked waiting for terminal permissions, including the command it's trying to run.

## Installation

Add it to your `opencode.json`:

```json
{
  "plugin": ["opencode-discord-notification@0.1.1"]
}
```

## Configuration

Create a configuration file at `~/.config/opencode/discord-notification-config.json`:

```json
{
  "enabled": true,
  "webhookUrl": "https://discord.com/api/webhooks/...",
  "username": "OpenCode Notifier",
  "avatarUrl": "https://opencode.ai/logo.png"
}
```

You can optionally include a `mention` entry (for example `"<@123456789012345678>"`) to ping a Discord user or role whenever a notification fires.

### Config Reference for Kilo

When running under Kilo (Kilo CLI 1.0 from Kilo-Org/kilo), configuration is managed through `/connect` for provider setup, the `~/.config/kilo/` files, and `kilo auth` for credentials. Kilo merges `config.json`, `opencode.json`, and `opencode.jsonc`, so place provider, model, permission, and MCP values in `opencode.json` (or `opencode.jsonc`) there and restart the CLI after editing. You can also keep the snippet above in `~/.config/opencode/discord-notification-config.json` if you need to work around schema validation.

## Development

1. Clone the repo.
2. Install dependencies: `bun install`.
3. Type-check: `bun x tsc`.

## License

MIT
