# Drilling (incl. Crazy Drilling)

## Overview

Drilling is Trickster Online's signature non-combat system: players **drill into the terrain of field maps** to dig up buried items and EXP. "You don't have to kill to gain" — many quest items, equipment, refine ores, gacha-adjacent treasures, potions, and galders come from underground. Sense types (Fox, Lion) excel at it because DA and WT enhance drilling.

## How to drill

1. Get a drill — the first one comes from **Driller Marky**; others are bought from Item Girls, dropped by monsters, dug up, or bought from MyShop.
2. Enter a field map (towns and some fields forbid drilling), press **D** to pull out the drill; the cursor changes to drill mode (right-click exits drill mode).
3. Click a spot. Your character walks there and a drilling bar appears. Repeatedly click (or hold) to raise the yellow bar — keep it **just above the small guideline** without overfilling it. Closer to the line = higher success odds; overfilling forces a restart but still costs drill life.
4. Depth numbers pop up as you dig. At the bottom you either find an item or nothing.

**Drill life:** drills have finite uses shown like `600/650` (remaining/total). **Depth rating:** each drill is rated for a maximum depth (e.g. Drill No. 1 = 20 m). Drills are also typed by ground (Sand / Land / Rock variants for each level).

## Results

- **Base EXP** on every completed drill (even finding nothing); deeper digs give more EXP. EXP is calculated from the drill's stage.
- **TM EXP** only when an item is found (see [TM leveling](03-tm-leveling-and-skills.md)).
- **DA matters:** with **90+ DA** detection is 100% — your character instantly knows "an item is not here" (squiggle icon) and never wastes attempts. A **lightbulb** icon over your character means more items remain at the same spot.
- After drilling a spot you cannot re-drill it immediately; move at least ~2 character-steps away. Other players drilling the same spot can take the item.

## Drill progression (NPC drills)

| Drill | Level req. | Depth | Cost | Durability |
| --- | --- | --- | --- | --- |
| Regular / Neo Drill No. 1 | 1 | 20 m | 1,000 g | 100 / 500 |
| Regular / Neo Drill No. 2 | 10 | 40 m | 2,000 / 25,000 g | 100 / 500 |
| Regular / Neo Drill No. 3 | 30 | 60 m | 10,000 / 25,000 g | 100 / 500 |
| Regular / Neo Drill No. 4 | 60 | deeper | varies | 100 / 500 |

Sold by each region's Item Girl (No. 1 at Gate of Desert Beach/Paradise; No. 2 at Megalopolis/Poppuri Dungeon/Event Garden; No. 3 at Gate of Caballa Relics/Azteca; No. 4 at Oops Wharf, Mermaid Palace, Phantom Snack Bar, etc.). "Neo" versions have enhanced durability (500). MyShop sells premium drills (e.g. Treble, Flicker-class). Ground-type specializations (sand/land/rock) were never proven to matter.

**Full drill taxonomy** (per the ggFTW drill charts): NPC drills come **soil-typed** — Sand, Land, Rock, plus Sea, Ice, and Snow families — in Regular and Neo grades No.1–8, alongside **Multi Drills** that dig any soil; every drill carries a **Stage 1–12** rating that sets drilling EXP (MyShop: Bubble/Propeller stage 5–6 → Thiefmon Drill stage 12, with the 60/120/180 specialty quartets — Crazy for stress, Novice for gauge, **Speed +30%**, Tank for lifespan; 131 drills documented). The drilling page also lists a "Love Drilling" section whose body text was not preserved in the wiki mirror.

## Drilling EXP formulas (jTrickster-era)

- **Base EXP** (whether or not you found anything): `Depth × stage multiplier` — Stage 1 = 1.2, Stage 2 = 2.4, Stage 3 = 4.4, Stage 4 = ~6, Stage 5 = 8.4.
- **TM EXP** (only when an item is found): `(Player Base Lv + depth the item was found at) × drill stage × 4`.
- If an item was definitely present but you get interrupted, the item is removed and the potential TM EXP is lost.
- Community tips: a dug-up item **respawns on a random patch of the same map**, so less-trafficked corners keep paying; newbie maps are only ~10 m deep while your first drill digs 20 m — drilling higher-region fields with passive monsters is better early income; never re-drill the patch you just drilled.

