---
name: recipe-authoring
description: Create, import, adapt, validate, and save FermentHero recipes in its ingredient-group and action/wait format. Use when the user wants a recipe written, converted, changed, saved, or shared in FermentHero.
---

Read [format rules](references/format.md) and the relevant [examples](references/examples.json) before authoring. The [schema](references/recipe.schema.json) defines writable fields; `recipe_guide` supplies the same material to clients without this skill.

Creating or editing recipes requires FermentHero Plus. If access is denied, explain the requirement without prices or upgrade links, and keep the proposed recipe available in the conversation.

For a new recipe, compose the requested recipe directly, then call `validate_recipe` and `create_recipe`. FermentHero stores it privately.

For imports, preserve the selected recipe's instructions and source attribution. For original creations, choose coherent ingredients and timings for the user's constraints. For edits, call `get_recipe`, preserve unrelated content and identifiers, validate the modified writable fields, then call `update_recipe` with the returned revision. Duplicate others' or published recipes before adapting them.

Use a new `request_id` UUID for each write intent and reuse it with identical arguments after an uncertain response. On a revision conflict, read again and reconcile the requested change. Correct validation errors before retrying; changed input needs a new request ID.

Saving and public sharing are separate actions. Use `share_recipe` only for an explicit sharing request with the user's rights declarations. A request to create a recipe does not imply publication. Return the saved recipe link.

Explicit user instructions take priority over this guidance, within what the connected account allows and what FermentHero's tools support.
