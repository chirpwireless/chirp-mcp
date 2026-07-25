# Chirp Home Automation MCP Server

[![smithery badge](https://smithery.ai/badge/chirp/chirp-home-automation)](https://smithery.ai/servers/chirp/chirp-home-automation)

Point the AI app you already talk to at your own home. Ask which sensors have gone quiet, what set off
last night's alert, how cold the garage got — and tell it to do something about it.

The server is hosted by [Chirp](https://chirpwireless.io). Nothing to install, no key to generate or
paste: you sign in with your usual Chirp account in the browser, once.

```
https://mcp-auth.chirpwireless.io/mcp
```

This repository holds the public metadata for that server — its registry manifest, its icon, and the
setup steps below. The service itself is closed-source.

## What is MCP?

[MCP](https://modelcontextprotocol.io) is a shared way for an AI app to reach out and use something
else safely. Chirp speaks it, so the app you already use can talk to your home with no custom plumbing
— Claude Code, Claude Desktop, ChatGPT, Codex, Cursor and more.

## What can your AI app do with your home?

| Area | What it can do |
|---|---|
| **Sensors** | List the sensors in your home, see their details and readings, add a new one — a LoRaWAN sensor or a tracker — from the available profiles |
| **Control** | Send a command to a device, and check that it went through |
| **Connections** | See how your home is connected, and set up a connection for a new sensor |
| **Automations** | Go through what you've built, and see what each one actually does |
| **Alerts** | Look at your alerts, summarize what has been triggering and how often, send a test notification to check it lands on your phone |
| **Dashboards** | List your dashboards and pull the data behind a widget, so it can chart or explain a reading |
| **Household** | Look up your home's details and members, invite someone, set what they can see |

Anything that changes something asks you first. Anything that only looks stays out of your way.

## Connecting Claude Code

```bash
claude mcp add --transport http chirp https://mcp-auth.chirpwireless.io/mcp
```

Run `/mcp` inside Claude Code, pick `chirp`, and sign in when the browser opens. Run `/mcp` again and
it shows as connected — then ask it which of your sensors went quiet this week.

## Connecting Claude Desktop, ChatGPT, Cursor or Codex

If your app has a **Connectors**, **Integrations** or **MCP servers** screen, choose whatever it calls
"add a custom server", paste `https://mcp-auth.chirpwireless.io/mcp`, and sign in when the browser
opens.

If it is configured from a file or a terminal instead, add the same address as a **Streamable HTTP**
server. Your app's own documentation will say where that setting lives.

## Which home does it see?

If you only have one home, skip this — it just works.

The plain address follows whichever home is selected in the Chirp app. If you look after a holiday
flat as well as your own place and want each AI client fixed to one, pin it:

```
https://mcp-auth.chirpwireless.io/o/{organizationId}/mcp
```

The ID for a home is in the Chirp web app. You can only connect to a home you're a member of.

## What it can and can't see

Your AI app sees exactly what you see. If something is hidden from you, it's hidden from your
assistant. There's no key to lose, because there is no key — the connection is your own browser
sign-in, and you can end it whenever you like.

## API vs MCP

The [REST API](https://docs.chirpwireless.io/api/) is for code *you* write — a script that exports
readings into a spreadsheet every Sunday, or a bridge to another home platform. It runs on a key you
create, with the scopes you choose. MCP is for asking questions and getting things done in the moment,
as yourself.

## Links

- Chirp: [chirpwireless.io](https://chirpwireless.io)
- Documentation: [docs.chirpwireless.io — MCP Server](https://docs.chirpwireless.io/api/mcp-server)
- Contact: [chirpwireless.io/contact](https://chirpwireless.io/contact/)
- Privacy policy: [chirpwireless.io/privacy-policy](https://chirpwireless.io/privacy-policy/) · Terms: [chirpwireless.io/terms-of-service](https://chirpwireless.io/terms-of-service/)

Two devices are free — start at [chirpwireless.io](https://chirpwireless.io).
