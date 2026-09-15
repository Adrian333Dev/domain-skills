# Backlog

Every open item in this repository. How Flow installs and uses these skills is tracked in Flow's own `backlog.md`, and Flow's `lab/context/` keeps the reasoning behind both.

- One line per item: what it is, then where the argument lives.
- **A finished item is deleted, never checked off.**
- **`## V1` blocks Flow's first release.** **`## After V1`** holds the rest, one subsection per area, the lowest priority last.
- **talk first** needs its own conversation before anything gets built. **parked** waits for a real case.

## V1

Nothing here blocks Flow's first release.

## After V1

### The contribution pipeline

- [ ] **The pipeline's second half**: the CI checks on pull requests here, and `/distill`. CI waits for the first contributor other than the user, and `/distill` for the first distill done by hand on the abuse-prevention case. `flow contribute` was built 2026-09-15. Later still: a drift agent and skill evals. Flow's `lab/context/skills.md`
- [ ] **A Flow command that sends a page or a skill here**: today it is an ordinary pull request, by the steps in `CONTRIBUTING.md`. Waits for the first contributed page to show the manual steps hurt. **parked**

### The skill shape

- [ ] **A domain skill covers one tool at several versions.** React 17, 18 and 19 differ, and the minors between them do too, and nothing in a skill's shape says where React 19 knowledge sits or how a run picks it. Raised by the user 2026-09-12; a `package.json` lookup was guessed and rejected, and the user has a mechanism in mind. **talk first**. Flow's `lab/context/skills.md`

### Individual skills

- [ ] **Rebuild `/web-pages` on `browser-harness`**: 1,059 lines to roughly 150: 54 in `SKILL.md`, 514 in `knowledge/`, 491 in 2 scripts. The capture transport dies, the investigation method stays. Waits for the move to Linux, and is the 1 skill excluded from Flow's writing pass until then. It sits unchanged in `drafts/web-pages/`, and ships by moving to `skills/` in the shape `CONTRIBUTING.md` sets. Its body appends what an investigation proved to a file in its own `knowledge/domains/`. Installed from a clone of this repository, that write would land in the clone, so the rebuild records it as a finding instead. Flow's `lab/context/skills.md`
- [ ] **Chrome extensions**: 3 guides at `drafts/chrome-extension/`, 749 lines on Manifest V3 extensions, single-page app hosts and YouTube. Written for an earlier workflow, moved here from Flow's deleted `lab/framework-build/` on 2026-09-15, and never shaped as a skill. Waits for the next extension project. **parked**
- [ ] **Excalidraw**: 3 third-party skills kept at `drafts/excalidraw/`, still no verdict. The lowest priority here. **talk first**
