---
name: setup
description: Get started with FermentHero after installing it. Use when the user sets up FermentHero, asks what it can do, or wants to connect their FermentHero account.
---

In hosts that show app screens, open `open_baking_companion` to browse recipes and read ingredients and fermentation steps. In text-only hosts, such as a terminal, use `search_recipes` and `get_recipe` instead and present the results as text. Public discovery works without signing in.

When the user wants saved recipes or current bakes, request their FermentHero account through the host OAuth flow. Show which account is connected using `get_current_user`; never request passwords in the conversation.

Ask what they want to bake and which timezone their schedule should use. Existing entitlements apply; do not advertise or link subscription upgrades. Preview a schedule before saving it. For recipe adaptations, follow the recipe-authoring skill and preserve attribution. Save new creations privately.

Explicit user instructions take priority over this guidance, within what the connected account allows and what FermentHero's tools support.
