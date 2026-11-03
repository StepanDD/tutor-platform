# Issue tracker: GitHub

Issues and specs for this repo live as GitHub issues. Use the `gh` CLI for all operations.

## Conventions

- Create: `gh issue create --title "..." --body "..."`.
- Read: `gh issue view <number> --json number,title,body,labels,comments`.
- List: `gh issue list --state open`; add label and state filters as needed.
- Sub-issues: use `gh issue create --parent <parent>` or `gh issue edit <parent> --add-sub-issue <child>`. If unavailable, put `Part of #<parent>` in the child body.
- Blocking: use native GitHub issue dependencies (`--blocked-by` / `--add-blocked-by`). If unavailable, write `Blocked by: #<n>` in the child body. A ticket is unblocked when all blockers are closed.
- Comment, label, or close with `gh issue comment`, `gh issue edit --add-label` / `--remove-label`, and `gh issue close`.
- Before the first issue creation in a session, confirm the target with `gh repo view --json nameWithOwner`. File issues only in this repo, never in `mattpocock/skills`.

## Pull requests as a triage surface

**PRs as a request surface: no.** PRs are not included in triage unless this flag is changed.

## When a skill says “publish to the issue tracker”

Create a GitHub issue. When it says “fetch the relevant ticket,” read it with `gh issue view`.

## Wayfinding

- The map is an issue labelled `wayfinder:map`, containing Notes, Decisions-so-far, and Fog.
- Link child tickets as sub-issues where available; otherwise use a task list in the map and `Part of #<map>` in each child.
- Use `wayfinder:<type>` labels (`research`, `prototype`, `grilling`, `task`).
- Claim a ticket with `gh issue edit <n> --add-assignee @me`. Resolve it by commenting, closing, and adding a context pointer to the map.
