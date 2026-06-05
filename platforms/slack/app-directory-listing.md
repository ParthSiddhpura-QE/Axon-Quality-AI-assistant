# Slack App Directory — Submission Guide

This guide takes you from a deployed Cloudflare Worker to a public listing in the Slack App Directory.

---

## Prerequisites

- Cloudflare account (free): [cloudflare.com](https://cloudflare.com)
- Anthropic API key: [console.anthropic.com](https://console.anthropic.com)
- Slack developer account: [api.slack.com](https://api.slack.com)

---

## Step 1 — Deploy the Cloudflare Worker

### Install Wrangler CLI

```bash
npm install -g wrangler
wrangler login
```

### Deploy

```bash
cd platforms/slack
wrangler deploy
```

Wrangler will output your worker URL, e.g.:
`https://quality-engineering-assistant.YOUR-SUBDOMAIN.workers.dev`

### Set secrets

```bash
wrangler secret put SLACK_SIGNING_SECRET
# paste your Slack signing secret when prompted

wrangler secret put ANTHROPIC_API_KEY
# paste your Anthropic API key when prompted
```

---

## Step 2 — Create the Slack app

1. Go to [api.slack.com/apps](https://api.slack.com/apps) → **Create New App** → **From an app manifest**.
2. Select any workspace for development.
3. Paste the content of `platforms/slack/app-manifest.yaml`.
4. Click **Create**.

---

## Step 3 — Configure slash command URLs

1. In your Slack app, go to **Slash Commands**.
2. For each command (`/8d`, `/fmea`, `/ncr`, `/rca`, `/audit`, `/qe-help`):
   - Click **Edit**.
   - Set **Request URL** to your Cloudflare Worker URL.
   - Click **Save**.

---

## Step 4 — Configure Event Subscriptions

1. Go to **Event Subscriptions** → **Enable Events**.
2. Set **Request URL** to your Cloudflare Worker URL.
3. Under **Subscribe to bot events**, add:
   - `app_mention`
   - `message.im`
4. Click **Save Changes**.

---

## Step 5 — Install and test

1. Go to **Install App** → **Install to Workspace**.
2. Copy the **Bot User OAuth Token** (`xoxb-...`) — you'll need it if you extend the bot later.
3. In Slack, type `/qe-help` — verify the bot responds with the command list.
4. Type `/8d a customer returned parts with incorrect hole diameter` — verify D0 gate starts.
5. Type `/ncr` — verify the bot asks for observations.

---

## Step 6 — Enable public distribution (OAuth)

For the Slack App Directory, you need OAuth so users from any workspace can install the app.

1. In your Slack app, go to **OAuth & Permissions**.
2. Under **Redirect URLs**, add: `https://quality-engineering-assistant.YOUR-SUBDOMAIN.workers.dev/oauth/callback`
3. Update `worker.js` to handle the OAuth callback (add a route for `/oauth/callback` that exchanges the code for a token and stores it).

**Minimal OAuth handler** — add to `worker.js`:

```javascript
// Add inside the fetch handler, before the POST check:
const url = new URL(request.url);

if (url.pathname === '/oauth/callback') {
  const code = url.searchParams.get('code');
  if (!code) return new Response('Missing code', { status: 400 });
  
  const tokenResponse = await fetch('https://slack.com/api/oauth.v2.access', {
    method: 'POST',
    headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
    body: new URLSearchParams({
      client_id: env.SLACK_CLIENT_ID,
      client_secret: env.SLACK_CLIENT_SECRET,
      code,
    }),
  });
  
  const data = await tokenResponse.json();
  if (data.ok) {
    // Store data.access_token in KV for this team
    // For now: redirect to success page
    return Response.redirect('https://github.com/RBraga01/Quality-Engineering-Skills', 302);
  }
  return new Response('OAuth failed', { status: 400 });
}
```

Add two more secrets:
```bash
wrangler secret put SLACK_CLIENT_ID
wrangler secret put SLACK_CLIENT_SECRET
```

---

## Step 7 — App Directory submission

1. In your Slack app, go to **Manage Distribution** → **Activate Public Distribution**.
2. Complete the **Direct Install URL** check.
3. Go to **Submit to App Directory**.

### Listing copy

**App name:** Quality Engineering Assistant

**Short description (140 chars max):**
```
8D coaching, FMEA review, NCR writing and ISO 9001 audit — structured quality engineering methodology in Slack.
```

**Long description:**
```
Quality Engineering Assistant brings structured quality methodology directly into Slack — exactly where quality engineers already work.

SLASH COMMANDS

/8d [complaint] — Start an interactive 8D investigation (D0 to D8) with validation gates. Or paste an existing 8D and get a Pass/Fail evaluation report.

/fmea [FMEA content] — Review a PFMEA or DFMEA against AIAG-VDA 2019. Get a gap report: missing failure modes, incorrect AP ratings, unaddressed H-AP items.

/ncr [observations] — Convert bullet-point observations into professional NCR text with objective-evidence language and severity grading (Critical/Major/Minor).

/rca [problem] — Run a structured 5-Why root cause analysis with evidence validation. Requires occurrence AND escape root causes. Detects circular reasoning.

/audit [iso9001 | iatf | both] — Start an interactive ISO 9001 or IATF 16949 internal audit clause-by-clause. Classifies findings as Major NC / Minor NC / OFI.

/qe-help — Show all available commands.

WHO IS THIS FOR
Quality engineers, quality managers, and supplier quality engineers in automotive, electronics, aerospace, medical devices, and general manufacturing.

STANDARDS COVERED
ISO 9001:2015 · IATF 16949:2016 · AIAG-VDA FMEA 2019

Powered by Quality-Engineering-Skills — the open-source canonical quality engineering methodology for AI agents.
```

**Categories:** Productivity, AI & Machine Learning

**App website:** https://github.com/RBraga01/Quality-Engineering-Skills

**Support email:** enter_on_junior@hotmail.com

**Privacy policy:** https://rbraga01.github.io/Quality-Engineering-Skills/privacy

---

## Step 8 — Screenshots

Take 5 screenshots at 1200×800 px from Slack:
1. `/qe-help` response showing all commands
2. `/8d` starting D0 gate
3. `/8d` evaluation report with Pass/Fail per discipline
4. `/ncr` output showing professional NCR text
5. `/rca` mid-session showing a 5-Why chain

---

## Step 9 — Submit

Click **Submit for review** in the App Directory submission page.

Slack review takes **5–10 business days**.

---

## After approval

The app appears in:
- **Slack App Directory** (slack.com/apps) — publicly searchable
- Any Slack user can install it in one click from the directory
- Works in any Slack workspace globally

---

## Privacy policy page

Add `docs/privacy.html` before submitting. Key points to include:
- Slash command text is sent to the Anthropic API (Claude) for processing
- No data is stored by Quality-Engineering-Skills
- Workspace tokens are not logged or stored beyond the request
- Anthropic API data usage follows Anthropic's privacy policy
