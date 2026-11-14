# FermentHero plugin

Find, create, edit, and plan fermentation recipes in [FermentHero](https://fermenthero.com) from Claude, ChatGPT and Codex: sourdough, kimchi, kefir, kombucha, hot sauce and more.

The plugin connects to the hosted FermentHero MCP server at `https://api.fermenthero.com/mcp` and adds four skills:

| Skill | What it does |
| --- | --- |
| `setup` | Gets you started and links your FermentHero account |
| `recipe-discovery` | Finds public recipes or your own and reads ingredients and steps |
| `recipe-authoring` | Writes, imports, adapts and validates recipes in the FermentHero format, then saves them privately |
| `planning-progress` | Schedules recipes in your planner, reschedules them and records step progress |

In Claude apps that show interactive screens (claude.ai, Claude Desktop, Cowork), the `open_baking_companion` tool opens the FermentHero search, recipe and planner screens. Claude Code shows text results only; all features work there through the same tools.

## Setup

**Claude (claude.ai, Desktop, Cowork):** install the plugin from the Claude directory, or add the connector under Settings → Connectors with the URL `https://api.fermenthero.com/mcp`.

**Claude Code:**

```sh
/plugin marketplace add Sopamo/fermenthero-plugin
/plugin install fermenthero@fermenthero
```

or load a local copy with `claude --plugin-dir <path to this folder>`. Then run `/mcp`, choose `fermenthero` and sign in.

**ChatGPT and Codex:** the same folder is also an OpenAI plugin (`.codex-plugin/plugin.json`).

Public recipe search works without an account. To use your own recipes and planner, sign in with your FermentHero account when Claude asks. FermentHero uses OAuth: you sign in on fermenthero.com and Claude never sees your password. Creating and editing recipes requires FermentHero Plus.

You can see and disconnect linked assistants in the FermentHero app under Settings → Connected assistants.

## Privacy

FermentHero processes the recipes, plans and account details that the tools read or write for you. See the privacy policy: https://app.fermenthero.com/gdpr

## Support

fermenthero@sopamo.de · https://fermenthero.com

## Source

This repository is published from `plugins/fermenthero` in the FermentHero API repository; changes are made there and copied here for each release.

## License

MIT, see [LICENSE](LICENSE). The license covers this plugin folder (skills and configuration), not the FermentHero service.
