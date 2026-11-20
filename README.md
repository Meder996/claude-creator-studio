# Claude Creator, Study & OmniRoute Studio

An independent, local-first, single-file web app for a focused student and creator toolkit, OmniRoute routing presets, prompt optimization, and reusable study/video skill templates.

## Run locally

Open `index.html` directly in a modern browser, or serve this directory:

```bash
python3 -m http.server 3000 --bind 0.0.0.0
```

The app has no build step or package dependencies. Compiled Tailwind CSS, fonts, SVG artwork, and a reference tokenizer are embedded in the HTML.

## Deploy to Vercel

Import this repository into Vercel using the **Other** framework preset. Leave build and install commands empty and use the repository root as the output directory. No environment variables, API keys, database, or backend are required.

`vercel.json` contains the static-site configuration.

## Included

- **GitHub Skills & MCPs:** 18 curated tools—original nine plus nine directly relevant additions—with topic, format, and source filters, setup notes, selection, and separate install/MCP exports.
- **OmniRoute & Token Optimizer:** three editable routing presets and a local prompt minifier with reference token counts.
- **Viral & Study Prompts:** two copyable/downloadable `SKILL.md` templates.
- Light/dark mode, offline operation, responsive layouts, clipboard feedback, and keyboard navigation.
- `claude-plugins-skills-catalog.md` and `.json`: the same focused 18-tool companion collection.

## Important distinctions

This is a catalog and configuration generator. It does not install or execute listed tools, make model/API requests, or collect API keys. Only the theme and selected tool IDs are stored locally; prompt text is not persisted.

OmniRoute's `localhost:20128/v1` address is a configuration example for a gateway on **your own computer**. Hosting this static studio does not host OmniRoute or grant provider access. The 25 core MCP tools refer to the documented Essential (14) and Advanced (11) groups; total tools vary by release.

MarkItDown's “up to 70%” savings figure is explicitly labeled as a third-party estimate, not a Microsoft benchmark or a guarantee. Actual token usage and billing depend on the document, extraction, model, and pricing. Reference token counts are not Claude billing counts.

Review upstream tools, dependencies, licenses, permissions, provider terms, and setup instructions before installing anything. The video pipelines are alternatives, not an install-all checklist.

This is an independent resource, not an Anthropic or Microsoft product. Embedded third-party attribution and license notices are included in `index.html`. Repository links and trademarks remain with their owners.
