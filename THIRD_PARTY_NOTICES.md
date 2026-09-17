# Third-party notices

The four Brydge plugins in `plugins/` contain skills and agents written by other people and released under the MIT
licence. MIT allows copying and modification as long as the copyright notice and licence text travel with the copy.
Each plugin keeps those texts in its own `LICENSES/` folder. This file records where every copied file came from and
every change Brydge made.

Third-party plugins listed in `.claude-plugin/marketplace.json` that are not in `plugins/` are **not copied**. Claude
Code downloads them from their original repositories, under their own licences, when someone installs them.

Copies were taken on 17 September 2026 from skills already installed and in use at Brydge. The installed files were
matched against each upstream repository by git file hash before copying.

---

## 1. claude-email

| | |
|---|---|
| Upstream | https://github.com/AgriciDaniel/claude-email |
| Licence | MIT, Copyright (c) 2026 Daniel Agrici |
| Upstream state checked | commit `182270a`, release v1.0.0 |
| Licence copy | `plugins/brydge-essentials/LICENSES/claude-email-MIT.txt`, `plugins/brydge-inbox/LICENSES/claude-email-MIT.txt` |

Copied files:

- `plugins/brydge-essentials/skills/email-write/`
- `plugins/brydge-essentials/skills/email-review/`
- `plugins/brydge-inbox/skills/email/`
- `plugins/brydge-inbox/skills/email-check/`
- `plugins/brydge-inbox/agents/email-compliance.md`, `email-content.md`, `email-deliverability.md`, `email-inbox.md`

Changes:

- Upstream keeps shared reference files and scripts in the parent `email` skill. So that `email-write` and
  `email-review` work on their own in `brydge-essentials`, these files were copied unchanged into those skills:
  - `email-write/references/copy-frameworks.md`
  - `email-review/references/technical-standards.md`, `compliance.md`, `deliverability-rules.md`
  - `email-review/scripts/score_subject_line.py`, `analyze_email_html.py`
- `email/SKILL.md`, "Audit Delegation": agent names changed from `email-deliverability, email-compliance` to
  `brydge-inbox:email-deliverability, brydge-inbox:email-compliance`, because agents inside a plugin are addressed
  with the plugin prefix.

## 2. claude-repurpose

| | |
|---|---|
| Upstream | https://github.com/AgriciDaniel/claude-repurpose |
| Licence | MIT, Copyright (c) 2026 AgriciDaniel |
| Upstream state checked | commit `669187e`, skills at version 1.0.0 |
| Licence copy | `plugins/brydge-comms/LICENSES/claude-repurpose-MIT.txt` |

Copied files:

- `plugins/brydge-comms/skills/repurpose/`
- `plugins/brydge-comms/skills/repurpose-newsletter/`, `repurpose-instagram/`, `repurpose-facebook/`, `repurpose-calendar/`
- `plugins/brydge-comms/agents/repurpose-community.md`, `repurpose-longform.md`, `repurpose-seo.md`,
  `repurpose-social.md`, `repurpose-visual.md`

Not copied: `repurpose/.venv/` (a local Python environment) and all `__pycache__/` folders.

Changes:

- Removed `repurpose/extensions/banana/` (`README.md`, `install.sh`). It is an installer that writes into
  `~/.claude/skills`, which does not apply inside a plugin. The `banana` skill ships in `brydge-creative` instead.
- `repurpose/references/image-prompts.md`, "/banana Detection", item 2: changed from checking
  `~/.claude/skills/banana/SKILL.md` on disk to checking that the `banana` skill is available from `brydge-creative`.
- `repurpose/SKILL.md`, "Step 4": added one paragraph, "Agent names", telling Claude to start the five agents with the
  `brydge-comms:` prefix.
- Shared reference files from `repurpose/references/` copied unchanged into the sub-skills that load them from their
  own folder:
  - `repurpose-newsletter/references/voice-adaptation.md`, `hook-formulas.md`, `engagement-benchmarks.md`
  - `repurpose-instagram/references/platform-specs.md`, `hook-formulas.md`, `voice-adaptation.md`
  - `repurpose-facebook/references/platform-specs.md`, `hook-formulas.md`, `voice-adaptation.md`
  - `repurpose-calendar/references/platform-specs.md`, `engagement-benchmarks.md`

