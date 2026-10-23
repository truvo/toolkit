<h1 align="center"><a href="https://www.truvo.com"><img src="assets/truvo-header.svg" alt="Truvo" width="300"></a></h1>

<p align="center">Get real car, renters, and pet insurance quotes from 50+ carriers. Truvo is an independent insurance agency, licensed in all 50 states and D.C.</p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/github/license/truvo/toolkit?label=License&labelColor=1E2C0C&color=86B621" alt="License"></a>
  <a href="https://github.com/truvo/toolkit/tags"><img src="https://img.shields.io/github/v/tag/truvo/toolkit?sort=semver&label=Release&labelColor=1E2C0C&color=86B621" alt="Release"></a>
  <a href="https://registry.modelcontextprotocol.io/?q=com.truvo%2Fmcp"><img src="https://img.shields.io/badge/MCP_Registry-com.truvo%2Fmcp-86B621?logo=modelcontextprotocol&logoColor=white&labelColor=1E2C0C" alt="MCP Registry"></a>
</p>

<p align="center">
  <a href="#claude-code"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/install-claude-code-light.svg"><img src="assets/install-claude-code-dark.svg" alt="Add to Claude Code" height="28"></picture></a>
  <a href="#codex"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/install-codex-light.svg"><img src="assets/install-codex-dark.svg" alt="Add to Codex" height="28"></picture></a>
  <a href="https://cursor.com/en/install-mcp?name=truvo&config=eyJ1cmwiOiJodHRwczovL2FwaS50cnV2by5jb20vdjEvbWNwIn0%3D"><picture><source media="(prefers-color-scheme: dark)" srcset="https://cursor.com/deeplink/mcp-install-light.svg"><img src="https://cursor.com/deeplink/mcp-install-dark.svg" alt="Add to Cursor" height="28"></picture></a>
  <a href="https://vscode.dev/redirect?url=vscode%3Amcp%2Finstall%3F%257B%2522name%2522%253A%2522truvo%2522%252C%2522type%2522%253A%2522http%2522%252C%2522url%2522%253A%2522https%253A%252F%252Fapi.truvo.com%252Fv1%252Fmcp%2522%257D"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/install-vscode-light.svg"><img src="assets/install-vscode-dark.svg" alt="Add to VS Code" height="28"></picture></a>
</p>

Follow the instructions below to add Truvo to your coding agent. Want to connect ChatGPT, Muse, or another personal assistant? See <a href="https://www.truvo.com/ai">truvo.com/ai</a>.

