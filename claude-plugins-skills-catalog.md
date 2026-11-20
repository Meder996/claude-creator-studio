# Claude Creator — Focused Student & Creator Toolkit

18 selected tools: your original nine plus nine directly useful additions. Source notes checked 2026-11-19.

A short, student-first toolkit for documents, source-grounded study, student coding projects, the original short-video workflows, and token-conscious routing. Not a complete marketplace directory.

## What changed

This replaces the oversized marketplace dump. Only tools directly relevant to study, documents, student coding projects, your original video workflows, or token-conscious routing are included. Unrelated business/CRM, marketing, payment, enterprise, cloud/deployment, security-scanning, and broad all-purpose libraries were removed. Duplicate standalone copies of bundled document skills were not added.

## Start with what you actually need

- **Ordinary studying:** start with your existing office skills, MarkItDown, and Obsidian if you use it. The Study Creator template in the app already covers source-grounded guides and Anki-style cards.
- **Longer assignments:** add document coauthoring or Planning with Files when a writing/planning workflow helps. Fetch and read-only filesystem access are optional ways to supply sources.
- **Coding projects only:** Context7, frontend-design, browser testing, and skill-creator are optional, not prerequisites for studying.
- **Creative shorts only:** preserve the original video tools and add focused Remotion guidance. The original video pipelines are alternatives; choose the one you actually use.
- **Token/cost workflows:** keep your existing OmniRoute and Repomix. No tool supplies free model subscriptions or provider credits.

## Selected tools at a glance

