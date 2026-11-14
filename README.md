# pocuston-skills

Agent Skills that work in Claude, ChatGPT and other agents that support the open [Agent Skills](https://agentskills.io) format.

| Skill | What it does |
|---|---|
| [socratic-reading](plugins/socratic-reading) | Test and deepen your understanding of anything you've read through Socratic questioning |

## Install

### Claude Code

```bash
claude plugin marketplace add Pocuston/pocuston-skills
claude plugin install socratic-reading@pocuston-skills
```

### Claude (web, desktop, mobile)

1. Download the skill folder, e.g. `plugins/socratic-reading/skills/socratic-reading/`, and zip it.
2. Upload the ZIP under Skills in Claude's settings.

### ChatGPT

Download the skill folder and add it as a skill in ChatGPT. The `SKILL.md` format is shared, so no changes are needed.

### Codex, Cursor, GitHub Copilot and other agents

```bash
npx skills add Pocuston/pocuston-skills --skill socratic-reading
```

## Repository layout

```
.claude-plugin/marketplace.json     # catalog of all plugins in this repo
plugins/<plugin>/
  .claude-plugin/plugin.json        # plugin manifest
  skills/<skill>/SKILL.md           # one or more skills
  README.md
```

### Adding a new skill

1. **Standalone:** create `plugins/<name>/` with `.claude-plugin/plugin.json`, `skills/<name>/SKILL.md` and a `README.md`.
2. **Related to an existing plugin:** add `skills/<name>/SKILL.md` inside that plugin instead.
3. For a new plugin, add an entry to `.claude-plugin/marketplace.json`. The entry's `name` must match the `name` in its `plugin.json`.
4. Bump `version` in the changed `plugin.json`, otherwise existing users won't receive the update.
5. Run `claude plugin validate .` and add the skill to the table above.

## License

MIT
