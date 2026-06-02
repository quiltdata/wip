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

**▶ Live (always reflects `main`):**
<https://raw.githack.com/quiltdata/wip/main/workspaces/index.html>

Or open [`index.html`](./index.html) directly in a browser — double-click it, no build,
no server, no dependencies. It's a single self-contained file (vanilla JS + inline
CSS) so it works offline. See [`DEMO.md`](./DEMO.md) for a 5-minute click-through.
Use the `☀/☾` control (top-right) to switch dark/light.

## Status

**Pass 1 — substrate (done).** The base Workspace shell + home view, built to nail the
*feel* before layering on shopping:

- One shell (top bar · left rail · main) that all later flows reuse.
- **Workspace home** spanning all Volumes, with **yours-first personalization** — your
  own recent/owned work leads; the rest of the role's data is one toggle away.
- **Objects / Packages / Tables** modes; per-Volume and live filtering; global search.
- **Role switcher** that swaps the whole workspace (role ≡ workspace).
- An empty **Subscribed** rail section + **Domain** / **New Asset·Product** entries that
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
- **Create → publish → shoppable** (10·11·12): publish an Asset (one Volume) or Product
  (spans Volumes) from a user's artifacts, then walk the lifecycle bar.

The **`○ shoppable → ◌ requested → ● granted`** state machine is live. Sending a request
shows `◌ requested`, then (with fake latency, to sell the feel) the owner "grants" and the
item **just appears** — under **Subscribed** in the rail, unlocked in its detail view
(screen 24), and folded into your workspace **Packages** beside your own work.

**Pass 3 — the rest of the brief (done).**

- **Flow 4 (interactive):** personal namespaces — packages under `ernie/` carry a
  `🛡 yours` ownership tag (peers can't overwrite). A **Focus** control in Packages
  ("just mine" / "hide a teammate's work") demonstrates that **filtering ≠ access
  control** via an explicit banner — a personal view filter, never a permission change.
- **Flows 5–8 (teasers, no faked depth):** a **Sharing model** view frames the
  *three levels of sharing* (Volumes → user namespaces → stewardship), then roadmap
  cards for low-friction external sharing (5), tables-as-first-class (7), and
  collaboration/notifications (8, marked "coming soon" per the brief's guardrail).

**Pass 4 — models as governed assets (done).** AI/ML models shop through the *same*
substrate as data — no new noun, no separate model registry:

- A published model shows in the Domain as `type: Asset` with a `▣ model` tag (mirroring the
  `▦ table` treatment). A model is an **artifact** wrapped in an **Asset** — the normative
  published nouns stay **Asset** and **Product**, no new noun.
- **Inspect** shows a standardized **model card** (training data, performance, applicability)
  with an intrinsic provenance link — *trained on → the single Product that produced it*.
  A grant is a clean derived-Asset grant; it never backdoors the producing Product's data.
- **Two tiers, same status vocabulary:** a **public/foundation** model is direct-access
  (already `● granted`, unlocked), a **private/fine-tuned** model shops via the
  `○ shoppable → ◌ requested → ● granted` flow. On grant it folds into **Packages** beside
  your own work, still tagged `▣ model`. Access path is framed as `quilt3` + API key (teaser).

**Out of scope by design (per brief):** arbitrary peer-to-peer sharing (sharing stays
role-scoped); notification depth. The Sharing model view states this explicitly so the
boundary reads as intentional, not a gap.

## Assets

- The "look" should be [flagship](./ui-flagship.png)
- The "feel" should be [quilt](ui-quilt.png)
- The functionality should be like a dashboard

In the age of AI, human attention is the scarcest resource. Don't waste it.
