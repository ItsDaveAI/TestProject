# Card Identification

## Overview

Card Identification (CID) is an **Enlightenment-era system** (Season 2 content) in which players use the power of **Harkon** to find **Secret Cards** hidden inside ordinary monster/character cards — a separate use of the card inventory from [Card Battle](06-card-battle.md). It feeds into the Soul Seed/Guardian chain and is a major source of Chaos's Feathers (for [Tempering](10-tempering.md)).

## Unlocking

The **Card Identification skill** (On/Off type, MP 30) is earned through the Card Identification quest chain, started in **Poppuri Dungeon - Rainbow Cave**:

1. Talk to **Curious Poppuri** (Rainbow Cave) → teleport to **Poppuri Dungeon - Mysterious Space**.
2. **Fairy Nono - First Special Trickster Power**: requires the Trickster Certificate (from Artisan Poppuri - Giant's Poppuri Treasure); conditions Lv 65+, 2nd job. Rewards the Card Identification skill.
3. Follow-up quests (Fairy Nono - Create a Trickster Crest) send you through the Courage / Wisdom / Dream / Love Trials for crests. Chain prizes include 4× Flower of Revival, potions, Scared Poppuri's Treasure 3, 5× Harkon Shard, and the Arcana Love / Dream / Smart / Brave cards.

## How identification works

(Client data confirms the reward structure:) `CardIdentify_Exp` sets identification payout at **TM EXP only** — base-EXP ratio **0**, TM ratio **1.0** ("기본 경험치") — which is why CID was *the* TM-farming loop. `CardIdentify_ComboTable` is the **combo multiplier**: consecutive identifications pay **1× / 2× / 4× / 7× / 12× / 19× …** (51 combo tiers), and `CardIdentify_GradeInfo` splits results per card **grade 1–12**, each grade rolling two result tables at fixed rates plus a **Special table** at its own rate (the `CardIdentify_ResultTable1–12` / `SpecialResult1–12` files hold the actual loot pools).

**The loot pools themselves:** each of the 12 result tables holds ~**40 items with exact drop rates** — e.g. Table 1: One-shot Potion and Gold Pearl Potion at **30%** each, Miracle/Sand/Ground Drill No. 1 at **5%** each — while the 12 Special tables carry the prizes: **transformation picture frames (변신 액자) at 26%** — Baby Rabbit, Baby Buffalo, and the other baby-animal transformation frames are the Special-table jackpot.

- Every Monster/Character Card is numbered **1–15**; each number carries fixed **Life** and **Gauge** values used in the identification minigame:

| Card # | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Life | +6 | +5 | +5 | +4 | +4 | +4 | +3 | +3 | +3 | +4 | +4 | +4 | +5 | +5 | +6 |
| Gauge | +0 | +6 | +2 | +8 | +4 | +0 | +6 | +2 | +6 | +0 | +4 | +8 | +2 | +6 | +0 |

Example cards per number: No. 1 — Don Cavalier; No. 4 — Tutankhamen, Bug Bear, Red Salamander; No. 5 — Sand Demon, Isis, Dancer Isabelle; No. 6 — Queen Mummy, Forest Mantis, Swamp Shark.
- Running identification on cards reveals whether a **Secret Card** is hidden inside.
- **Collecting all 16 Secret Cards** yields a **Secret Space Map**, which grants access to **Janus's Secret Hideaway - Memory of Flames** (via the related "Surprise Spot" content), where the Soul Guardian quest chain continues (Living Flames dropped by Red Flame Spirit Lv 180).
- Identification also disgorges practical loot on every run — potions, **transformation picture frames (변신 액자)**, and equipment-enhancement items — with Secret Cards at low chance, so Korean guides advise running it with an empty inventory. **Harkon Shards** come at random from the **Harkon Relic** item.
- On the Korean service the same chain fed **awakening**: Secret Cards (also obtainable from Nephtri's **Dimensional Card Pack**) assemble the Secret Space Map used for the Lv 180 Guardian awakening (see [Guardians](13-guardians.md) and [Korean version systems](33-korean-version-systems.md)).

## What CID feeds

- **Soul Seed / Soul Guardian quests** (see [Guardians](13-guardians.md)) — prerequisite skill.
- **Chaos's Feathers** — CID is a repeatable source for tempering materials at every feather tier.
- **Harkon Shards / Arcana cards** — exchange and equipment prizes.

## Related systems

- [Card Battle](06-card-battle.md)
- [Guardians](13-guardians.md)
- [Tempering](10-tempering.md)

## Sources

- [Card Identification Quests Guide — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Card_Identification_Quests_Guide.html)
- [Card Identification (skill) — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Card_Identification.html)
- [Card List by Number — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Card_List_by_Number)
- [Soul Guardian Quests Guide — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Soul_Guardian_Quests_Guide.html) (Secret Space Map, Janus's Hideaway)
- [Card Identification Guide — PandaTO Wiki](https://pandato.fandom.com/wiki/Card_Identification_Guide) (Life/Gauge table, cards by number)
- [Alan — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Alan.html) (feather sources)
- [전직/카드식별/영혼의 씨앗/각성 퀘스트 — cyan's Trickster blog](https://livehepa.blogspot.com/2020/11/trickster-job-change-card.html) (CID rewards, Dimensional Card Pack)
