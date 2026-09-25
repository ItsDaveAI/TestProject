# Item Fusion & Defusion

## Overview

Item Fusion lets one equipment's **image (appearance)** be fused onto another equipment's **stats** — the core "fashion over function" system. The surviving item is the **STATS equipment**; the consumed item (appearance only) is the **IMAGE equipment**. Service NPC: **Fusion Master Arlene** (Paradise Shop, Megalopolis Shop, and other town shops). Pet appearance fusion is a separate service (see [Pets](12-pets.md)).

## How to fuse

**Fusion odds (client data):** `EquipFusionSupportItemTable` sets the **base fusion success at 70%** ("70%, 장비융합 기본적용 확률") — with **two support-item catalysts that add +30 percentage points each** (items 19818, 19822), i.e. a boosted fusion can reach 100%. Fusion failure paths and the skin-system renewal ride on the same table family.

1. Talk to Arlene with the stats item, the image item, and an **Artisan's Flame** (MyShop catalyst — 1,600 points each per the ggFTW-era price; earlier sources cite ~4,400).
2. Stats item in one slot, image item in the other; confirm the fusion preview.

**Rules:**
- All stats come from the STATS equipment; none from the IMAGE equipment.
- The image item is **consumed**; its icon and in-game appearance transfer to the fused item.
- Fused equipment **can no longer be dropped**.
- **Tradable status follows the stats item** — fusing a non-tradable MyShop image onto a tradable in-game stat item yields a *tradable* item with the MyShop look. (Fusing onto a MyShop stat item makes the result non-tradable.)
- Examples: Lunar Rod (stats) + Saturn Staff (image) = Lunar Rod with Saturn Staff looks.

## Defusion ("Disassemble Equipment")

- Arlene's defusion window separates a fused item back into the **main item** (original look restored) and a **Skin/Form item** carrying the fused appearance.
- Defusing also consumes an **Artisan's Flame**.
- **Form items are tradable** — this became the standard way players trade MyShop looks.

## Skin System Renewal

A later update (documented in the Thai official news) removed the Artisan's Flame cost when fusing a stat item with an **Item Form** (already-defused skin) — stat item + Form = free fusion, letting players swap looks endlessly with a collection of Forms.

## Related systems

- [Pets](12-pets.md) — Pet Fusion (Erin)
- [MyShop](22-myshop.md) — Artisan's Flame source
- [Wedding system](20-wedding-system.md) — Forever/Promise wedding tickets via Arlene

## Sources

- [Item Fusion — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Item_Fusion.html)
- [Random Entry 20/02/2008 — Miyuki's blog](https://kawaiimiyuki.wordpress.com/2008/02/20/random-entry-20022008-trickster-online/) (2008-era fusion walkthrough)
- [Trickster Skin System Renewal news — Online Station (Thai)](https://www.online-station.net/pc-console-game/135719)