| Tool | Format | Why it is included |
| --- | --- | --- |
| [A little office magic](https://github.com/tfriedel/claude-office-skills) | Skill collection | Your original all-in-one office workflow for assignments, reports, presentations, spreadsheets, and PDFs. No duplicate document-skill bundles are added. |
| [A cleaner page of context](https://github.com/microsoft/markitdown) | MCP server | Turn lecture slides and reading material into cleaner Markdown before summarizing or making study guides. |
| [Notes that think with you](https://github.com/MarkusPfundstein/mcp-obsidian) | MCP server | Use your own organized notes for recall questions, connected concepts, and revision. |
| [Document coauthoring](https://github.com/anthropics/skills/tree/HEAD/skills/doc-coauthoring) | Agent skill | A structured writing workflow for essays, reports, and project documentation using sources you provide. |
| [Planning with files](https://github.com/OthmanAdi/planning-with-files) | Agent skill | Keep the plan, findings, and progress of a longer assignment or research project in simple Markdown files. |
| [Fetch web content](https://github.com/modelcontextprotocol/servers/tree/HEAD/src/fetch) | MCP server | Read publicly accessible articles and course documentation as text/Markdown; verify author, date, and citations against the original page. |
| [Scoped filesystem access](https://github.com/modelcontextprotocol/servers/tree/HEAD/src/filesystem) | MCP server | Let the client read only an explicitly chosen course folder. The example keeps read-only mode on and avoids exposing your whole home directory. |
| [One route. More possibilities.](https://github.com/cheaper-inference/OmniRoute) | MCP server | Preserves your original provider-routing and cost-control workflow. You still supply your own provider access and credentials. |
| [Your codebase, neatly packed](https://github.com/yamadashy/repomix) | MCP server | Package a trusted coding assignment or project into compact context instead of repeatedly pasting files. |
| [Animation skills](https://github.com/artemnovitckii/claude-animation-skills) | Agent skill | Preserves your original 9:16 Three.js and Zack D.-style explainer workflow. Use this only when making those videos. |
| [From a “what if” to a film](https://github.com/Anil-matcha/zack-d-films-ai-video-generator) | CLI / pipeline | Preserves your original beats-to-video pipeline. This is an alternative creator workflow, not something every student needs to install. |
| [Small figures. Big stories.](https://github.com/SyedBahjat/claude-stickman-shorts) | Agent skill | Preserves your original Remotion stickman storytelling and caption workflow. Choose a video pipeline rather than installing all of them. |
| [Drawn simply. Told well.](https://github.com/deenukhan/stick-figure-shorts) | Agent skill | Preserves your original simple illustrated short-explainer workflow, including narration and word timing. |
| [Remotion video skills](https://github.com/remotion-dev/skills) | Skill collection | Focused animation/rendering guidance that directly supports your existing code-generated short-video workflows. |
| [Frontend design](https://github.com/anthropics/claude-plugins-official/tree/HEAD/plugins/frontend-design) | Claude Code plugin | Useful for class websites, portfolios, and small web-project demos. Optional for coding projects, not required for normal studying. |
| [Context7](https://github.com/anthropics/claude-plugins-official/tree/HEAD/external_plugins/context7) | Claude Code plugin | Look up current library and framework documentation while working on coding assignments, rather than relying only on possibly outdated examples. |
| [Playwright browser MCP](https://github.com/microsoft/playwright-mcp) | MCP server | Test a student website or project in a real browser, inspect pages, fill forms, and take screenshots. Keep sensitive signed-in sessions separate. |
| [Skill creator](https://github.com/anthropics/claude-plugins-official/tree/HEAD/plugins/skill-creator) | Claude Code plugin | Turn a repeated study routine, flashcard format, or project checklist into a reusable skill and evaluate it. Optional if the included templates already meet your needs. |

## Setup & safety

- A skill is an instruction/resource package. A plugin can bundle skills, hooks, agents, and tool connections. A standalone MCP server is separately configured. Plugin installation and Desktop MCP JSON are kept separate.
- Review upstream code and licenses before running commands. Plugins, hooks, and local MCP servers can execute code with your user permissions. Source documentation was reviewed; upstream tools were not installed, executed, or security-audited.
- The three plugin entries are selected marketplace listings, not the complete marketplace. Marketplace inclusion does not mean every plugin is Anthropic-authored.
- Copy only the setups you need. The Bash examples below are self-contained macOS/Linux review scripts; Windows may need native commands or absolute executable paths.
- Merge selected MCP server objects into your existing claude_desktop_config.json instead of overwriting it. Replace every path/credential placeholder locally. JSON syntax alone does not complete authentication or dependency setup.
- Keep API keys private, restrict access to course/project folders, and isolate browser profiles. Provider plans, licenses, dependencies, and limits vary.

## Study & Docs · 7 tools

### A little office magic

[Source / package](https://github.com/tfriedel/claude-office-skills) · Skill collection · Original toolkit

Create, edit, and analyze .docx, .pptx, .xlsx, and .pdf files. Complete SKILL.md workflows for tracked changes, HTML-to-slides, and formulas.

**Why kept:** Your original all-in-one office workflow for assignments, reports, presentations, spreadsheets, and PDFs. No duplicate document-skill bundles are added.

**Setup requirements:** Requires Git and dependencies described upstream, which can include Python, Node.js, LibreOffice, Poppler, and Pandoc. Overlaps with the individual Anthropic document skills.

[Upstream setup source](https://github.com/tfriedel/claude-office-skills)

```bash
#!/usr/bin/env bash
set -euo pipefail

# Claude Creator, Study & OmniRoute Studio
# Source snapshot: 2026-11-19
# Review upstream code, hooks, permissions, dependencies, and licenses first.
# Run from a trusted project. Plugin installs use local project scope.
# This script is for macOS/Linux; it never writes Claude Desktop MCP JSON.
# Some upstream installers can change their own files or execute setup scripts.
# Choose a small toolkit, not the whole catalog.
TOOLS_DIR="$HOME/claude-studio-tools"
mkdir -p "$TOOLS_DIR"

# ── tfriedel/claude-office-skills · A little office magic ──
# https://github.com/tfriedel/claude-office-skills
# Requires Git and dependencies described upstream, which can include Python, Node.js, LibreOffice, Poppler, and Pandoc. Overlaps with the individual Anthropic document skills.
if [ ! -d "$TOOLS_DIR/claude-office-skills/.git" ]; then
  git clone https://github.com/tfriedel/claude-office-skills.git "$TOOLS_DIR/claude-office-skills"
fi
mkdir -p "$HOME/.claude/skills"
for skill in docx pptx xlsx pdf; do
  # Keep any skill that is already installed.
  if [ ! -e "$HOME/.claude/skills/$skill" ] && [ ! -L "$HOME/.claude/skills/$skill" ]; then
    ln -s "$TOOLS_DIR/claude-office-skills/public/$skill" "$HOME/.claude/skills/$skill"
  fi
done
# Follow the repository README for Python, Node, and system dependencies.

# Next: merge only the separate standalone MCP JSON into your Desktop config.
# Replace every path/credential placeholder locally, then restart the client.
# Plugin-bundled MCP connections are configured by their plugin, not this JSON.
# Windows: use the documented native commands / executable paths instead.
```

### A cleaner page of context

[Source / package](https://github.com/microsoft/markitdown) · MCP server · Original toolkit

Convert dense PDFs, lecture PowerPoints, and Word files to clean Markdown to cut document-analysis token costs—up to 70% reported (third-party estimate; actual savings vary).

**Figure note:** The up to 70% figure is a third-party reported estimate for document token usage, not a Microsoft benchmark or a measured guarantee from this studio. Actual token use and billed costs depend on the document, extraction method, model, and pricing. [3](https://admin365.blog/2026/06/17/stop-uploading-pdfs-to-claude-use-microsofts-free-markitdown-tool-instead/)

**Why kept:** Turn lecture slides and reading material into cleaner Markdown before summarizing or making study guides.

**Setup requirements:** Requires Python and uv/uvx for the exported MCP command. Optional converters have additional dependencies. Document token reductions vary by source content.

[Upstream setup source](https://github.com/microsoft/markitdown)

```json
{
  "mcpServers": {
    "markitdown": {
      "command": "uvx",
      "args": [
        "markitdown-mcp"
      ]
    }
  }
}
```

### Notes that think with you

[Source / package](https://github.com/MarkusPfundstein/mcp-obsidian) · MCP server · Original toolkit

Connect Claude to your local Markdown notes through Obsidian’s REST API. Turn your own knowledge into active-recall quizzes, connected ideas, and better study guides.

**Why kept:** Use your own organized notes for recall questions, connected concepts, and revision.

**Setup requirements:** Requires uv/uvx, a running Obsidian vault, its Local REST API community plugin, and a locally supplied API key. Limit the notes you expose.

[Upstream setup source](https://github.com/MarkusPfundstein/mcp-obsidian)

```json
{
  "mcpServers": {
    "mcp-obsidian": {
      "command": "uvx",
      "args": [
        "mcp-obsidian"
      ],
      "env": {
        "OBSIDIAN_API_KEY": "REPLACE_WITH_OBSIDIAN_API_KEY",
        "OBSIDIAN_HOST": "127.0.0.1",
        "OBSIDIAN_PORT": "27124"
      }
    }
  }
}
```

### Document coauthoring

[Source / package](https://github.com/anthropics/skills/tree/HEAD/skills/doc-coauthoring) · Agent skill · Anthropic

Use a structured workflow for gathering context, refining a draft, and checking whether readers can understand it.

**Why kept:** A structured writing workflow for essays, reports, and project documentation using sources you provide.

**Setup requirements:** Requires a compatible Agent Skills host. This setup links one skill into ~/.claude/skills and keeps an existing destination. Review SKILL.md for any Python, Node, browser, or system-tool dependencies; skills are instructions, not model access.

[Upstream setup source](https://github.com/anthropics/skills/blob/HEAD/skills/doc-coauthoring/SKILL.md)

```bash
#!/usr/bin/env bash
set -euo pipefail

# Claude Creator, Study & OmniRoute Studio
# Source snapshot: 2026-11-19
# Review upstream code, hooks, permissions, dependencies, and licenses first.
# Run from a trusted project. Plugin installs use local project scope.
# This script is for macOS/Linux; it never writes Claude Desktop MCP JSON.
# Some upstream installers can change their own files or execute setup scripts.
# Choose a small toolkit, not the whole catalog.
TOOLS_DIR="$HOME/claude-studio-tools"
mkdir -p "$TOOLS_DIR"

# ── anthropics/skills · Document coauthoring ──
# https://github.com/anthropics/skills/tree/HEAD/skills/doc-coauthoring
# Requires a compatible Agent Skills host. This setup links one skill into ~/.claude/skills and keeps an existing destination. Review SKILL.md for any Python, Node, browser, or system-tool dependencies; skills are instructions, not model access.
if [ ! -d "$TOOLS_DIR/anthropics-skills/.git" ]; then
  git clone https://github.com/anthropics/skills.git "$TOOLS_DIR/anthropics-skills"
fi
mkdir -p "$HOME/.claude/skills"
if [ ! -e "$HOME/.claude/skills/doc-coauthoring" ] && [ ! -L "$HOME/.claude/skills/doc-coauthoring" ]; then
  ln -s "$TOOLS_DIR/anthropics-skills/skills/doc-coauthoring" "$HOME/.claude/skills/doc-coauthoring"
fi
# Read skills/doc-coauthoring/SKILL.md for dependencies and use instructions.

# Next: merge only the separate standalone MCP JSON into your Desktop config.
# Replace every path/credential placeholder locally, then restart the client.
# Plugin-bundled MCP connections are configured by their plugin, not this JSON.
# Windows: use the documented native commands / executable paths instead.
```

### Planning with files

[Source / package](https://github.com/OthmanAdi/planning-with-files) · Agent skill · Community

Organize a longer assignment or project with durable Markdown task plans, findings, and progress notes between sessions.

**Why kept:** Keep the plan, findings, and progress of a longer assignment or research project in simple Markdown files.

**Setup requirements:** Requires Node.js to use the interactive skills CLI. This installs the named planning skill; translated variants are available upstream. Review any hooks and scripts before use.

[Upstream setup source](https://github.com/OthmanAdi/planning-with-files)

```bash
#!/usr/bin/env bash
set -euo pipefail

# Claude Creator, Study & OmniRoute Studio
# Source snapshot: 2026-11-19
# Review upstream code, hooks, permissions, dependencies, and licenses first.
# Run from a trusted project. Plugin installs use local project scope.
# This script is for macOS/Linux; it never writes Claude Desktop MCP JSON.
# Some upstream installers can change their own files or execute setup scripts.
# Choose a small toolkit, not the whole catalog.
TOOLS_DIR="$HOME/claude-studio-tools"
mkdir -p "$TOOLS_DIR"

# ── OthmanAdi/planning-with-files · Planning with files ──
# https://github.com/OthmanAdi/planning-with-files
# Requires Node.js to use the interactive skills CLI. This installs the named planning skill; translated variants are available upstream. Review any hooks and scripts before use.
npx skills add OthmanAdi/planning-with-files --skill planning-with-files -a claude-code

# Next: merge only the separate standalone MCP JSON into your Desktop config.
# Replace every path/credential placeholder locally, then restart the client.
# Plugin-bundled MCP connections are configured by their plugin, not this JSON.
# Windows: use the documented native commands / executable paths instead.
```

### Fetch web content

[Source / package](https://github.com/modelcontextprotocol/servers/tree/HEAD/src/fetch) · MCP server · MCP reference

Fetch web pages and convert content into a more useful text/Markdown representation for analysis.

**Why kept:** Read publicly accessible articles and course documentation as text/Markdown; verify author, date, and citations against the original page.

**Setup requirements:** Requires uv/uvx and a compatible Python runtime. Fetching untrusted URLs can expose internal network resources; review the server network/security guidance.

[Upstream setup source](https://github.com/modelcontextprotocol/servers/tree/HEAD/src/fetch)

```json
{
  "mcpServers": {
    "fetch": {
      "command": "uvx",
      "args": [
        "mcp-server-fetch"
      ]
    }
  }
}
```

### Scoped filesystem access

[Source / package](https://github.com/modelcontextprotocol/servers/tree/HEAD/src/filesystem) · MCP server · MCP reference

Read and search files inside explicitly allowed folders. This example starts in read-only mode, not with unrestricted home-directory access.

**Why kept:** Let the client read only an explicitly chosen course folder. The example keeps read-only mode on and avoids exposing your whole home directory.

**Setup requirements:** Requires Node.js. Replace the absolute folder placeholder with a folder you explicitly want to expose. Keep --read-only unless you deliberately need writes.

[Upstream setup source](https://github.com/modelcontextprotocol/servers/tree/HEAD/src/filesystem)

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem@latest",
        "--read-only",
        "/ABSOLUTE/PATH/TO/ALLOWED/FOLDER"
      ]
    }
  }
}
```

## Viral Shorts · 5 tools

### Animation skills

[Source / package](https://github.com/artemnovitckii/claude-animation-skills) · Agent skill · Original toolkit

Turn “what if?” into 9:16 Three.js explainers. /zach-d-films adds curiosity hooks, slow-mo impacts, red force ripples, whip cuts, and 1–3 word captions.

**Why kept:** Preserves your original 9:16 Three.js and Zack D.-style explainer workflow. Use this only when making those videos.

**Setup requirements:** Requires Git, Node, Python, and ffmpeg. Review the upstream installer before execution; optional local voice models require a sizable download.

[Upstream setup source](https://github.com/artemnovitckii/claude-animation-skills)

```bash
#!/usr/bin/env bash
set -euo pipefail

# Claude Creator, Study & OmniRoute Studio
# Source snapshot: 2026-11-19
# Review upstream code, hooks, permissions, dependencies, and licenses first.
# Run from a trusted project. Plugin installs use local project scope.
# This script is for macOS/Linux; it never writes Claude Desktop MCP JSON.
# Some upstream installers can change their own files or execute setup scripts.
# Choose a small toolkit, not the whole catalog.
TOOLS_DIR="$HOME/claude-studio-tools"
mkdir -p "$TOOLS_DIR"

# ── artemnovitckii/claude-animation-skills · Animation skills ──
# https://github.com/artemnovitckii/claude-animation-skills
# Requires Git, Node, Python, and ffmpeg. Review the upstream installer before execution; optional local voice models require a sizable download.
if [ ! -d "$TOOLS_DIR/claude-animation-skills/.git" ]; then
  git clone https://github.com/artemnovitckii/claude-animation-skills.git "$TOOLS_DIR/claude-animation-skills"
fi
(cd "$TOOLS_DIR/claude-animation-skills" && ./install.sh)
# Optional local voice + word-timing models (~1 GB):
# (cd "$TOOLS_DIR/claude-animation-skills" && ./install.sh --voice)

# Next: merge only the separate standalone MCP JSON into your Desktop config.
# Replace every path/credential placeholder locally, then restart the client.
# Plugin-bundled MCP connections are configured by their plugin, not this JSON.
# Windows: use the documented native commands / executable paths instead.
```

### From a “what if” to a film

[Source / package](https://github.com/Anil-matcha/zack-d-films-ai-video-generator) · CLI / pipeline · Original toolkit

An end-to-end curiosity loop: beats.json, orthographic 3D character sheets, keyframes, FFmpeg zoompans, and optional consent-based voice cloning.

**Why kept:** Preserves your original beats-to-video pipeline. This is an alternative creator workflow, not something every student needs to install.

**Setup requirements:** Requires Git, Python, ffmpeg, and your own MuAPI credentials. Voice cloning requires the speaker’s explicit consent; provider charges and licensing terms apply.

[Upstream setup source](https://github.com/Anil-matcha/zack-d-films-ai-video-generator)

```bash
#!/usr/bin/env bash
set -euo pipefail

# Claude Creator, Study & OmniRoute Studio
# Source snapshot: 2026-11-19
# Review upstream code, hooks, permissions, dependencies, and licenses first.
# Run from a trusted project. Plugin installs use local project scope.
# This script is for macOS/Linux; it never writes Claude Desktop MCP JSON.
# Some upstream installers can change their own files or execute setup scripts.
# Choose a small toolkit, not the whole catalog.
TOOLS_DIR="$HOME/claude-studio-tools"
mkdir -p "$TOOLS_DIR"

# ── Anil-matcha/zack-d-films-ai-video-generator · From a “what if” to a film ──
# https://github.com/Anil-matcha/zack-d-films-ai-video-generator
# Requires Git, Python, ffmpeg, and your own MuAPI credentials. Voice cloning requires the speaker’s explicit consent; provider charges and licensing terms apply.
if [ ! -d "$TOOLS_DIR/zack-d-films-ai-video-generator/.git" ]; then
  git clone https://github.com/Anil-matcha/zack-d-films-ai-video-generator.git "$TOOLS_DIR/zack-d-films-ai-video-generator"
fi
mkdir -p "$HOME/.claude/skills"
if [ ! -e "$HOME/.claude/skills/zack-d-films" ] && [ ! -L "$HOME/.claude/skills/zack-d-films" ]; then
  ln -s "$TOOLS_DIR/zack-d-films-ai-video-generator" "$HOME/.claude/skills/zack-d-films"
fi
(cd "$TOOLS_DIR/zack-d-films-ai-video-generator" && python3 -m venv .venv && .venv/bin/python -m pip install requests pillow)
# Requires ffmpeg and your own MUAPI_API_KEY. See upstream README.
# Clone voices only with the speaker's explicit consent.

# Next: merge only the separate standalone MCP JSON into your Desktop config.
# Replace every path/credential placeholder locally, then restart the client.
# Plugin-bundled MCP connections are configured by their plugin, not this JSON.
# Windows: use the documented native commands / executable paths instead.
```

### Small figures. Big stories.

[Source / package](https://github.com/SyedBahjat/claude-stickman-shorts) · Agent skill · Original toolkit

A Remotion stick-figure story engine with IK walk cycles, A/B comment-voting hooks, word-synced yellow captions, and procedural, copyright-free sound effects.

**Why kept:** Preserves your original Remotion stickman storytelling and caption workflow. Choose a video pipeline rather than installing all of them.

**Setup requirements:** Requires the runtimes and rendering/audio dependencies described upstream. Review the skill’s first-run engine setup and the licenses of any media or TTS services.

[Upstream setup source](https://github.com/SyedBahjat/claude-stickman-shorts)

```bash
#!/usr/bin/env bash
set -euo pipefail

# Claude Creator, Study & OmniRoute Studio
# Source snapshot: 2026-11-19
# Review upstream code, hooks, permissions, dependencies, and licenses first.
# Run from a trusted project. Plugin installs use local project scope.
# This script is for macOS/Linux; it never writes Claude Desktop MCP JSON.
# Some upstream installers can change their own files or execute setup scripts.
# Choose a small toolkit, not the whole catalog.
TOOLS_DIR="$HOME/claude-studio-tools"
mkdir -p "$TOOLS_DIR"

# ── SyedBahjat/claude-stickman-shorts · Small figures. Big stories. ──
# https://github.com/SyedBahjat/claude-stickman-shorts
# Requires the runtimes and rendering/audio dependencies described upstream. Review the skill’s first-run engine setup and the licenses of any media or TTS services.
if [ ! -d "$TOOLS_DIR/claude-stickman-shorts/.git" ]; then
  git clone https://github.com/SyedBahjat/claude-stickman-shorts.git "$TOOLS_DIR/claude-stickman-shorts"
fi
mkdir -p "$HOME/.claude/skills"
if [ ! -e "$HOME/.claude/skills/stickman-shorts" ] && [ ! -L "$HOME/.claude/skills/stickman-shorts" ]; then
  ln -s "$TOOLS_DIR/claude-stickman-shorts/skills/stickman-shorts" "$HOME/.claude/skills/stickman-shorts"
fi
# The skill sets up its engine on first use. Review upstream requirements.

# Next: merge only the separate standalone MCP JSON into your Desktop config.
# Replace every path/credential placeholder locally, then restart the client.
# Plugin-bundled MCP connections are configured by their plugin, not this JSON.
# Windows: use the documented native commands / executable paths instead.
```

### Drawn simply. Told well.

[Source / package](https://github.com/deenukhan/stick-figure-shorts) · Agent skill · Original toolkit

Code-drawn, 20–40 second stickman visual explainers with ElevenLabs narration and Whisper word-level timing. A simple canvas for surprisingly memorable ideas.

**Why kept:** Preserves your original simple illustrated short-explainer workflow, including narration and word timing.

**Setup requirements:** Requires Node, Python, ffmpeg, and ElevenLabs setup. Review commercial audio and Remotion licensing before monetizing outputs.

[Upstream setup source](https://github.com/deenukhan/stick-figure-shorts)

```bash
#!/usr/bin/env bash
set -euo pipefail

# Claude Creator, Study & OmniRoute Studio
# Source snapshot: 2026-11-19
# Review upstream code, hooks, permissions, dependencies, and licenses first.
# Run from a trusted project. Plugin installs use local project scope.
# This script is for macOS/Linux; it never writes Claude Desktop MCP JSON.
# Some upstream installers can change their own files or execute setup scripts.
# Choose a small toolkit, not the whole catalog.
TOOLS_DIR="$HOME/claude-studio-tools"
mkdir -p "$TOOLS_DIR"

# ── deenukhan/stick-figure-shorts · Drawn simply. Told well. ──
# https://github.com/deenukhan/stick-figure-shorts
# Requires Node, Python, ffmpeg, and ElevenLabs setup. Review commercial audio and Remotion licensing before monetizing outputs.
if [ ! -d "$TOOLS_DIR/stick-figure-shorts/.git" ]; then
  git clone https://github.com/deenukhan/stick-figure-shorts.git "$TOOLS_DIR/stick-figure-shorts"
fi
mkdir -p "$HOME/.claude/skills"
if [ ! -e "$HOME/.claude/skills/stick-figure-shorts" ] && [ ! -L "$HOME/.claude/skills/stick-figure-shorts" ]; then
  ln -s "$TOOLS_DIR/stick-figure-shorts" "$HOME/.claude/skills/stick-figure-shorts"
fi
# Follow SETUP.md for Node 18+, ffmpeg, Python, and ElevenLabs.
# Review the ElevenLabs and Remotion licenses before commercial use.

# Next: merge only the separate standalone MCP JSON into your Desktop config.
# Replace every path/credential placeholder locally, then restart the client.
# Plugin-bundled MCP connections are configured by their plugin, not this JSON.
# Windows: use the documented native commands / executable paths instead.
```

### Remotion video skills

[Source / package](https://github.com/remotion-dev/skills) · Skill collection · Vendor / community

A skill collection for building and rendering programmatic videos with Remotion, including animation and composition guidance.

**Why kept:** Focused animation/rendering guidance that directly supports your existing code-generated short-video workflows.

**Setup requirements:** Requires an appropriate Node/Remotion project for rendering. Review Remotion licensing and browser/system requirements. The copyable command uses the third-party skills CLI and prompts you to choose skills for Claude Code.

[Upstream setup source](https://github.com/remotion-dev/skills)

```bash
#!/usr/bin/env bash
set -euo pipefail

# Claude Creator, Study & OmniRoute Studio
# Source snapshot: 2026-11-19
# Review upstream code, hooks, permissions, dependencies, and licenses first.
# Run from a trusted project. Plugin installs use local project scope.
# This script is for macOS/Linux; it never writes Claude Desktop MCP JSON.
# Some upstream installers can change their own files or execute setup scripts.
# Choose a small toolkit, not the whole catalog.
TOOLS_DIR="$HOME/claude-studio-tools"
mkdir -p "$TOOLS_DIR"

# ── remotion-dev/skills · Remotion video skills ──
# https://github.com/remotion-dev/skills
# Requires an appropriate Node/Remotion project for rendering. Review Remotion licensing and browser/system requirements. The copyable command uses the third-party skills CLI and prompts you to choose skills for Claude Code.
npx skills add remotion-dev/skills -a claude-code
# Interactive installer: review the source and choose only the skills you need.

# Next: merge only the separate standalone MCP JSON into your Desktop config.
# Replace every path/credential placeholder locally, then restart the client.
# Plugin-bundled MCP connections are configured by their plugin, not this JSON.
# Windows: use the documented native commands / executable paths instead.
```

## Coding & Projects · 4 tools

### Frontend design

[Source / package](https://github.com/anthropics/claude-plugins-official/tree/HEAD/plugins/frontend-design) · Claude Code plugin · Anthropic

Create distinctive, production-grade frontend interfaces with high design quality. Generates creative, polished code that avoids generic AI aesthetics.

**Why kept:** Useful for class websites, portfolios, and small web-project demos. Optional for coding projects, not required for normal studying.

**Setup requirements:** Requires current Claude Code. Review the plugin and its license before installing. Building or running a generated website needs that project's own dependencies; this plugin does not provide hosting or model access.

[Upstream setup source](https://github.com/anthropics/claude-plugins-official/blob/HEAD/.claude-plugin/marketplace.json)

```bash
#!/usr/bin/env bash
set -euo pipefail

# Claude Creator, Study & OmniRoute Studio
# Source snapshot: 2026-11-19
# Review upstream code, hooks, permissions, dependencies, and licenses first.
# Run from a trusted project. Plugin installs use local project scope.
# This script is for macOS/Linux; it never writes Claude Desktop MCP JSON.
# Some upstream installers can change their own files or execute setup scripts.
# Choose a small toolkit, not the whole catalog.
TOOLS_DIR="$HOME/claude-studio-tools"
mkdir -p "$TOOLS_DIR"

# Claude Code plugins; current Claude Code is required.
command -v claude >/dev/null 2>&1 || { echo "Install Claude Code first." >&2; exit 1; }

if ! claude plugin marketplace list | grep -Fq -- 'claude-plugins-official'; then
  claude plugin marketplace add 'anthropics/claude-plugins-official'
fi

# ── anthropics/claude-plugins-official · Frontend design ──
# https://github.com/anthropics/claude-plugins-official/tree/HEAD/plugins/frontend-design
# Requires current Claude Code. Review the plugin and its license before installing. Building or running a generated website needs that project's own dependencies; this plugin does not provide hosting or model access.
claude plugin install 'frontend-design@claude-plugins-official' --scope local

# Next: merge only the separate standalone MCP JSON into your Desktop config.
# Replace every path/credential placeholder locally, then restart the client.
# Plugin-bundled MCP connections are configured by their plugin, not this JSON.
# Windows: use the documented native commands / executable paths instead.
```

### Context7

[Source / package](https://github.com/anthropics/claude-plugins-official/tree/HEAD/external_plugins/context7) · Claude Code plugin · Marketplace

Upstash Context7 MCP server for up-to-date documentation lookup. Connects to Context7's hosted remote MCP server (https://mcp.context7.com/mcp) — no local Node.js or npx required — to pull version-specific documentation and code examples directly from source repositories into your LLM context. Works anonymously out of the box; set CONTEXT7_API_KEY for higher rate limits.

**Why kept:** Look up current library and framework documentation while working on coding assignments, rather than relying only on possibly outdated examples.

**Setup requirements:** Anonymous access is documented; an optional Context7 key raises rate limits. The plugin uses a hosted MCP service.

[Upstream setup source](https://github.com/anthropics/claude-plugins-official/blob/HEAD/.claude-plugin/marketplace.json)

```bash
#!/usr/bin/env bash
set -euo pipefail

# Claude Creator, Study & OmniRoute Studio
# Source snapshot: 2026-11-19
# Review upstream code, hooks, permissions, dependencies, and licenses first.
# Run from a trusted project. Plugin installs use local project scope.
# This script is for macOS/Linux; it never writes Claude Desktop MCP JSON.
# Some upstream installers can change their own files or execute setup scripts.
# Choose a small toolkit, not the whole catalog.
TOOLS_DIR="$HOME/claude-studio-tools"
mkdir -p "$TOOLS_DIR"

# Claude Code plugins; current Claude Code is required.
command -v claude >/dev/null 2>&1 || { echo "Install Claude Code first." >&2; exit 1; }

if ! claude plugin marketplace list | grep -Fq -- 'claude-plugins-official'; then
  claude plugin marketplace add 'anthropics/claude-plugins-official'
fi

# ── anthropics/claude-plugins-official · Context7 ──
# https://github.com/anthropics/claude-plugins-official/tree/HEAD/external_plugins/context7
# Anonymous access is documented; an optional Context7 key raises rate limits. The plugin uses a hosted MCP service.
claude plugin install 'context7@claude-plugins-official' --scope local

# Next: merge only the separate standalone MCP JSON into your Desktop config.
# Replace every path/credential placeholder locally, then restart the client.
# Plugin-bundled MCP connections are configured by their plugin, not this JSON.
# Windows: use the documented native commands / executable paths instead.
```

### Playwright browser MCP

[Source / package](https://github.com/microsoft/playwright-mcp) · MCP server · Vendor / community

Control a browser, inspect accessibility snapshots, fill forms, take screenshots, and test web workflows.

**Why kept:** Test a student website or project in a real browser, inspect pages, fill forms, and take screenshots. Keep sensitive signed-in sessions separate.

**Setup requirements:** Requires a supported Node.js runtime and installed browser/system dependencies. Use a separate browser profile and avoid exposing sensitive signed-in sessions.

[Upstream setup source](https://github.com/microsoft/playwright-mcp)

```json
{
  "mcpServers": {
    "playwright": {
      "command": "npx",
      "args": [
        "-y",
        "@playwright/mcp@latest"
      ]
    }
  }
}
```

### Skill creator

[Source / package](https://github.com/anthropics/claude-plugins-official/tree/HEAD/plugins/skill-creator) · Claude Code plugin · Anthropic

Create new skills, improve existing skills, and measure skill performance. Use when users want to create a skill from scratch, update or optimize an existing skill, run evals to test a skill, or benchmark skill performance with variance analysis.

**Why kept:** Turn a repeated study routine, flashcard format, or project checklist into a reusable skill and evaluate it. Optional if the included templates already meet your needs.

**Setup requirements:** Requires current Claude Code. Review the plugin's scripts and license first. Evaluation workflows can need local runtimes and model usage under your own account; this does not supply free model credits.

[Upstream setup source](https://github.com/anthropics/claude-plugins-official/blob/HEAD/.claude-plugin/marketplace.json)

```bash
#!/usr/bin/env bash
set -euo pipefail

# Claude Creator, Study & OmniRoute Studio
# Source snapshot: 2026-11-19
# Review upstream code, hooks, permissions, dependencies, and licenses first.
# Run from a trusted project. Plugin installs use local project scope.
# This script is for macOS/Linux; it never writes Claude Desktop MCP JSON.
# Some upstream installers can change their own files or execute setup scripts.
# Choose a small toolkit, not the whole catalog.
TOOLS_DIR="$HOME/claude-studio-tools"
mkdir -p "$TOOLS_DIR"

# Claude Code plugins; current Claude Code is required.
command -v claude >/dev/null 2>&1 || { echo "Install Claude Code first." >&2; exit 1; }

if ! claude plugin marketplace list | grep -Fq -- 'claude-plugins-official'; then
  claude plugin marketplace add 'anthropics/claude-plugins-official'
fi

# ── anthropics/claude-plugins-official · Skill creator ──
# https://github.com/anthropics/claude-plugins-official/tree/HEAD/plugins/skill-creator
# Requires current Claude Code. Review the plugin's scripts and license first. Evaluation workflows can need local runtimes and model usage under your own account; this does not supply free model credits.
claude plugin install 'skill-creator@claude-plugins-official' --scope local

# Next: merge only the separate standalone MCP JSON into your Desktop config.
# Replace every path/credential placeholder locally, then restart the client.
# Plugin-bundled MCP connections are configured by their plugin, not this JSON.
# Windows: use the documented native commands / executable paths instead.
```

## OmniRoute & Tokens · 2 tools

### One route. More possibilities.

[Source / package](https://github.com/cheaper-inference/OmniRoute) · MCP server · Original toolkit

Free, MIT-licensed AI gateway at localhost:20128/v1 for Claude Code and CLI tools. Built-in MCP server with 25 core tools, quota tracking, and Subscription → Cheap API → Free Models auto-fallback. Total MCP tools vary by version.

**Figure note:** The 25 core tools are the documented Essential (14) and Advanced (11) groups, not the total in every release. Current releases include additional MCP tool groups. Fallback needs your own connected providers and eligible healthy targets; free-tier access and quotas follow provider terms. [MCP tool-count breakdown](https://github.com/cheaper-inference/OmniRoute/blob/HEAD/docs/frameworks/MCP-SERVER.md)

**Why kept:** Preserves your original provider-routing and cost-control workflow. You still supply your own provider access and credentials.

**Setup requirements:** Requires Node/npm and a locally running OmniRoute gateway. Connect your own providers; subscription, API, free-tier, and MCP availability depend on their terms and your configuration.

[Upstream setup source](https://github.com/cheaper-inference/OmniRoute)

```json
{
  "mcpServers": {
    "omniroute": {
      "command": "omniroute",
      "args": [
        "--mcp"
      ]
    }
  }
}
```

### Your codebase, neatly packed

[Source / package](https://github.com/yamadashy/repomix) · MCP server · Original toolkit

Pack a whole project into one AI-friendly XML file. Use code-aware compression to trim context, keep what matters, and make repository conversations more focused.

**Why kept:** Package a trusted coding assignment or project into compact context instead of repeatedly pasting files.

**Setup requirements:** Requires Node/npm. Only expose trusted repositories and keep secrets out of packed context. Use upstream sandboxing for untrusted code.

[Upstream setup source](https://github.com/yamadashy/repomix)

```json
{
  "mcpServers": {
    "repomix": {
      "command": "npx",
      "args": [
        "-y",
        "repomix",
        "--mcp"
      ]
    }
  }
}
```

## Using the studio

Open index.html in a modern browser. Topic, format, and source filters apply only to these 18 selected tools. Select a few cards to export one setup script and a separate standalone MCP JSON object. The two included SKILL.md templates, routing presets, live minifier, light/dark mode, and offline fonts/reference tokenizer are preserved. The studio does not install or run any listed tool.
