# Refinement

## Overview

Refinement (refining) makes equipment stronger by upgrading its **predetermined base stats**, using **ores (refine stones)** drilled in **Mines** across Caballa Island. It is one of the three equipment-modification systems, alongside [Maturing Compound](09-maturing-compound.md) (adding stats to slots) and [Tempering](10-tempering.md) (re-rolling base stats).

## The service

Provided by **Blacksmith Marx** in the town shops (Paradise Shop, Megalopolis Shop, Carbigal Shop, etc.). New players learn refining via the "Learn to Refine!" story quest (the *Refining Guide* book from Marx, part of Officer Robert's Don's Push questline). Marx also runs "Find Ingredients for Precious Jewel" and "Silent Lava Mine Collection" quests whose reward is a **Harkon**.

## Refine stones

- **Two families:** *Physical* refine stones for physical weapons, hats, and shields; *Magic* refine stones for magic-type weapons, hats, and shields.
- Stones are drilled in mines (e.g. Crystal Copper mine at Desert Beach, Silent Lava at Tapasco).

**Four refining tiers:**

| Tier | Ores | Equipment refine levels |
| --- | --- | --- |
| Rookie | Fragments (incl. Soft Iron, Steel) | Lv 1–4 |
| Novice | Impures and Gems | Lv 5–7 |
| Advanced | Pures and Flawless | Lv 8–10 |
| Expert | Rare ores: Ancient Steel, Moonstone, Mithril, Garnet, Ori-Harkon, Zircon, Adamantite, Alexandrite | Lv 11–13 (Lv 13 is the cap) |

**Ore quantities per refine level (physical weapons, ggFTW refine chart):**

**Refine economics from the client:** the seven `ItemRefineTable0–6` files are the exact cost tables — one per equipment level bracket, each specifying the **ore item ID and count for every refine level 1–13** (e.g. Lv 0–30 weapons: 7 → 8 → 10 → 12 ores of the first tier, then 7 → 10 → 13 of the next, escalating onward). `RefineLevelTable` (34 rows) maps every refine level to its **display name and color** (낡은 "worn", 일반 "normal", … the refine-tier naming scheme), and `RefineSupportItemLevel` (77 rows) prices the **support items per refine-level band with their success probabilities** — the Artisan's-Flame-class helpers. `ItemRefineCostDiscount` is the discount event hook (the 2011 Poppuri stage-3 refine-discount reward).

| Item level | Lv 1–4 (Rookie) | Lv 5–7 (Novice) | Lv 8–10 (Advanced) | Lv 11–13 (Expert) |
| --- | --- | --- | --- | --- |
| 1–70 | 7 / 8 / 10 / 12 × Fragment | 7 / 10 / 13 × Impure | 3 / 5 / 7 × Pure | 1 × Ancient Steel |
| 71–130 | Fragments give way to Soft Iron (91–110) and Steel (111–130) | 7 / 10 / 13 × Impure | 3 / 5 / 7 × Pure | 2 × Mithril |
| 131–150 | 7 / 8 / 10 / 12 × Fragment | 7 / 10 / 13 × Impure | 3 / 5 / 7 × Pure | 3 × Ori-Harkon |

Historical note: the Season-1 ores (Agate, Jasper, Tantalum) originally served Expert refine and are now obsolete. PandaTO's wiki additionally documents the **refinement success-rate and stat-magnification ratios**, the per-equipment stat calculation, **anvils**, and each **mine's location** (Crystal Copper at Desert Beach, etc.).

