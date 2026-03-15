# Brodocs

## Tech docs for the agent economy — convert users and their AI agents 😎

Brodocs is a SaaS docs site builder that generates beautiful documentation sites directly from markdown files in your git repos — no manual tree building, no CMS, no admin panel overhead.

> 💡 **Try it now:** No account needed. Send one `curl` to get a live site in seconds — see [Quick start](/About/Quick%20start.md). You can use [GitHub repo](https://github.com/brodocsdev/docs) which is source for this site.



## Who it's for

**Founders** — ship polished public docs for your product without dev overhead. Your docs site goes live from the same repo you already write markdown in.

**SMB and enterprise teams** — internal knowledge portal built from multiple repos, one per team or service, unified under a single site with top menu navigation.


## Key features

- **Agent economy ready** — every site generates both human-readable pages and `llms.txt` files, so your users' AI agents can navigate your docs just like people do
- **Git-native** — sites rebuild automatically on every push via webhook; your docs stay in sync with your code
- **One API call to launch** — pass a git repo URL, a name, and your email; get a live URL back in milliseconds
- **Auto navigation** — left menu is built from your directory and file names; no manual tree configuration
- **Auto top menu** — first-level directories become top menu items when enabled; multi-repo multisites supported via a simple YAML manifest
- **File ordering** — control order with plain `order` text files or the open-source [VSCode Sort Explorer](https://marketplace.visualstudio.com/items?itemName=Tyriar.sort-lines) plugin — what you see in VSCode is what you get
- **Diagram rendering** — PlantUML diagrams are converted automatically on build
- **Themes** — dark and light color schemes; select via config file in your repo


## Implemented features

- [Build and index sites from public and private repos](/About/Quick%20start.md)
- [`llms.txt` generation for AI agent access](https://brodocs.io/llms.txt)
- [Auto-rebuild after git push](/About/Updates.md)
- [Multisites with top menu from multiple repos](/About/Multisites%20with%20top%20menu.md)
- [PlantUML diagram conversion](/About/Diagrams%20conversion.md)
- [File and directory ordering](/About/Ordering.md)


## Coming next

- Management app — account creation, site management dashboard
- Private sites with team sharing
- GitHub and GitLab native push notifications (currently via webhooks)
- RBAC for internal portals
- MCP server with semantic search over your docs for use with Claude Code, Copilot, and similar tools
- More diagramming and charting tools
- Additional themes


## Pricing

See [Pricing](/About/Pricing.md) for current tiers. Free plan available — no credit card required.


## Get started with a custom domain

The self-service management app is coming soon. In the meantime, onboarding is handled personally — mail **founder@brodocs.io** to get your site set up with a custom domain.
