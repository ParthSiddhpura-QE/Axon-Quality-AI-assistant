# Quality Engineering Assistant — M365 Copilot Declarative Agent

The QES agent for Microsoft 365 Copilot. **No backend, no API keys, no code** — the agent runs entirely on the user's own M365 Copilot. This is the M365 equivalent of the ChatGPT custom GPT and the Claude.ai project instructions.

## What the user needs

- A Microsoft 365 account with a **Microsoft 365 Copilot license**
- That's it — no Copilot Studio, no Azure, no configuration

## Package contents

| File | Purpose |
|------|---------|
| `manifest.json` | Teams app manifest (v1.19) — identity, icons, publisher info |
| `declarativeAgent.json` | The agent itself — instructions, modes, conversation starters |
| `color.png` | 192×192 color icon |
| `outline.png` | 32×32 outline icon |

## Build the app package

Zip the four files (flat, no folder inside the zip):

```powershell
Compress-Archive -Path manifest.json, declarativeAgent.json, color.png, outline.png -DestinationPath qes-agent.zip -Force
```

```bash
zip -j qes-agent.zip manifest.json declarativeAgent.json color.png outline.png
```

## Distribution options

### Option 1 — Sideload (testing, single user)

1. Open Teams → **Apps** → **Manage your apps** → **Upload an app** → **Upload a custom app**
2. Select `qes-agent.zip`
3. The agent appears in M365 Copilot under **Agents**

> Requires custom app upload to be enabled by the tenant admin
> (Teams admin center → Teams apps → Setup policies → "Upload custom apps").

### Option 2 — Organization catalog (whole company)

The IT admin uploads `qes-agent.zip` in the **Teams admin center** → **Teams apps** → **Manage apps** → **Upload new app**. Every user in the tenant can then install the agent from the company app store.

### Option 3 — AppSource (public, anyone can install)

1. Create a [Partner Center](https://partner.microsoft.com/) developer account (one-time registration fee)
2. Submit `qes-agent.zip` as a new **Microsoft 365 and Copilot** offer
3. Microsoft validates the package (typically 3–10 business days)
4. Once approved, the agent is listed publicly — any M365 Copilot user can install it

## Validate before submitting

Use the Microsoft 365 Agents Toolkit (VS Code extension) or the
[Teams app validation tool](https://dev.teams.microsoft.com/validation) to lint the package before sideloading or submitting to AppSource.

## Updating the agent

1. Edit `declarativeAgent.json` (instructions, starters) or `manifest.json`
2. Bump `version` in `manifest.json` (semver)
3. Re-zip and re-upload (sideload/org catalog) or submit an update (AppSource)

## Note on the API plugin (advanced, optional)

The files in the parent folder (`openapi.yaml`, `plugin-manifest.json`, `worker.js`, `wrangler.toml`) are an **optional self-hosted API plugin** — a different architecture where requests are served by your own Cloudflare Worker calling the Anthropic API at your cost. Most users should ignore it and use this declarative agent instead. See `../setup-guide.md`.
