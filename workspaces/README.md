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

## Assets

- The "look" should be [flagship](./ui-flagship.png)
- The "feel" should be [quilt](ui-quilt.png)
- The functionality should be like a dashboard

In the age of AI, human attention is the scarcest resource. Don't waste it.
