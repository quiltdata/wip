# Quilt Workspaces — Demo Script

A 5-minute click-through of the prototype. Open [`index.html`](./index.html) — no
setup. The one idea to land: **human-centric, not bucket-centric** — your workspace is
everything your role can touch, and shopping for more data is part of that same surface.

> Tip: `☀/☾` (top-right) toggles dark/light. Dark reads as "product"; light reads well
> on a projector.

---

## 1 · The reframe — your workspace, not a bucket (30s)

Land on **Oncology Research**. Say the line:

> "This isn't a bucket. It's *my workspace* — everything my role can see across **3
> Volumes** at once — and it leads with **my** work, not a flat team dump."

- Point at **Your recent activity** (the `ernie/` packages, tagged `🛡 yours`) above
  **Across Oncology Research**.
- Toggle **Yours first → All activity** to show the same data, re-sorted.
- Top-right: switch the **Workspace** dropdown to **Clinical Operations** — the *entire*
  workspace swaps. "Workspace ≡ role." Switch back.

## 2 · One browse experience, three modes (45s)

- **Objects** — click into `assay-results / incoming` — it's the familiar Quilt bucket
  tree (folders, breadcrumb). "Raw files are browsable, but never the unit of shopping."
- **Packages** — the rich, shoppable unit.
- **Tables** — registered tabular data, also first-class (see step 5).

## 3 · Shop the Domain — "it just works" (90s) ← the payoff

Click **🛒 Domain** in the rail. Same shell, same table, same status words.

1. **Browse**: assets, products *and* tables, each with state (`○ shoppable`, `◌
   requested`, `● granted`, `✕ declined`). Everything locked is `🔒`.
2. Click **Study X — full release** → inspect: **metadata + file names only**, contents
   `🔒`. "I can evaluate before I commit — but I can't read the data yet."
3. Tick a couple of `○ shoppable` rows → **Request selected** → add a message → **Send**.
4. It drops to **My requests** as `◌ requested`. **Wait ~3 seconds** — the owner "grants,"
   a toast fires, and the item flips to `● granted`.
5. **This is the moment:** the item now appears under **Subscribed** in the left rail,
   and back in **Packages** (workspace home) it sits in a green **Subscribed** group
   *beside your own data*. Click it → contents are **unlocked** (preview/download), and
   it's in search. "Granted data just appears — no second tool, no copy step."

## 4 · Publish side (45s)

- **＋ New Product** → query (`study_id = "X"`), scope Volumes, **dynamic vs static**
  (flagged as an open decision). Create.
- Walk the **lifecycle bar**: `created → publish → make shoppable`. Three separable steps.
- In **Domain ▸ Published**: your items with **Grant / Decline** on each incoming request.

## 5 · Tables are first-class (20s)

- **Tables** mode → your `ernie_qc_metrics` has **＋ New Asset**. A table is an *artifact*,
  so you publish it by wrapping it in a single-Volume **Asset** (subset = that table) —
  same `create → publish → shoppable` path, no special noun.
- In the **Domain**, those show as type **Asset** with a `▦ table` tag — they shop exactly
  like any other Asset.

## 5b · Models are governed exactly like data (30s)

- In the **🛒 Domain ▸ Browse**, two models show as type **Asset** with a `▣ model` tag —
  no model registry, no third noun (the model is an *artifact* wrapped in an Asset).
  **BioFoundation-1B** is `● granted` (public / foundation → direct access, already unlocked);
  **Onco-Response v2** is `○ shoppable` (private / fine-tuned → shops like any data).
- Inspect **Onco-Response v2** → a standardized **model card** (training data, performance,
  applicability) with a provenance link **↳ trained on → Study X — full release**. Click it:
  you can see the producing Product's card but its contents stay `🔒` — *the model grant is a
  clean derived-Asset grant, never a backdoor to the training data.*
- Request it → on grant it folds into **Packages** beside your own work, still tagged `▣ model`.
  "Models are governed exactly like data — we are not becoming an ML platform."

## 6 · The framing — three levels of sharing (30s)

Click **🔗 Sharing model**:

- **Volumes** (strict segregation) → **user namespaces** (`ernie/` = intra-role write
  ownership) → **stewardship** (read-only inter-team grants via the Domain). All live.
- Show **Filtering ≠ access control**: back in Packages, the **Focus** dropdown ("hide a
  teammate's work") filters *your view* only — the banner makes clear it changes nobody's
  access. Roadmap teasers (easy sharing, notifications) are clearly marked, not faked.

---

## What to *not* claim

- Arbitrary peer-to-peer sharing is **out of scope** — sharing stays role-scoped (stated
  on the Sharing model screen, so the boundary reads as intentional).
- Notifications are a known gap — shown as intent only.
- Don't surface the architecture (Postgres/AVP/Cedar/DataZone). This demo is about *feel*.

## Note for the driver

The grant in step 3 is on a **~2–3s timer** (fake latency, to sell the moment). If you'd
rather grant manually on screen, do it from **Domain ▸ Published** instead.
