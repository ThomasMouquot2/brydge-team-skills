# Brydge Team Skills

The skills and plugins Brydge recommends for client teams using Claude Code, in one place.

- **Brydge plugins** (names start with `brydge-`) are maintained by Brydge in this repository.
- **Other plugins** (Anthropic, Canva, Firecrawl and others) are listed here so you can install them the same way, but
  they download from their makers' own repositories. See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

A **skill** is one recipe Claude follows. A **plugin** is a package of skills (sometimes with helper agents or
connections) that you install in one step.

---

## 1. Before you start (once per laptop)

You need:

1. **Claude Code in VS Code**, set up during your training.
2. **A GitHub account with access to this repository.** This repository is private. Send your GitHub username to your
   Brydge trainer and accept the email invitation.
3. **Your laptop signed in to GitHub**, so Claude Code can download the plugins. In VS Code, open a terminal
   (**View > Terminal**) and paste:

   **Windows (PowerShell)**

   ```powershell
   winget install --id GitHub.cli -e
   ```

   Close the terminal, open a new one, then:

   ```powershell
   gh auth login
   ```

   **Mac (Terminal)**

   ```bash
   brew install gh
   gh auth login
   ```

   Answer the questions like this: **GitHub.com** > **HTTPS** > **Yes** (authenticate Git) > **Login with a web
   browser**. Copy the code it shows, press Enter, and approve in the browser.

## 2. Add the Brydge marketplace (once)

In the VS Code terminal, paste:

```bash
claude plugin marketplace add https://github.com/ThomasMouquot2/brydge-team-skills.git
```

You should see `Successfully added marketplace: brydge-team-skills`.

## 3. Install the plugins for your team

Everyone installs the **Everyone** block, then the block for their team. Paste the lines into the VS Code terminal.
When you are done, start a new Claude Code conversation (or type `/reload-plugins` in the Claude Code panel).

**Everyone**

```bash
claude plugin install brydge-essentials@brydge-team-skills
claude plugin install discernment-nudge@brydge-team-skills
claude plugin install academy-guide@brydge-team-skills
```

**Marketing and communications**

```bash
claude plugin install brydge-comms@brydge-team-skills
claude plugin install brydge-creative@brydge-team-skills
claude plugin install frontend-design@brydge-team-skills
claude plugin install canva@brydge-team-skills
claude plugin install firecrawl@brydge-team-skills
claude plugin install last30days@brydge-team-skills
```

**Programs, front desk and admissions**

```bash
claude plugin install brydge-comms@brydge-team-skills
claude plugin install xlsx@brydge-team-skills
```

**Leadership**

```bash
claude plugin install docx@brydge-team-skills
claude plugin install pptx@brydge-team-skills
claude plugin install internal-comms@brydge-team-skills
claude plugin install last30days@brydge-team-skills
```

**Finance**

```bash
claude plugin install xlsx@brydge-team-skills
claude plugin install pdf@brydge-team-skills
```

**Optional, for anyone who needs them**

```bash
claude plugin install skill-creator@brydge-team-skills
claude plugin install canvas-design@brydge-team-skills
claude plugin install playwright@brydge-team-skills
claude plugin install brydge-inbox@brydge-team-skills
```

To see what you have installed: `claude plugin list`. To remove one:
`claude plugin uninstall <name>@brydge-team-skills`. You can also browse and manage plugins by typing `/plugins` in
the Claude Code panel.

## 4. Using a plugin

