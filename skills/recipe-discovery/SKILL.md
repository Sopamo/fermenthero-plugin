---
name: recipe-discovery
description: Find public FermentHero recipes or the connected user's own recipes and read their ingredients and procedures. Use when the user looks for a fermentation or baking recipe in FermentHero or asks about one.
---

Use `search_recipes` with `scope: public` for discovery or `scope: mine` for personal recipes. Filter by category, language or difficulty when relevant. Follow `next_page` for an exhaustive request. Read selected recipes with `get_recipe`; search results alone do not include the procedure.

Respect Plus access. For a locked Plus recipe `get_recipe` returns the overview and ingredients with `steps_locked: true` and never spends an unlock; use `unlock_recipe` only when the user authorizes using an available free token. Account linking is required for personal recipes. Include returned FermentHero links and preserve source attribution when suggesting adaptations.

Explicit user instructions take priority over this guidance, within what the connected account allows and what FermentHero's tools support.
