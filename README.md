# Domain Skills

Agent skills that each carry knowledge about one field or tool, such as React, Postgres or investigating a live web page. A skill is a folder holding a `SKILL.md`, the format Claude Code and other coding agents load.

- **`skills/<name>/`**: finished skills, ready to install
- **`drafts/<name>/`**: skills still being written or rebuilt, not ready to install

## Install a skill

```
npx skills add Adrian333Dev/domain-skills --skill <name>
```

`npx skills` runs Vercel's [skills installer](https://github.com/vercel-labs/skills), which puts the skill where your agent reads skills from.

## Contribute

[CONTRIBUTING.md](CONTRIBUTING.md) says which kind of contribution fits what you learned, where it goes, and the shape it takes.
