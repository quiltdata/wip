# Quilt Workspaces — Prototype

A clickable, standalone prototype of the Quilt Workspaces UX, for the MAT/Flagship
review. Goal: show *how it feels to use this* — a human-centric, role-scoped
workspace with a continuous data-shopping affordance.

## Source of truth

The design brief, screen mockups, and spec live in the
`proj/260529-quilt-workspaces` package (not in this repo). Start here:

**[10-workspaces-ux-brief.md](https://nightly.quilttest.com/b/quilt-dev/packages/proj/260529-quilt-workspaces/tree/latest/10-workspaces-ux-brief.md)**

That brief points to everything else: the canonical ASCII screen mockups (`ui/`),
the publisher/consumer user stories, the spec, and the framing/reset docs.

## Dependencies

This folder holds the generated prototype code. The brief is authoritative;
when the two disagree, the brief wins.
If something turns out to be wrong, update the brief at its source.

> **Caveat:** if you have direct filesystem access to the
> `proj/260529-quilt-workspaces` package, edit the brief there directly — you
> don't need MCP. Use MCP (against the nightly stack) only when working remotely
> without that local access.

## Running it

Open [`index.html`](./index.html) directly in a browser — double-click it, no build,
no server, no dependencies. It's a single self-contained file (vanilla JS + inline
CSS) so it works offline.

## Status

**Pass 1 — substrate (done).** The base Workspace shell + home view, built to nail the
*feel* before layering on shopping:

- One shell (top bar · left rail · main) that all later flows reuse.
- **Workspace home** spanning all Volumes, with **yours-first personalization** — your
  own recent/owned work leads; the rest of the role's data is one toggle away.
- **Objects / Packages / Tables** modes; per-Volume and live filtering; global search.
- **Role switcher** that swaps the whole workspace (role ≡ workspace).
- An empty **Subscribed** rail section + **Domain** / **New asset·product** entries that
  foreshadow where pass 2 plugs in — without faking depth.

**Pass 2 — shopping overlay (next):** consumer browse→inspect→request→granted and the
publisher create→publish→shoppable→grant flows, with the live `○→◌→●` state machine and
granted data flowing back into the **Subscribed** rail. See the brief's flows 2–3.

## Assets

- The "look" should be [flagship](./ui-flagship.png)
- The "feel" should be [quilt](ui-quilt.png)
- The functionality should be like a dashboard

In the age of AI, human attention is the scarcest resource. Don't waste it.
