# Contributing

Every skill here carries knowledge about one field or tool, such as React, Postgres or investigating a live web page. You can send 3 things: a finding, a page, or a whole skill. This page says which one fits what you learned, where it goes, and the shape it has to take.

## Table of contents

- [What to send](#what-to-send)
- [How the repository is laid out](#how-the-repository-is-laid-out)
- [A skill](#a-skill)
- [A page](#a-page)
- [A finding](#a-finding)
- [Drafts](#drafts)

## What to send

- **A small fact that holds for anyone using the subject** → a finding
- **A whole subject**, such as React hooks or Postgres indexes → a page inside the skill
- **A whole field** nothing here covers yet → a skill
- **A fact true only for your project** → nothing. Keep it in your project

## How the repository is laid out

```
skills/
└─ react/
   ├─ SKILL.md        the map: what the skill covers, and where each page is
   ├─ references/     pages the agent reads, one subject each
   ├─ scripts/        files the agent runs
   ├─ examples/       files the agent copies, such as a whole worked component
   └─ findings/       findings waiting to be merged, never loaded
drafts/
└─ web-pages/         a skill not yet in this shape
```

A skill needs only `SKILL.md`. Add a folder when the skill has something to put in it.

## A skill

`SKILL.md` is a map of about 150 lines. It holds what the field covers, the few rules that hold every time, and where the live documentation is once the pages run out.

It opens with 2 frontmatter fields:

```yaml
---
name: react
description: <what the skill covers>
---
```

`name` matches the folder name. `description` says what the skill covers, never its steps. An agent decides whether to load the skill from this line alone.

**Every section of the body ends with a pointer to the page that goes deeper**, naming what the page holds: "see `hooks.md` for useCallback, useMemo, useSyncExternalStore". The body closes with an index listing every page. Past about 10 pages, group the index under topic headings.

**Link only to files inside the same skill folder.** A page, a script or an example ships with the skill. A finding never gets linked, because it is deleted once merged.

**A skill that needs another skill names it in one sentence**: "Browser steps use the `playwright-cli` skill. If it is not installed, install it before continuing." Nothing installs dependencies automatically.

**The last line of the body is always this**, with the skill's own name:

```
!`flow overlays react 2>/dev/null || true`
```

A line starting with `!` and a command in backticks runs when the skill loads, and its output is pasted into the skill. On a machine running Flow, this line adds a project's own notes about the skill. Everywhere else it prints nothing.

## A page

A page covers one subject, in `references/`. It opens with the same 3 fields every time:

```yaml
---
subject: React 19 hooks
date: 2026-09-13
proved-by: the React 19 upgrade guide, https://react.dev/blog/2024/04/25/react-19-upgrade-guide
---
```

`proved-by` is a sentence saying what showed the page to be true, with a link. Never write a path from your own machine there.

**Knowledge kept per item goes in a sub-folder named for the kind of item.** For example, `web-pages` keeps one page per website in `references/sites/`, such as `references/sites/youtube-watch.md`. Every page in that sub-folder has the same sections, and `SKILL.md` names those sections once.

## A finding

A finding is one small, proved fact, in its own file under `skills/<name>/findings/`. Name the file for what was learned, in 4 to 8 words: `hydration-mismatch-from-server-date-formatting.md`.

It opens with this header:

```yaml
---
skill: react
date: 2026-09-13
proved-by: ticket t045, a Next 15 app on Node 22
---
```

Below the header, say what happened, what fixed it, and the rule that follows.

**The maintainer merges findings into the skill.** Merging rewrites the body or a page so it carries the fact, then deletes the finding. A finding is merged only when all 6 of these hold:

1. **True for anyone** using the subject, not only for one project
2. **Proved**: the header says what proved it
3. **New, or a correction** of something the skill already says
4. **Versioned**: it names the version it holds for, such as React 19.1, not React
5. **Fits the size budget**: `SKILL.md` stays near 150 lines
6. **Written from a failure**: something went wrong without it

A finding that fails one of them is deleted, and the commit deleting it names the rule it failed.

## Drafts

`drafts/<name>/` holds a skill still being written or rebuilt, which does not yet have the shape above. The `skills` installer looks in `skills/`, so a draft never appears next to a finished skill.

A draft ships by moving its folder into `skills/`, once it has the shape.
