# Boss Monsters

## Overview

Caballa Island's nine **boss monsters** are instanced-style world bosses guarded by **trial questlines**. Bosses drop coveted equipment ("uniques"), their **cards** (usable in [Card Battle](06-card-battle.md) and GvG Boss Battle), and 5-star boss pets; they anchor the endgame farming loop.

## The bosses

| Boss | Notable location |
| --- | --- |
| **Tutankhamen** | Pyramid Dungeon 7 - Doom of Pharaoh (Desert Beach) |
| **Tombeth** | Oops Wharf region |
| **Captain Skull** | Oops Wharf (pirate boss) |
| **Pirate King Karan** | Ghost Blue / pirate content |
| **Count Blood** | Vamp Castle (Abyss region) |
| **Tenter Lion** | Swamp Dungeon 7 - Tenterlion's Cave (Black Swamp) |
| **Queen Odinea** | Snow Hill region |
| **Soki** | Snow Hill / Tapasco era content |
| **Spicy Dragon** | Spicy Island (Tapasco Volcano) |
| **Mad Ray** | Phantom School's hidden laboratory (Korean-era boss, reached via the rift quest chain) |

Mad Ray (매드레이) is the outlier on the list — a school-laboratory boss rather than a trial-guarded world boss: it **warps away** if your opening burst fails to kill it, and its quest rewards **Phantom Repair Powder** (a self-stacking Repair Powder variant). The Korean revival server Natural Trickster restored its quest rewards.

## Trial systems

Bosses are reached through multi-step trials (party-scale puzzle/defense content):

- **Tenter Lion (Lv 420, Charm type, gun weakness; summons Stoor Worm Lv 221, Slug G Lv 224, Yeti Lv 226, Kilimanjaro Lv 273):** begins with *Protect the Sky Lotus* and follow-on trials via the Frog Shaman; heavy elemental resistances (absorbs water; resists physical/magic/fire/air/electric/earth/dark).
- **Tombeth (Lv 121, Charm type, gun weakness; resists magic/earth/air; HP 6,845×4; summons Chimu Lv 78, Naranjo 84, Monkya 173, Arachne 178; casts Power Blow, Final Blow, Super Hips, Sturdy Shield, Mana Reflector, Magic Meltdown, Cure, Enhanced Resistance):** entry via Rosemary at Caballa Relics Dungeon 3 (1× 500 Galder Coupon; Lv 1–150; re-enterable 20 minutes after your previous Tombeth kill; bring a 60 m+ drill). Seven trials:
  1. Kill 6 Guard Stone Soldiers in 1 minute.
  2. Drill up Torn Clue 1.
  3. Kill 30 Awakened Guiana in 10 minutes.
  4. Drill up Torn Clue 2.
  5. *Waking the Ancients* — 5 Philosopher's Stones from Awoken Mimics, then a hidden wall southwest of Explorer Reina.
  6. *Guide Stones* — an 11-room maze walked with Brick (+1 room), Chaotic (random), and Chaotic+Fractal (+4 rooms) guide stones via Keeper Julio and Guide Sabrina — dodging Awakened Chimu's **Banish**, which teleports you back to Megalopolis.
  7. Final teleport into **The Trident Maze** for the fight itself.
- **Spicy Dragon (via Cletta at Spicy Island — bring 2× Spicy Egg):** a four-path gauntlet — adventurer tests, **destroy the 5/8 statues** in spawn order, **Leviathan's Trials**, Hunter Master's monster-room trials, **slide puzzles (3×3, 4×4, 5×5)**, a storyline chain (Cletta's Crystal, Fortune Teller, Leviathan's Help with an invincible monster only Leviathan's spell can kill), then the pre-boss kill. New Spicy Dragon respawns **60 minutes** after the previous kill.
- **Tutankhamen's Trial** rooms (Test of Calmness / Power / Knowledge / Quickness) sit inside the Pyramid Dungeon — the "Room of Guardian" tests double as early trial content.

## Boss content ties

**Legendary Unique gear is boss content (client data):** the boss-themed legendary equipment — Tutankhamen's Gold Sword/Pharaoh Hat line, Count Blood's Blood Sword/Vampire Mark, Captain Skull's White Gun/Red Eyepatch/Black Hat, Tenterion's Tail Spear — doubles as a **dialog key**: Tapasco NPCs' trees branch on *wearing* it ("오! 전설 유니크 장비를 갖고 계신 분이로군요!" — "Oh! One who carries Legendary Unique equipment!"), with quest-state checks offering legendary-holder-only options — and the lore ties them to "the adventurer who helped Leviathan and Spicy Dragon" ([Spicy Dragon](#the-bosses)'s trial gauntlet). Boss hunting → legendary sets → Set titles ([Chaos Tower — Titles](28-chaos-tower.md)) → Tapasco's recognition quests is a closed loop.

