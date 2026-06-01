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

**Pass 2 — shopping overlay (done).** The Domain reuses the same shell — one surface,
three tabs:

- **Browse** (consumer, screen 20): shoppable assets/products with live state badges,
  lock glyphs, multi-select → *Request selected*.
- **Inspect** (21): metadata + file names only, contents 🔒 until granted.
- **Request** (22): batch-request multiple items with a message to owners.
- **My requests** (23): per-item `◌ requested / ● granted / ✕ declined`, re-request.
- **Published** (publisher, screen 13): your published items with inline **Grant / Decline**
  per incoming request and a **Make shoppable** control.
- **Create → publish → shoppable** (10·11·12): create a data asset (one Volume) or product
  (spans Volumes), then walk the lifecycle bar.

The **`○ shoppable → ◌ requested → ● granted`** state machine is live. Sending a request
shows `◌ requested`, then (with fake latency, to sell the feel) the owner "grants" and the
item **just appears** — under **Subscribed** in the rail, unlocked in its detail view
(screen 24), and folded into your workspace **Packages** beside your own work.

**Out of scope (per brief):** arbitrary peer-to-peer sharing; notification depth.

## Assets

- The "look" should be [flagship](./ui-flagship.png)
- The "feel" should be [quilt](ui-quilt.png)
- The functionality should be like a dashboard

In the age of AI, human attention is the scarcest resource. Don't waste it.