## 3. claude-blog

| | |
|---|---|
| Upstream | https://github.com/AgriciDaniel/claude-blog |
| Licence | MIT, Copyright (c) 2025-2026 AgriciDaniel |
| Upstream NOTICE | Kept in full at `plugins/brydge-comms/LICENSES/claude-blog-NOTICE.txt`. It credits methodology adapted from impeccable by Paul Bakaus (Apache-2.0), which `blog-brand` draws on. |
| Version copied | v1.9.1 (upstream has since released v2.2.0) |
| Licence copy | `plugins/brydge-comms/LICENSES/claude-blog-MIT.txt` |

Copied files:

- `plugins/brydge-comms/skills/blog-translate/`, `blog-localize/`, `blog-brand/`, `blog-chart/`
- `plugins/brydge-comms/agents/blog-translator.md`

The attribution in `blog-translate` and `blog-localize` to `claude-blog-multilingual` by Chris Mueller is kept
unchanged.

Changes:

- `blog-chart/references/visual-media.md` copied unchanged from the parent `blog` skill, which is not included.
- `blog-translate/SKILL.md`, "Phase 4": agent name changed from `blog-translator` to `brydge-comms:blog-translator`.

## 4. banana-claude

| | |
|---|---|
| Upstream | https://github.com/AgriciDaniel/banana-claude |
| Licence | MIT, Copyright (c) 2026 AgriciDaniel |
| Version copied | skill version 1.4.1 (upstream has since released v3.0.0) |
| Licence copy | `plugins/brydge-creative/LICENSES/banana-claude-MIT.txt` |

Copied files:

- `plugins/brydge-creative/skills/banana/`
- `plugins/brydge-creative/agents/brief-constructor.md`

Changes:

- `banana/SKILL.md`: removed the final section, "Community Footer" (with its sub-sections "When to show" and
  "When to skip"). It told Claude to add a promotional call-to-action for an online community to the end of image
  results. Nothing else in the file was changed.

## 5. frontend-slides

| | |
|---|---|
| Upstream | https://github.com/zarazhangrui/frontend-slides |
| Licence | MIT, Copyright (c) 2025 Zara Zhang |
| Upstream state checked | commit `9906a34`, latest release v2.1.0 |
| Licence copy | `plugins/brydge-essentials/skills/frontend-slides/LICENSE` (upstream file) and `plugins/brydge-essentials/LICENSES/frontend-slides-MIT.txt` |

Copied files: `plugins/brydge-essentials/skills/frontend-slides/` including `bold-template-pack/` and `scripts/`.

Changes: none.

## 6. taste-skill

| | |
|---|---|
| Upstream | https://github.com/Leonxlnx/taste-skill |
| Licence | MIT, Copyright (c) 2026 Leonxlnx |
| Upstream state checked | commit `e79ca9e` |
| Licence copy | `plugins/brydge-creative/LICENSES/taste-skill-MIT.txt` |

Copied files: `plugins/brydge-creative/skills/design-taste-frontend/`

Changes: none.

---

## Referenced, not copied

These entries in `marketplace.json` point at the original repositories. Their licences apply when installed.

| Plugin | Source | Licence | Pin |
|---|---|---|---|
| xlsx, docx, pptx, pdf | anthropics/skills | Proprietary, source-available (Anthropic). **Never copy these into this repository.** | `main` |
| internal-comms, canvas-design, discernment-nudge, academy-guide | anthropics/skills | Apache-2.0 | `main` |
| skill-creator, frontend-design | anthropics/claude-plugins-official | Apache-2.0 | `main` |
| playwright | anthropics/claude-plugins-official, `external_plugins/playwright` | Apache-2.0 | `main` |
| firecrawl | firecrawl/firecrawl-claude-plugin | No licence file in the repository | commit `ed01614` |
| canva | canva-sdks/canva-skills, `plugins/canva` | Apache-2.0 | commit `b56291e` |
| last30days | mvanhorn/last30days-skill | MIT | tag v3.24.0, commit `ca9d415` |
| anti-slop | AgriciDaniel/anti-slop, `anti-slop-plugin` | Apache-2.0 (code), CC BY-SA (content) | commit `7b2b0f4` |
