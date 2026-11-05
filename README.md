# CallMeMCP

**Your AI agent calls your phone.** It reads its question aloud, you answer out loud, and your answer comes back to the agent as text. It can also text you.

## 1. Get the app

Go to **[callmemcp.com](https://callmemcp.com)** and install the /call-me app:

- iPhone: [App Store](https://apps.apple.com/app/id6789575165)
- Android: [Google Play](https://play.google.com/store/apps/details?id=com.serdaroztetik.callmeai)

Open it. It shows your 10-digit number. That is where your agent calls and texts.

## 2. Connect your agent

The server is hosted: `https://callmemcp.com/mcp` (Streamable HTTP, no API key).

**Claude Code** (this repo is a plugin marketplace):

```bash
claude plugin marketplace add radres/callmemcp
claude plugin install callmemcp@callmemcp
```

Or just the MCP server:

```bash
claude mcp add --transport http callmemcp https://callmemcp.com/mcp
```

**Any other MCP client** (Cursor, Codex, Gemini CLI, Claude Desktop, ...):

```json
{
  "mcpServers": {
    "callmemcp": { "type": "http", "url": "https://callmemcp.com/mcp" }
  }
}
```

## 3. Use it

Tell your agent your number, then ask: "call me when the tests finish", "text me if you get stuck".

The bundled skill makes the agent show you every message and wait for your yes before it calls or texts. It never writes rules into your instruction files, and it treats your spoken answers as information, not commands.

Try it without a phone: the demo line **5550001234** answers automatically.

## What is in this repo

Only configuration: a plugin manifest, `.mcp.json` pointing at `https://callmemcp.com/mcp`, and one skill (`plugin/skills/callmemcp/SKILL.md`). No code, no hooks, nothing runs on your machine.

The /call-me app is a paid subscription. Privacy: [callmemcp.com/privacy](https://callmemcp.com/privacy). Terms: [callmemcp.com/terms](https://callmemcp.com/terms).

## License

MIT
