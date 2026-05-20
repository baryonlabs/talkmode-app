# TalkMode

Public community home for **TalkMode** — a real-time Korean voice assistant for macOS.

- **Website & download** — https://talkmode.baryon.ai
- **Issues** — bug reports and feature requests → the [Issues](https://github.com/baryonlabs/talkmode-app/issues) tab
- **Discussions** — questions, ideas, and help → the [Discussions](https://github.com/baryonlabs/talkmode-app/discussions) tab

The macOS app source is maintained in a separate private repository; this repo
holds the public website, documentation and tooling. TalkMode is free software
under the GNU Affero General Public License v3.0.

## What's in this repo

| Folder | What it is |
|---|---|
| [`web/`](web/) | The **talkmode.baryon.ai** landing page — a static HTML/CSS site with an in-browser README viewer and the signed app download. Deployed to Cloudflare Pages. |
| [`READMEs/`](READMEs/) | The TalkMode README translated into all **20 supported UI languages**. |
| [`mcp/`](mcp/) | Scaffold for an **MCP (Model Context Protocol) server** that will expose the assistant's skills — calendar, mail, messages, memory — as MCP tools so any MCP-aware client can drive them. Not yet implemented. |
| [`subtools/`](subtools/) | Scaffold for **standalone helper tools** that support TalkMode but ship separately from the macOS app — CLI utilities, release helpers, diagnostics. Not yet implemented. |

## Become a contributor

TalkMode is built in the open with its community, and the easiest way to get
involved is to **open an issue** — that's all it takes to start contributing.

- Found a bug, or something feels off? → [file an issue](https://github.com/baryonlabs/talkmode-app/issues/new)
- Have an idea, or want to help build `mcp/` or `subtools/`? → [open an issue](https://github.com/baryonlabs/talkmode-app/issues/new) describing it, or [start a discussion](https://github.com/baryonlabs/talkmode-app/discussions)
- Spotted a translation in `READMEs/` that could read better? → open an issue with the fix

Every issue is a starting point: comment on one, claim it, and you're a
contributor. We review and label new issues regularly — come say hello.

Made in Seoul by [Baryon Labs](https://baryon.ai).
