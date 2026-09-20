# Stats & Base Leveling

## Overview

Trickster Online has **two leveling systems**: base leveling and TM leveling (covered in [TM levels & skills](03-tm-leveling-and-skills.md)). Base level is the primary character level.

- Base EXP percentage shows as a long yellow bar at the top of the screen.
- Each base level grants **4 points** to allocate among **12 stats** in the **MyView** window.
- Base level gates equipment (level requirements) and is the requirement for job advancements and content entry.

## The 12 stats

Stats are grouped under the four types:

| Group | Stat | Effect |
| --- | --- | --- |
| Power | **AP** (Attack Power) | Physical hit damage; main Power-type damage stat (also boosts some Charm skills) |
| Power | **AC** (Accuracy) | Whether physical hits/skills miss; vital for everyone, and the main stat for Lions' gun abilities |
| Power | **DX** (Dexterity) | Attack speed — lower is faster; invisible cap of −40 |
| Magic | **MP** (Magic Points) | Mana pool for spells |
| Magic | **MA** (Magic Attack) | Spell damage; main Magic-type damage stat |
| Magic | **MD** (Magic Defense) | Defense against magic attacks |
| Sense | **WT** (Weight) | Carry capacity; above 90% weight your character walks instead of runs |
| Sense | **DA** (Detect Ability) | Drilling detection — higher DA tells you "an item is not here"; at **90 DA detection is 100%** and you never drill up nothing. Main stat for non-gunner Foxes and hybrid Lions |
| Sense | **LK** (Luck) | Whether your attacks are blocked and whether you block/critical; popularly believed to influence Mature Compound results (largely chance) |
| Charm | **HP** (Health Points) | Survivability; boosts some Charm skills |
| Charm | **DP** (Defense Points) | Physical damage reduction; boosts Cat's Siren Song damage |
| Charm | **HV** (Hit Evasion) | Physical dodge; also a main damage stat for several Charm skills |

## Growth and builds

At character creation you pick a **Build Graph** of four digits — **Power / Magic / Sense / Charm** (e.g. `4123` = Power 4, Magic 1, Sense 2, Charm 3), shown in the creation screen with per-type explanations. Your type's own digit is **locked at 4** and can never change (a Power type always has 4 Power — a "1432 Bunny" is impossible). The graph drives automatic stat growth per level; on top of that, the 4 bonus points per base level go into the 12 individual stats — conventionally **all** into a single stat ("all-AP", "all-MA", "all-DA"...), because spreading points thin produces a weak character.

**Classic beginner builds:**

| Character | Graph | Bonus points into |
| --- | --- | --- |
| Bunny / Buffalo | 4114 or 4123 | AP |
| Sheep | 1432 / 1423 (Earth: 1423 or 1414; future Dark Witch: 1432 or 1441) | MA |
| Dragon | Dark 1432 / 1441; Light 1432 / 1423 / 1414 | MA |
| Fox | 2143 or 1144 | DA |
| Lion (gunner) | 2143 or 1144 | AC |
| Cat | 3124 or 4114 | AP (Evolution cats) or HV |
| Raccoon | 3124 or 4114 | AP; Metamorphosis raccoons always HV |

Because Sense types carry a locked 4 in Sense, Fox and Lion are the game's natural drillers; any other character who invests heavily in Sense can also drill well. Era PvP warning from the same guides: don't build a character purely for PvP/GvG without strong MyShop gear — those modes were overwhelmingly equipment-dominated.

**Derived stat formulas** (per stat level, from the Charm-type class page): **HP = stat level × 30 + 90**; **DP = stat level × 4 − 8**. Similar linear formulas govern the other stats — which is why graph builds (4-digit builds above) matter more than single points.