**The official boss roster (client data):** `BossHistoryList` tracks exactly **nine bosses** in the kill-history system — **Tutankhamen, Tombeth, Captain Skull, Tenterlion, Count Blood, Queen Odinea, Soki, Spicy Dragon, and Pirate King Karan** — the game's formal answer to "which world bosses count."

**Boss behavior scripts (client data):** `BossMonsterparamEx` (224 boss rows, 529 KB) is the boss master table — per boss: **LifeCnt** (multi-bar lives), a **summon block** (up to 4 summon monster IDs with min/max counts, summon type, interval, total cap, and despawn rules), and **heal blocks** (HealLeftLife / HealLevel / HealTime — bosses that heal themselves on thresholds). The summon tables in this file (Tenter Lion's Stoor Worms, Tombeth's four adds…) are one row each there.

**The boss-spawn footprint (client `BossMon_*`):** **239 per-map spawn tables — 218 populated, 333 spawn rows** — pin where boss-class monsters appear: one family per region (Beach, Coral, Relics, Wharf, Seabed, Rose, Snow, Swamp, Mirage, Marine, Alteo, Abyss, the Office/Path maps…) covering that region's field, dungeon, mine, and play maps, plus the **event park** (Halloween) and the instanced towers (Chaos, Tartaros — see [Chaos Tower](28-chaos-tower.md) / [Korean systems](33-korean-version-systems.md)). Each row locks a boss ID to a count, a check time, and a region gate — the spawn scheduler's raw data. One `BossMon_test` table (18 rows) survives from development.

- **GvG Boss Battle** (see [Guild system](18-guild-system.md)): guilds fight boss-class copies that spawn in level order — "Tutankhamen G" first, Spicy Dragon last — with Recall Tiles choosing the next spawn.
- **Boss uniques:** e.g. the Pharaoh set (excluded from [tempering](10-tempering.md) on official rules); boss drops also feed the [recycling/trading economy](31-economy-bank-trade.md).
- **Boss pets** are 5-star pets for [synergy](12-pets.md).
- Revival servers adjust boss access: xTrickster removed entry level caps and trials entirely; PandaTO allows tempering boss uniques.

- **NPC combat assists (client dialog):** dungeon NPCs can cast skills *for* the player — in Volcano Dungeon 16, **Leviathan himself offers to help** ("why are you struggling against mere monsters? Take my power and finish them!") via `NpcSkillStart` — a borrowed-buff mechanic inside boss dungeon content.

## Related systems

- [Party system](17-party-system.md), [Chaos Tower](28-chaos-tower.md), [Card Battle](06-card-battle.md)

## Sources

- [Category:Boss Monsters — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Category_Boss_Monsters.html)
- [Tenter Lion — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Tenter_Lion.html)
- [Tombeth — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Tombeth.html) (stat block, seven trials, entry conditions)
- [Tombeth Trials — Our Trickster Online Wiki](https://oto.fandom.com/wiki/Tombeth_Trials) (Rosemary entry, 20-minute cooldown)
- [Spicy Dragon — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Spicy_Dragon.html)
- [GvG — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/GvG.html)
- [X Trickster Online (server feature notes)](https://xtrickster.com/)
- [매드레이 공략 — 네추럴트릭스터 blog](https://myashdd.blogspot.com/2020/07/1.html) (Mad Ray laboratory chain)
- Client data: `BossMon_*` (239 spawn tables, 333 rows — the per-region boss-spawn footprint), `BossHistoryList` (9-boss kill history), `BossMonsterparamEx` (224-row boss master)
