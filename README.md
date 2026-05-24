# TalkMode

> **Free for work.** No ads in the app. The app doesn't track you. Your files, your control.

Public community home for **TalkMode** — a real-time Korean (and 35-language) voice assistant for macOS.

- **Website & download** — https://talkmode.baryon.ai
- **Visual install guide** — https://talkmode.baryon.ai/install (macOS 15+ Gatekeeper walkthrough)
- **Free lifetime license** — https://talkmode.baryon.ai/signup (no credit card, beta-unlimited)
- **Issues** — bug reports and feature requests → the [Issues](https://github.com/baryonlabs/talkmode-app/issues) tab
- **Discussions** — questions, ideas, and help → the [Discussions](https://github.com/baryonlabs/talkmode-app/discussions) tab

The macOS app source is maintained in a separate repository (https://github.com/baryonlabs/talkmode); this repo holds the public website, documentation and tooling.

## What's new (0.4.22)

- **Translate mode** — speak in language A, the assistant speaks back in language B.
- **Obsidian vault sync** — meetings / conversations / memories / translations land as Markdown in your vault. No plugin needed.
- **Local LLM providers** — LM Studio, Ollama, and now MLX (`mlx_lm.server`) on Apple Silicon. Fully offline voice assistant possible.
- **Hosted Baryon backend default** — first-time users get 30 free calls per device, no API key, no setup. Switch to Claude / Codex / OpenAI / local later.

## What's in this repo

| Folder | What it is |
|---|---|
| [`web/`](web/) | The **talkmode.baryon.ai** landing page — a static HTML/CSS site with an in-browser README viewer and the signed app download. Deployed to Cloudflare Pages. |
| [`READMEs/`](READMEs/) | The TalkMode README translated into all **20 supported UI languages**. |
| [`mcp/`](mcp/) | Scaffold for an **MCP (Model Context Protocol) server** that will expose the assistant's skills — calendar, mail, messages, memory — as MCP tools so any MCP-aware client can drive them. Spec in progress. |
| [`subtools/`](subtools/) | Scaffold for **standalone helper tools** that support TalkMode but ship separately from the macOS app — CLI utilities, release helpers, diagnostics. Not yet implemented. |

## Become a contributor

TalkMode is built in the open with its community, and the easiest way to get
involved is to **open an issue** — that's all it takes to start contributing.

- Found a bug, or something feels off? → [file an issue](https://github.com/baryonlabs/talkmode-app/issues/new)
- Have an idea, or want to help build `mcp/` or `subtools/`? → [open an issue](https://github.com/baryonlabs/talkmode-app/issues/new) describing it, or [start a discussion](https://github.com/baryonlabs/talkmode-app/discussions)
- Spotted a translation in `READMEs/` that could read better? → open an issue with the fix

Every issue is a starting point: comment on one, claim it, and you're a
contributor. We review and label new issues regularly — come say hello.

Made in Seoul by [Baryon Labs](https://baryon.ai). TalkMode is free software (AGPL-3.0).