## Related drilling features

**The buried-item placement dataset (client data):** the `R_MapItem_*` family is the drilling layer's raw data — **158 per-map placement tables holding 3,243 item-placement rows**, each specifying the item ID, optional source monster, a **depth band (MinDepth–MaxDepth, spanning 10 m to 300 m across the island)**, average and maximum spawn counts, a time table, and a placement priority. Every "dig here, find this, at this depth" fact in this file is one of those 3,243 rows. The companion `MapItem_` tables carry per-map placement for the field items, and `TreasureMap_Item` binds the 67 treasure maps to their 5 candidate dig spots.

- **Mines** — special mining maps scattered across Caballa Island where **refine ores** are drilled (see [Refinement](08-refinement.md)).
- **Treasure Hunts** — "Worn and Old" Treasure Maps drilled up in each region's fields lead to buried treasure (a "Surprise" drilling outcome; also a source of Chaos's Feathers). The rarest **Weird Treasure Maps** open each region's hidden **Black Market** (see [Economy](31-economy-bank-trade.md)).
- **Surprise Spot quests** — the map tiers carry a repeatable quest layer on top: **Explorer Reina** runs *Treasure Hunting 1 & 2* (the Worn and Old Map tiers) and **Driller King Marky** runs *Romance of Drilling* (Weird Maps), plus Indiana John's one-off — **43 quests** across every region except Coral Beach, Phantom School, and Abyss. Worn-map quests repeat infinitely; the Weird/Old tiers are dailies, and a region's Old-map chain only unlocks after **50 Worn-map quests in that same region**.
- **GPS hunts** — quest chains (notably Phantom School's classroom quests) use **GPS items** dropped by local monsters: activate one and a radar indicator appears, its detection level counting down (1 = closest) until you dig up a buried **Poseidon's treasure** chest ("SURPRISE!" on success).
- **Poseidon's Treasure / treasure map digging** — quest-linked buried treasure content.

## Crazy Drilling

A passive **skill learned from Driller Marky's questline** (Marky, Reina, and John at the top-left edge of Paradise; drilling + killing tasks; reward includes the Crazy Drill User Manual).

- Failing to find items fills an **anger meter** (the `>:3` gauge); misses and "item is not here" fill it faster than finds.
- At the threshold, **Crazy Driller Mode** activates: clicking instantly drills that spot (item or nothing), with a chance of a **rain of items**.
- Follow-up skills: **Anger Management** and **Mega Crazy Drilling**.
- Caveat: on some event types (e.g. Poppuri event boxes), boxes could not be drilled up while in Crazy Drilling mode.

Client data (`CrazyDrillStrings`, `StressPointInfo`, `Item_DrillParam`) fills in the mechanics: Crazy Mode is **duration-based** ("%d seconds maintained") and is **reset by changing your equipped drill** or entering a no-crazy zone (the mode's zone list is data-driven). The gauge is per-drill — every drill in `Item_DrillParam` (191 of them) carries its own **CDM_GaugeMax** and **CDM_StressBonus**, plus a **Grade**, a **GroundNature** enum (the ground-type specialization, real in data), DigDepth, effective area, gauge speed, scoop mass, and DrillLife. `StressPointInfo` defines five stress event types (0.15 / 0.35 / 1.5 / 0.25 points, with −999 as the reset value). And `DrillGradeExpRate` scales drill **EXP by drill grade** — grade 0 = 1.0×, rising through 6× / 12× / 20× / 30× / 42× / 56× / 72× / 90× / 111× / 136× … up to grade 20: better drills are EXP multipliers, not just depth.

## Auto-drilling pets

**Driller Boy** (Lv 10, MyShop, 2,900 pts, 15 days) and **Driller Girl** (Lv 45, 2,900 pts, 15 days), plus Super variants (30 days): with the pet equipped, pressing **D** makes your character auto-drill — it moves half a step and drills repeatedly until drills run out (puppy-eyes emote on empty digs). Timed pets can be recharged via Pia's Recharge Service with **Recharge Coupons** (LifeTO's guide calls this "Idle Drilling"; the pets themselves are official MyShop items). The Korean community calls Driller Boy **드릴군 (Driller-kun)** — its 2013 Korean event variant was the **Baby Driller-kun** pet, and a Korean community tip rates Crazy Drilling as mainly worthwhile on Foxes (whose drill skills synergize), with other characters better off buying drills from personal shops. The line's Korean origin is dated precisely by the press: Entriv Soft announced **Driller-kun on November 23, 2011** as a pet that **digs *and* loots on its own** — one button starts fast self-drilling — sold in **Lv 100 and Lv 200 variants** with large weight capacity for mass excavation, and **gifted free to every player who logged in by December 21, 2011**, alongside an island-wide **Poppuri Box hunt** whose per-box rewards ran to the EXP booster armband, Artisan's Flame, and GM gift boxes.

The client's `AutoDrillPetInfo` confirms the full auto-drill pet roster — **7 pets**, each with a fixed **3,000 ms (3-second) dig cycle**.

## Related systems

- [Card Identification](07-card-identification.md) and [Gacha](23-gacha.md) both reuse the drilling metaphor
- [Stats](02-stats-and-base-leveling.md) (DA/WT)
- [Events](30-events.md) (Poppuri drilling events)

## Sources

- Trickster Online Korean client data tables (user-provided `xml.zip`, 2026-09): `Item_DrillParam.xml` (191 drills: grade, ground nature, depth, CDM gauge/stress), `StressPointInfo.xml`, `DrillGradeExpRate.xml`, `AutoDrillPetInfo.xml`, `CrazyDrillStrings.xml`, `TreasureMap_Item.xml` / `TreasureMap_Teleport.xml` (67 treasure maps, 5 candidate spots each)

- [Caleb's Drilling Guide — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Caleb%27s_Drilling_Guide.html)
- [Drilling — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Drilling.html)
- [Digging — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Digging.html)
- [Drilling — CoraTO Wiki](https://mewsie.world/CoraTOWiki/index.php/Drilling) (lightbulb/squiggle/surprise, crazy drilling, AFK drilling)
- [Crazy Drilling — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Crazy_Drilling.html)
- [Drills — PandaTO Wiki](https://pandato.fandom.com/wiki/Drills) (drill table)
- [Driller Boy / Driller Girl / Super Driller Boy — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Driller_Boy.html)
- [Alan — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Alan.html) (treasure hunts, feathers)
- [초반에 구매하면 좋은 마이샵템 — arca.live Trickster channel](https://arca.live/b/trickster/107457369) (Driller-kun, Crazy Drill tip)
- [매드레이 공략 — 네추럴트릭스터 blog](https://myashdd.blogspot.com/2020/07/1.html) (GPS radar hunts)
- [Black Market — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Black_Market.html) (Weird Treasure Maps)
- [엔트리브소프트, 트릭스터에 신규 펫 '드릴군' 출시 — 게임동아 (2011-11-23)](https://game.donga.com/59719/) (Korean launch date, Lv 100/200 variants, auto-dig + auto-loot)
- [트릭스터, 자동 아이템 발굴 신규 펫 '드릴군' 출시 — 천지일보 (2011-11-23)](https://www.newscj.com/news/articleView.html?idxno=105200) (free-gift event, Poppuri Box hunt rewards)
- [Surprise Spot Quests Guide — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Surprise_Spot_Quests_Guide.html) (Reina/Marky quest structure, 50-quest unlock, daily vs infinite tiers)
- [Category:Surprise Spot Quest — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Category_Surprise_Spot_Quest.html) (the 43-quest catalogue)
