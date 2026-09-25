# Harkon Protector

## Overview

Harkon Protector is a **recurring group PvE tower-defense event** (Enlightenment content): teams of up to 30 Tricksters enter a regional **Shadow Sanctuary** and defend **5 Harkon Statues** from waves of Shadow monsters for 20 minutes. Success grants fortune boosts and drops; failure grants nothing. "The hint to succeed is coordination."

## Entry

- Requirement: enlightenment (Mind's Eye) for the Shadow-World side of the content (see [Shadow World](14-shadow-world.md)) — but the **Harkon Sanctuary Eclipse appears publicly**: no Mind's Eye is needed to join the defense itself, which is why it served as the group PvE on-ramp.
- Talk to **Eclipse** at the scheduled time; she teleports you to that region's Sanctuary.
- The **first 30 characters** to talk to Eclipse per area are accepted.
- Sanctuaries open at fixed times every day (US Eastern); once a Harkon Statue is destroyed the Sanctuary closes.
- The original-era Sanctuaries were **tiered by level band** — 1st (Lv 30–79), 2nd (Lv 80–129), 3rd (Lv 130–179), each with its own Wicked/Violent monster roster — across **six daily windows** (12:00/14:00/16:00/18:00/20:00/22:00, two per band, announced in Event Garden - Ceremonia 10 and 2 minutes ahead, where **Happisto Stallone** offers three preparation quests). Waves escalate through mid-tier bosses (Wicked Scylla, Hecate, Charybdis — each broadcasting taunts) to **Lord Chronos** himself as the finale.

## Schedule (per region)

| Region | Eclipse's location | Start | End |
| --- | --- | --- | --- |
| Black Swamp | Carbigal | 11:00 | 11:20 |
| Oops Wharf | Oops Wharf | 13:00 | 13:20 |
| Techichi Volcano | Techichi Town - Neil's Camp | 15:00 | 15:20 |
| Tapasco Volcano | Gate of Tapasco Volcano | 17:00 | 17:20 |
| Snow Hill | Snow Hill Town - Laplanoel | 19:00 | 19:20 |
| Rose Garden | Ceremonia | 21:00 | 21:20 |
| Ghost Blue | Aquarius | 23:00 | 23:20 |
| Caballa Relics | Azteca | 01:00 | 01:20 |

## The defense

- In-map UI: a minimap showing Harkon Statue positions, defenders per statue, and attackers per statue, plus remaining time.
- **Multiple assault modes** appear randomly per sanctuary:
  - **Mode 1 — 1st Assault:** 8 waves of monster mobs, each wave ~40 seconds (Wicked Addax Lv 20, Wicked Nephthys Lv 30, Wicked Koom Lv 40, Wicked Aposis Lv 50...), escalating to mid-bosses like Wicked Scylla (Lv 60) with storyline taunts from Chronos/Scylla.
  - Other modes continue with stronger waves and **Shadow Bosses**, ending in a final Shadow Boss.
- PandaTO describes it as PvE tower defense where AoE skills and group strategy carry the run; staff-run "Harkon Raids" with prizes are a server addition.

## Rewards

- **Top monster-killer:** Harkon Protector Fortune 3-hour boost (AP +528, AC +33, DX −11, MA +33, MD +528, DA +33, LK +33, DP +528, HV +33).
- **Remaining survivors:** Fortune 3-hour boost (AP +168, AC +7, MA +7, MD +168, DA +7, LK +7, DP +168, HV +7).
- **Monster drops:** shadow equipment, boss shards, HP & MP potions, galders.

## The 2012 Korean renewal

The November 2012 Korean update reworked 하르콘 수호전 into **four game modes**:

| Mode | Play |
| --- | --- |
| **Defense (수호모드)** | Protect 5 Harkons from encroaching monster waves |
| **Siege (공성모드)** | Defend a single Harkon from charging monsters, fighting alongside NPC allies |
| **Infinite (무한모드)** | Defend the Harkon against monsters that revive 50+ times |
| **Harkon Boss Battle** | Assault a powerful boss supported by special items/equipment |

Entry became **level 30+, six runs per day**, via Eclipse at Event Garden - Ceremonia. The Korean schedule ran by **level bracket, two windows each**: 1st defense Lv 30–79 at 0:00 and 18:00; 2nd Lv 80–129 at 14:00 and 20:00; 3rd Lv 130–179 at 16:00 and 22:00 (dying mid-run just means re-entering). The renewal event awarded **Harkon Exchange Tickets / Harkon Coins** (up to 500 by cumulative attendance) plus Pet Rice Balls.

## Speed-charm economy (신속부)

The defense became the game's non-cash source of **move-speed accessories**: **Happy Stollon** at Event Garden - Ceremonia exchanges **Evil Thought Masses** and **Corrupted Souls** (dropped by the 1st/2nd/3rd defense brackets, tradable) for unlimited-duration brands:

| Accessory | Level | Move speed |
| --- | --- | --- |
| Mega Brand 30 / 60 | 30 / 60 | +40% / +45% |
| Giga Brand 80 / 110 | 80 / 110 | +50% / +55% |
| Tera Brand 130 / 160 | 130 / 160 | +60% / +70% |

Each comes in Power/Charm (AP, AC, LK, DP, HV) and Magic/Sense (AC, MA, DA, LK — twice the weight) variants; any class can wear either. Every new character also receives a free **Broken Speed Charm** (+30% move speed, unlimited duration, accessory slot). Community advice: jump from the starter charm straight to Giga/Tera — the low tiers are skipped while leveling fast.

## Related systems

- [Shadow World & Mind's Eye](14-shadow-world.md) — entry requirement and schedule
- [Guardians](13-guardians.md)
- [Star Gazing](16-star-gazing.md) — parallel fortune boosts

## Sources

**The defense economy (client data):** `HarconDefInfo` (27 rows) configures each defense instance (level, item, unlock ID, **MinP/MaxP player counts**, wait map); `HarconDefDrop` scales rewards by **win count** (defense #1 pays 3 drops, declining to 1 by the 10th — fresh content paid best); `HarconShop_1/2` (53 goods) are the **defense-exchange shops**, stocking **Nate's Compound Frames (조합틀) by level 15–85+** and more; and `HarconRecordInfo` (23 records) is the **record board** — named stats with units and display colors. The `HarconMission*_Str` families carry the three mission briefings' text.

**The wave engine (client data):** the `Sc_HarconDef_*` family holds the event's scenario scripts — six per themed mode (Ancient 1–6, plus Fire, Ice, Fantasy, and the Eagle event variant, each 15–24 rows) — where **each row is one wave carrying up to 20 simultaneous monster slots**, every slot specifying the monster ID, maximum count, spawn position, spawn lump size, and spawn delay. The four-mode Harkon Defense of the 2012 renewal (Ancient/Fire/Ice/Fantasy) is scripted row-by-row in these tables, alongside the boss-script file — and the mode's boss spawns are registered in their own `BossMon_Harcon1th/2th/3th` and `BossMon_EP6_Harcon` tables.

- [Harkon Protector — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Harkon_Protector.html)
- [1st Harkon Sanctuary Assaults — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/1st_Harkon_Sanctuary_Assaults.html)
- [Harkon Protector — PandaTO Wiki](https://pandato.fandom.com/wiki/Harkon_Protector)
- [Eclipse — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Eclipse.html)
- [트릭스터, 디펜스 모드 '하르콘 수호전' 리뉴얼 — 게임톡 (2012-11-21)](https://www.gametoc.co.kr/news/articleView.html?idxno=5452) (four modes, level 30+, 6/day, event)
- [무게부/신속부 얻는 방법 — cyan's Trickster blog](https://livehepa.blogspot.com/2020/12/trickster-how-to-get-speed-weight.html) (bracket schedule, Stollon exchange table, Broken Speed Charm)
- [Harkon Sanctuaries — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Harkon_Sanctuaries.html) (level-band tiers, six PST windows, public Eclipse, Stallone quests)
- [1st Harkon Sanctuary Assaults — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/1st_Harkon_Sanctuary_Assaults.html) (wave script, Scylla/Hecate/Chronos broadcasts)
- Client data: `BossMon_Harcon1th/2th/3th`, `BossMon_EP6_Harcon` (mode boss spawns), alongside `HarconDefInfo`/`HarconDefDrop`/`HarconShop_*`/`HarconRecordInfo`/`Sc_HarconDef_*`