**Per-level stat growth** (ggFTW archive's documented baseline rates — the Build Graph then multiplies each group: **4 pips = 1 stat level**, and each graph digit sets how many pips its group gains per character level):

| Stat | Baseline growth |
| --- | --- |
| AP / MP / HP | **+4 AP, +30 MP, +30 HP per level** |
| WT | **+80 per level** |
| DP / MD | **+4 per level** |
| AC / MA / DA / LK / HV | **+1 per 4 levels** |
| DX | **−1 per 12–13 levels** (lower is better; attack delay only — unaffected by skills and guns) |

Interaction notes from the same archive: **LK** governs spell/gun hit rate, spell/gun evasion, and critical rate (its — and DA's — rumored compound-result influence is explicitly marked *disputed* there); **HV** resists gun damage and powers several Raccoon skills.

**EXP curve:** the eTO experience chart shows the steep joint base/TM climb — Lv 25 needs 118,900 base / 95,030 TM; Lv 49 needs 836,340 base / 2,449,250 TM (the TM requirement jumps hard approaching 50); level 332's requirement was corrected to 246,191,680. Full curve on the ggFTW Experience Chart page.

## Weight

Every item has a weight value (WT). Exceeding 90% of capacity makes your character walk until items are dropped, sold, or stored (bank/storage/personal inventory). Weight management is a real constraint on long farming sessions.

## Level-up reward boxes

At milestone base levels the Megalo Company delivers a **gift box to your MyShop inventory** ("a gift from Megalo Company") — open the MyShop window to claim it. Documented examples: **Lv 15** → Lotus Leaf Hat; **Lv 30** → extra ears/tails mail (sellable for starter galders); **Lv 40** → a timed **Stallion Sprint** (the MyShop speed-accessory family); **Lv 50** → a 100k Galder Check; **Lv 100/180** → a **Booster Bracer Ex** — a timed accessory that multiplies **EXP and TM EXP ×3**; **Lv 120** → 2× Resurrect Scroll. The 3rd-Job Guide (Lv 120) and Eclipse's Message (Lv 180) letters arrive through the same channel. The boxes are non-tradable and non-bankable.

## Related systems

- [Character types](01-character-types-and-creation.md)
- [TM leveling](03-tm-leveling-and-skills.md)
- [Maturing Compound](09-maturing-compound.md) (equipment can compound most of these stats)
- [Star Gazing](16-star-gazing.md) (temporary stat boosts)

## Sources

- [Trickster Online — Wikipedia](https://en.wikipedia.org/wiki/Trickster_Online) (leveling system, 4 points / 12 stats)
- [Character Stats — PandaTO Wiki](https://pandato.fandom.com/wiki/Character_Stats) (12 stat descriptions, DX cap, 90 DA rule, 90% weight)
- [Digging — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Digging.html) (Sense 4 growth, DA benefits)
- [Common Character Builds for Newbies — GameFAQs Trickster Online board](https://gamefaqs.gamespot.com/boards/926855-trickster-online/44168520) (build table, all-points convention, PvP warning)
- [How are they reading the numbers? — GameFAQs board](https://gamefaqs.gamespot.com/boards/926855-trickster-online/41269566) (P/M/S/C digits, locked type stat)
- [Picking Your First Character — Trickster Online Amino](https://aminoapps.com/c/trickster-online/page/user/willard-trees/DZze_wlCdfmJvq78lRrP4Mz00KBKMVpqEX) (creation-screen Build Graph UI)
- [Charm Type — Trickster Online Miraheze wiki](https://tricksteronline.miraheze.org/wiki/Charm_Type) (HP/DP derived formulas)
- [Stats — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Stats.html) (12-stat growth rates, pip mechanics, LK/DA compound dispute)
- [Experience Chart — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Experience_Chart.html) (per-level base/TM curve)
- [Level Up Reward Box Guide — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Level_Up_Reward_Box_Guide.html) (milestone boxes via MyShop)
- [Lv. 15 / Lv. 120 / Lv. 180 Gift Box — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Lv-9.html) (box contents)
- [무게부/신속부 얻는 방법 — cyan's Trickster blog](https://livehepa.blogspot.com/2020/12/trickster-how-to-get-speed-weight.html) (timed speed charms from level-up boxes)