You rarely need to call a skill by name. Ask for what you want ("write a follow-up email to parents who missed the
open house") and Claude picks the right skill. To call one directly, type `/` in the Claude Code panel followed by
the plugin and skill name, for example `/brydge-essentials:email-write`.

## 5. Getting updates

Brydge improves these plugins over time. To get the latest versions, paste:

```bash
claude plugin marketplace update brydge-team-skills
claude plugin update brydge-essentials@brydge-team-skills
```

Repeat the second line for each plugin you use. Or turn on automatic updates once: type `/plugin` in Claude Code,
open **Marketplaces**, choose **brydge-team-skills**, then **Enable auto-update**.

---

## What each plugin does

### Brydge plugins

| Plugin | Skills inside | What you get | Needs |
|---|---|---|---|
| `brydge-essentials` | `email-write`, `email-review`, `frontend-slides` | Draft emails with subject line options; check an email before it goes out (subject, wording, spam triggers, compliance) with a score out of 100; build animated HTML slide decks or convert PowerPoint files. | Python for the email checks |
| `brydge-comms` | `repurpose`, `repurpose-newsletter`, `repurpose-instagram`, `repurpose-facebook`, `repurpose-calendar`, `blog-translate`, `blog-localize`, `blog-brand`, `blog-chart` | Turn one article, video or post into a newsletter, Instagram carousel and caption, Facebook posts and a 7-day posting calendar; translate content and adapt it for another culture; write down your brand voice once so every skill follows it; make simple charts. | Python for reading web pages |
| `brydge-creative` | `banana`, `design-taste-frontend` | Create and edit images with Google Gemini; design web pages that do not look like a template. | A free Google AI Studio key for images. Claude walks you through setup the first time. |
| `brydge-inbox` | `email`, `email-check` | Sort your inbox by importance with suggested replies; check a domain's email setup (SPF, DKIM, DMARC); scan for compliance. **Opt-in.** | A Gmail or Outlook connection, and `brydge-essentials` |

### Other recommended plugins

| Plugin | Made by | What you get | Needs |
|---|---|---|---|
| `xlsx` | Anthropic | Create, read and edit Excel files, with formulas and formatting | Python. Recalculating formulas also needs LibreOffice. |
| `docx` | Anthropic | Create and edit Word documents, including tracked changes | Python and Node. Some tasks also need LibreOffice, pandoc or Poppler. |
| `pptx` | Anthropic | Create and edit PowerPoint presentations | Python and Node. Some tasks also need LibreOffice or Poppler. |
| `pdf` | Anthropic | Read, fill, merge, split and create PDFs | Python. Reading scanned PDFs also needs Poppler and Tesseract. |
| `internal-comms` | Anthropic | Staff updates, status reports, newsletters and FAQs in a consistent format | Nothing |
| `canvas-design` | Anthropic | Posters and one-page visual designs as PNG or PDF | Nothing |
| `discernment-nudge` | Anthropic | After a substantial answer, two or three short questions to help you check the facts before you rely on it | Nothing |
| `academy-guide` | Anthropic | Suggests the right Claude Academy course when you ask how to do something | Nothing |
| `skill-creator` | Anthropic | Build your own skill step by step and test it | Nothing |
| `frontend-design` | Anthropic | Polished web pages and page sections | Nothing |
| `playwright` | Microsoft | Claude opens a browser, clicks through a site, fills forms and takes screenshots | Node. Downloads a browser the first time. |
| `canva` | Canva | Create, resize and brand-check Canva designs | A Canva account |
| `firecrawl` | Firecrawl | Read, search and crawl websites | A Firecrawl API key |
| `last30days` | Matt Van Horn | What people said about a topic in the last 30 days on Reddit, Hacker News, YouTube and more | Python. Each research run is large (about 60,000 tokens), so use it for real research questions only. |

### Listed, not recommended yet

| Plugin | Why |
|---|---|
| `anti-slop` | Reviews writing for generic AI patterns. Installed as a plugin, it arrives without its checking scripts (they live in a separate folder upstream), so its automatic check does nothing while still starting Python after every file Claude writes. Brydge will recommend it once that is resolved. |

## Not included, and why

| Left out | Reason |
|---|---|
| SEO, Google Ads, Meta Ads and marketing strategy plugins, including `small-business` and `marketing`, which bundle them | Brydge delivers this work for clients. |
| Email and calendar plugins | Use the Gmail, Google Calendar and Microsoft 365 connectors from your claude.ai account instead. They are available in Claude Code when you sign in with claude.ai. |
| `productivity` | Writes its own instruction file into your folders and is built for Claude Cowork. |
| `brand-voice` | Adds six extra sign-in services. `blog-brand` in `brydge-comms` does the same job without them. |
| `banana-claude` (the upstream plugin) | `brydge-creative` includes the same `banana` skill with a promotional footer removed. |
| `desktop-commander`; data, finance and customer-support plugins | Not needed for current client work. Ask Brydge if your team needs one. |
| `nonprofit-grant-writer-kit` | Its repository imitates an official Anthropic name. |

---

## For Brydge maintainers

**Layout**

```
.claude-plugin/marketplace.json   the catalogue: Brydge plugins plus referenced third-party plugins
plugins/<name>/.claude-plugin/plugin.json
plugins/<name>/skills/<skill>/SKILL.md
plugins/<name>/agents/<agent>.md
plugins/<name>/LICENSES/          upstream licence texts for anything copied
THIRD_PARTY_NOTICES.md            source, licence and every change for copied files
```

**Rules**

- Check before every push: `claude plugin validate .` from the repository root. The only expected warning is the
  missing `version`.
- Brydge plugins have **no `version` field on purpose**. Each commit counts as a new version, so staff get changes
  without a version bump.
- Agents inside a plugin are named `<plugin>:<agent>`. A skill that starts an agent must use that full name, for
  example `brydge-comms:repurpose-social`.
- Anthropic plugins track `main`. Other third-party plugins are pinned to a commit `sha`. To move a pin, read the
  upstream changes first, then replace the `sha`.
- Never copy `xlsx`, `docx`, `pptx` or `pdf` into this repository. Their licence does not allow it.
- Anything copied from elsewhere keeps its licence text in `LICENSES/` and gets an entry in THIRD_PARTY_NOTICES.md,
  including every change.
- Never commit keys, `.env` files or client data. `.gitignore` blocks the common cases.
- Keep this README free of client names. Staff from different clients can read it.

**Adding a plugin for one client or team**

1. Create `plugins/<client>-<purpose>/` with `.claude-plugin/plugin.json` (at least `name`, `description`,
   `author`, `license`) and a `skills/` folder.
2. Add an entry to `.claude-plugin/marketplace.json` with `"source": "./plugins/<client>-<purpose>"`.
3. Run `claude plugin validate .`, commit and push.

**Access**

Collaborators on a repository owned by a personal GitHub account can push changes as well as read. To give staff
read-only access, move this repository to a GitHub organization and give staff the **Read** role.
