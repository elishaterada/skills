# Skills

A collection of portable Agent Skills for Codex, Claude, Cursor, and other compatible AI tools.

## Available skills

### `pii-directory-opt-out`

Finds the user's personal listings on people-search, contact-directory, and data-broker websites and guides cautious, trackable opt-outs while preserving legitimate online accounts.

### `visual-tech-explainer`

Turns complex technology concepts into clear, self-contained visual explanations with bento-box layouts, diagrams, timelines, and progressive disclosure.

## Use a skill

Each directory under `skills/` is an independent skill. Install or link the directory into the location your AI tool uses for Agent Skills. You can also point an agent directly to its `SKILL.md` file.

The core instructions are vendor-neutral. Tool-specific metadata, such as `agents/openai.yaml`, is optional and does not change the portable workflow.

## Repository structure

```text
skills/
  visual-tech-explainer/
    SKILL.md
    agents/
    references/
    assets/
```

## Add another skill

Create a new kebab-case directory under `skills/` with a `SKILL.md` containing only the required `name` and `description` frontmatter followed by concise instructions. Keep detailed knowledge in `references/`, reusable output files in `assets/`, and deterministic automation in `scripts/`.

## License

MIT