- [Set up](#set-up)
  - [Claude Code](#claude-code)
  - [Codex](#codex)
  - [Cursor](#cursor)
  - [VS Code and GitHub Copilot](#vs-code-and-github-copilot)
  - [GitHub Copilot CLI](#github-copilot-cli)
  - [Visual Studio](#visual-studio)
  - [Antigravity](#antigravity)
  - [Gemini CLI](#gemini-cli)
  - [Grok Build](#grok-build)
  - [Devin](#devin)
  - [Zed](#zed)
  - [Kiro](#kiro)
  - [Cline](#cline)
  - [Kilo Code](#kilo-code)
  - [Junie](#junie)
  - [Warp](#warp)
  - [Factory Droid](#factory-droid)
  - [Goose](#goose)
  - [Amp](#amp)
  - [opencode](#opencode)
  - [OpenClaw](#openclaw)
  - [Hermes Agent](#hermes-agent)
  - [Other clients](#other-clients)
- [Get started](#get-started)
- [Tools](#tools)
- [What's in this repo](#whats-in-this-repo)
- [For businesses](#for-businesses)
- [Support](#support)
- [Privacy](#privacy)
- [License](#license)

## Set up

Add the Truvo MCP server, `https://api.truvo.com/v1/mcp`. It signs in with OAuth: your client opens Truvo's sign-in page in your browser.

### Claude Code

```text
/plugin marketplace add truvo/toolkit
/plugin install truvo@truvo
```

Then run `/mcp` in a session and select the Truvo server to sign in with Truvo in your browser.

Or add the server without the plugin:

```text
claude mcp add --transport http truvo https://api.truvo.com/v1/mcp
claude mcp login truvo
```

### Codex

```text
codex plugin marketplace add truvo/toolkit
codex plugin add truvo@truvo
```

Or add the server without the plugin:

```text
codex mcp add truvo --url https://api.truvo.com/v1/mcp
codex mcp login truvo
```

Or add this to `~/.codex/config.toml`:

```toml
[mcp_servers.truvo]
url = "https://api.truvo.com/v1/mcp"
```

Then sign in with Truvo:

```text
codex mcp login truvo
```

In the ChatGPT desktop app, open **Settings**, then select **MCP servers**. In the IDE extension, open the gear menu, then select **MCP servers**. Add `https://api.truvo.com/v1/mcp` and sign in with Truvo.

### Cursor

Install the Truvo plugin from the Cursor Marketplace, open the **Add to Cursor** link above, or add this to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "truvo": {
      "url": "https://api.truvo.com/v1/mcp"
    }
  }
}
```

Cursor opens your browser so you can sign in with Truvo.

### VS Code and GitHub Copilot

Add this to `.vscode/mcp.json` in your workspace:

```json
{
  "servers": {
    "truvo": {
      "type": "http",
      "url": "https://api.truvo.com/v1/mcp"
    }
  }
}
```

Or open the **Add to VS Code** link above, or run **MCP: Add Server** from the Command Palette.

The first time VS Code connects to Truvo, it opens your browser so you can sign in with Truvo.

### GitHub Copilot CLI

```text
copilot plugin install truvo/toolkit
```

Or add the server without the plugin:

```text
copilot mcp add --transport http truvo https://api.truvo.com/v1/mcp
```

Or add this to `~/.copilot/mcp-config.json`:

```json
{
  "mcpServers": {
    "truvo": {
      "type": "http",
      "url": "https://api.truvo.com/v1/mcp"
    }
  }
}
```

Then run `/mcp auth truvo` in Copilot CLI to sign in with Truvo.

### Visual Studio

Add this to `%USERPROFILE%\.mcp.json`:

```json
{
  "servers": {
    "truvo": {
      "url": "https://api.truvo.com/v1/mcp"
    }
  }
}
```

Then select the **Authentication Required** CodeLens in the file and sign in with Truvo.

### Antigravity

Add this to `~/.gemini/config/mcp_config.json`, or to `.agents/mcp_config.json` in your workspace:

```json
{
  "mcpServers": {
    "truvo": {
      "serverUrl": "https://api.truvo.com/v1/mcp"
    }
  }
}
```

Then open Agent settings, go to the **Customizations** tab, and select **Authenticate** next to Truvo. Sign in with Truvo in your browser, copy the authorization code, paste it back into the settings panel, and select **Submit**.

### Gemini CLI

```text
gemini extensions install https://github.com/truvo/toolkit
```

Or add the server without the extension:

```text
gemini mcp add -s user --transport http truvo https://api.truvo.com/v1/mcp
```

Then run `/mcp auth truvo` in Gemini CLI to sign in with Truvo.

### Grok Build

```text
grok mcp add --transport http truvo https://api.truvo.com/v1/mcp
```

Grok Build then starts the sign-in with Truvo.

### Devin

Devin Desktop (formerly Windsurf): add this to `~/.config/devin/mcp_config.json` (Windows: `%APPDATA%\devin\mcp_config.json`):

```json
{
  "mcpServers": {
    "truvo": {
      "url": "https://api.truvo.com/v1/mcp"
    }
  }
}
```

Devin CLI:

```text
devin mcp add truvo https://api.truvo.com/v1/mcp
devin mcp login truvo
```

### Zed

Settings → AI → MCP Servers → Add Server → Add Remote Server, or add this to settings:

```json
{
  "context_servers": {
    "truvo": {
      "url": "https://api.truvo.com/v1/mcp"
    }
  }
}
```

Zed then asks you to sign in with Truvo.

### Kiro

Add this to `.kiro/settings/mcp.json` or `~/.kiro/settings/mcp.json`:

```json
{
  "mcpServers": {
    "truvo": {
      "url": "https://api.truvo.com/v1/mcp"
    }
  }
}
```

### Cline

```text
cline mcp add truvo https://api.truvo.com/v1/mcp --transport http
```

Or add this to the MCP settings file:

```json
{
  "mcpServers": {
    "truvo": {
      "type": "streamableHttp",
      "url": "https://api.truvo.com/v1/mcp"
    }
  }
}
```

To sign in with Truvo, run `cline mcp` and select **Authorize OAuth**.

### Kilo Code

Add this to `~/.config/kilo/kilo.jsonc`:

```jsonc
{
  "mcp": {
    "truvo": {
      "type": "remote",
      "url": "https://api.truvo.com/v1/mcp"
    }
  }
}
```

Kilo Code starts the sign-in with Truvo when it connects.

### Junie

Run `/mcp` and open the MCP Installation Assistant. Add `https://api.truvo.com/v1/mcp`, then select **Authorize** to sign in with Truvo.

### Warp

Go to **Settings › Agents › MCP servers**, select **+ Add**, then **Streamable HTTP or SSE Server (URL)**, and enter `https://api.truvo.com/v1/mcp`. When the server starts, Warp opens your browser so you can sign in with Truvo.

### Factory Droid

```text
droid mcp add truvo https://api.truvo.com/v1/mcp --type http
```

Then run `/mcp` to sign in with Truvo in your browser.

### Goose

Open this link:

```text
goose://extension?url=https%3A%2F%2Fapi.truvo.com%2Fv1%2Fmcp&type=streamable_http&id=truvo&name=Truvo&description=Get%20real%20car%2C%20renters%2C%20and%20pet%20insurance%20quotes%20from%2050%2B%20carriers
```

Or add this to `~/.config/goose/config.yaml` (Windows: `%APPDATA%\Block\goose\config\config.yaml`):

```yaml
extensions:
  truvo:
    type: streamable_http
    name: truvo
    enabled: true
    uri: "https://api.truvo.com/v1/mcp"
```

Or start a session with:

```text
goose session --with-streamable-http-extension "https://api.truvo.com/v1/mcp"
```

### Amp

```text
amp mcp add truvo https://api.truvo.com/v1/mcp
```

The next time you start Amp, it opens Truvo's sign-in page in your browser.

### opencode

Add this to `opencode.json`:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "truvo": {
      "type": "remote",
      "url": "https://api.truvo.com/v1/mcp"
    }
  }
}
```

Then run `opencode mcp auth truvo` to sign in with Truvo in your browser.

### OpenClaw

Stop the gateway, then run:

```text
openclaw mcp add truvo --url https://api.truvo.com/v1/mcp --transport streamable-http --auth oauth
openclaw mcp login truvo
```

Or in the Control UI, go to **Settings › MCP › Add server**.

### Hermes Agent

Add this to `~/.hermes/config.yaml`:

```yaml
mcp_servers:
  truvo:
    url: "https://api.truvo.com/v1/mcp"
    auth: oauth
```

Then run `hermes mcp login truvo` to sign in with Truvo. On a machine without a browser, add `--flow device`.

### Other clients

Add `https://api.truvo.com/v1/mcp` as a remote MCP server. If the client asks for a transport, choose Streamable HTTP. The server signs in with OAuth, so the client opens Truvo's sign-in page.

## Get started

Truvo is an independent insurance agency, licensed in all 50 states and D.C. Sign in, and your assistant can get you real car, renters, and pet insurance quotes from 50+ carriers, in your chat.

The MCP server runs the same operations as the Truvo API. Check what a line needs with `get_capabilities`, start a request with `start_quote_request`, and read each carrier's answer with `get_quote_request` and `get_quote`. `list_quote_requests` lists the requests you started while signed in. Every caller can send feedback with `send_feedback`.

1. "Get me renters quotes for my apartment in Austin, Texas."
2. "Show me the car insurance quotes I started with Truvo."
3. "Get pet insurance quotes for my dog."

A quote is a price offer, not coverage.

## Tools

| Tool | What it does | Who sees it |
| --- | --- | --- |
| `get_capabilities` | Shows the states, the required facts, and the possible actions for auto, renters, or pet. Reads only. | Every caller |
| `request_callback` | Queues a call back from Truvo's advisor line, open 24/7. | Signed-in people and Truvo platform accounts |
| `start_quote_request` | Starts one quote request for one person and one line. Carriers answer in the background. | Every caller |
| `get_quote_request` | Reads the request's status and each carrier's result. While the request is in progress, it waits up to 20 seconds for a change; `wait_seconds` (0 to 20) sets the wait. Starts no new quote. | Every caller |
| `get_quote` | Reads one quote: carrier, price, coverage, expiry, assumptions, and next actions. | Every caller |
| `list_quote_requests` | Lists your quote requests, newest first. | Signed-in people and Truvo platform accounts |
| `send_feedback` | Tells Truvo how a quote went, or reports a bug, a missing feature, or an unclear error. | Every caller |
| `list_api_requests` | Shows how your recent calls ended, with error codes. | Truvo platform accounts |
| `send_test_event` | Queues a test event for one of your webhook subscriptions. | Truvo platform accounts |
| `list_event_deliveries` | Lists one webhook subscription's deliveries from the last 30 days, newest first. | Truvo platform accounts |
| `get_event_delivery` | Reads one webhook delivery and its attempts. | Truvo platform accounts |
| `replay_event_delivery` | Sends one event from a subscription's delivery log again. | Truvo platform accounts |
| `get_event_subscription_health` | Shows whether delivery to one webhook subscription works. | Truvo platform accounts |

## What's in this repo

| Path | What it does |
| --- | --- |
| `.mcp.json` | Connects to `https://api.truvo.com/v1/mcp` |
| `mcp.json` | Connects Cursor to the same server |
| `skills/truvo-quotes/` | A skill that tells the agent how to get your quotes |
| `skills/truvo-api/` | A skill that tells the agent how to add Truvo quotes to an app |
| `.claude-plugin/` | The Claude Code plugin and the `truvo` marketplace |
| `.cursor-plugin/` | The Cursor plugin |
| `.agents/plugins/` | The Codex marketplace |
| `.codex-plugin/` | The Codex plugin |
| `gemini-extension.json` | The Gemini CLI extension |
| `server.json` | The MCP Registry entry |
| `SECURITY.md` | How to report a security problem |

## For businesses

To build Truvo quotes into your product, create a sandbox API key on the [Keys](https://partners.truvo.com/developers) page of the portal, and follow [Build a platform integration](https://docs.truvo.com/guides/connect-your-ai-agent#build-a-platform-integration). Sandbox keys start with `trv_sandbox_`. Keep the key out of prompts, chats, and any file you commit. The `truvo-api` skill covers that path.

## Support

Write to [support@truvo.com](mailto:support@truvo.com).

## Privacy

This plugin is configuration and skills, with no code of its own. It connects your agent to one server, `https://api.truvo.com/v1/mcp`, and sends only the requests your agent makes with the Truvo tools, after you sign in. Truvo handles that data under its [privacy notice](https://www.truvo.com/privacy).

## License

MIT. See [LICENSE](LICENSE).