**Star ranks and refinement odds** (PandaTO's documented table): equipment carries a star rank — 0★ Old, 1★ Normal, 2★ Special, 3★ Rare, 4★ Unique, 5★ Legend — that gates its **magnification ratio**. Success declines per refine level (100% at Lv 1, then 90/80/70/60/50/40%…), while the ratio climbs from ×1.10 (Lv 1, 0–3★) to ×2.74 at Lv 7 for 4★ gear; 4–5★ equipment magnifies faster from Lv 1 (×1.20) upward. **Anvils and Refine Fortune Cards** raise the success percentage at Marx; on PandaTO, **Anvil Stones** add +50% for refine levels 5–13. Full table in the [Item Encyclopedia](41-item-encyclopedia.md).

**Magic refine stone ladder (by equipment level):** Quartz (1–30), Amethyst (31–50), Agate (51–70), Moonstone (1–70), Jasper (71–90), Cat's Eye (91–110), Kunzite (111–130), Garnet (71–130), Turquoise (131–150), Opal (151–170), Tiger's Eye (171–200), Zircon (131–200), Alexandrite (201–400), Spinel (201–240), Hyacinth (241–280), Chrysocolla (281–320), Jacinth (321–360), Cassiterite (361–400). Each comes in **Fragment / Gem / Flawless** grades drilled at the mine lots (e.g. Amethyst in Crystal Copper's 2nd Mining Lot).

## Notes

- Refine levels raise the equipment's built-in stats (damage for weapons, defense for hats/shields) in fixed increments per level. Era sources disagree on the cap: InspireMari's guide caps refinement at **level 11**, while the ggFTW archive's Expert tier lists ores for levels **11–13** — the ceiling moved upward as late-era content shipped.
- **Refining can fail and break the item.** A broken non-MyShop item can no longer be equipped and must be repaired with **Repair Powder** (MyShop; also a common Gacha/event filler) — Marx tells you exactly how many powders a broken item needs.
- Late-era example: **Spinel ores** (ore/piece/crystal) from Tapasco Volcano's mine shaft 2 are the refine materials for the Lv 215 magic-type weapon "Stick" and traded at high prices.
- Refining costs galders (discounted during certain event weeks — e.g. Poppuri event stage rewards included 2-week refine-cost discounts).
- Some servers/era variants alter failure behavior and costs; the ggFTW archive is the reference for the official NA era.
- Refinement and compounding interact: compounding adds stats to open **slots**; tempering re-rolls base stats. Refinement is the only one of the three that uses ores from mines.

## Related systems

- [Maturing Compound](09-maturing-compound.md)
- [Tempering](10-tempering.md)
- [Drilling](05-drilling.md) (mines)
- [Events](30-events.md) (refine-cost discount stages)

## Sources

- [Refinement — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Refinement.html)
- [Refining Guide (item) — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Refining_Guide.html)
- [Paradise Shop — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Paradise_Shop.html) (Marx refining service)
- [Trickster Online Items - Refine Guide — Trickster Online Tips blog](http://tricksteronlinetips.blogspot.com/2009/08/trickster-online-items-refine-guide.html)
- [Poppuri Event 09 — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Poppuri_Event_09_(2011_-_GM_Poppuricia).html) (refine discount stage)
- [Trickster Online: Refining — InspireMari](https://inspiremari.nl/trickster-online-refining/) (Lv 11 cap, break/Repair Powder)
- [Refinement — PandaTO Wiki](https://pandato.fandom.com/wiki/Refinement) (success rates, magnification ratios, anvils, mine locations, obsolete ores)
- [Amethyst Fragment — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Amethyst_Fragment.html) (magic refine stone ladder, Fragment/Gem/Flawless grades)
- [수호자와 교감하기 + 각성 준비 — Aeidein's Trickster diary](https://aeideincarte.tistory.com/entry/%EB%84%A4%EC%B6%94%EB%9F%AC-%ED%8A%B8%EB%A6%AD%EC%8A%A4%ED%84%B0-14-%EC%88%98%ED%98%B8%EC%9E%90%EC%99%80-%EA%B5%90%EA%B0%90%ED%95%98%EA%B8%B0-%EA%B0%81%EC%84%B1-%EC%A4%80%EB%B9%84) (Spinel refine stones, Lv 215 Stick)
