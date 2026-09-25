# Monster System

## Overview

Every monster in Trickster carries a full **stat block** — and monsters share the player's skill system. The ggFTW blocks document: **Type** (Power / Magic / Sense / Charm / Neutral), Level, **Weakness**, **Resistance**, elemental attributes, HP shown as bars (e.g. Tombeth 6,845×4, Tenter Lion 23,065×5), AP/MA/DP/MD/GD, an Active flag, **Summon** tables, and **Skills by level** — monster skills are the same skills players use, leveled (Tombeth: Power Blow 4, Sturdy Shield 6, Cure 6; Tenter: Mana Reflector 8, Magic Meltdown 8; boss pages carry the same columns).

## Type, weakness & resistance

- Types mirror the four character types (+Neutral) — a monster's type tells you which stat family it scales on.
- **Weakness** is usually a damage channel: bosses are commonly **gun-weak** (Tombeth, Tenter) while resisting most elements — the era answer to tanky bosses was Lion's guns.
- **Elemental attributes** (Tombeth Earth 48%, Tenter Earth 66%) multiply element skills; resistances (or absorption "at red HP" for some bosses) gate elemental builds per fight.

## Damage tolerance

Bosses carry a **damage-tolerance table** — percentage reduction *per damage channel*: Tenter Lion takes Physical −21%, Magic −1%, Gun −47%, and spread elemental tolerances, so channel choice swings boss damage by double digits. Reading the tolerance table before a boss fight was core era strategy.

## Special monster behaviors

| Behavior | Examples |
| --- | --- |
| **Banish** (teleports you to town) | Awakened Chimu in Tombeth's maze — a run-ender deep in a trial |
| **Warp-away escapes** | Mad Ray (Phantom School lab) warps out if your opening burst fails |
| **Self-destruct** | Ghost Books in Phantom Dungeon — they telegraph "Guaah!" first |
| **Teleport attack** | Dark Ball sends victims to Megalopolis |
| **M-Defense Paralysis** | The monster version of the debuff: 90%+ of its hits crit against you — the most feared monster skill |
| **Guard / Buff Canceller / Deadly Poison / Blood Drain** | The Chaos Tower 2011 boss kit — stop attacking through Guard and Blood Drain |
| **Unkillable wardens** | Wicked Keeper (Lv 400) in Phantom School — one-shots players, cannot be killed; walk around them |
| **Summons** | Tenter Lion's Stoor Worm/Slug G/Yeti/Kilimanjaro; Spicy's salamanders — adds with their own levels and drops |

## Variant families

- **Corrupt / Chaos pairs** — the Chaos Tower's floor monsters (12F: Corrupt/Chaos Golden Mole 147/149; 24F: Naranjo 197/199; 36F: Freyja 247/249), the ladder climbing ~50 levels per 12 floors.
- **Shadow monsters** — infest regular dungeons at endgame levels (Slide Cave: Shadow Kokebi 384 → Shadow Lucia 657) and drive the Shadow World dailies.
- **Requiem Spirits** — the dimensional-gap timed kills on every 12th tower floor (Lv 297 at 24F), the source of Requiem boxes.
- **고신류 (Ancient-god class)** — Tartarus's Lv 618–950 roster ending at True Chronos.

## Monsters → items

**Monster data at scale (client):** the archive's monster layer runs ~**97 Tartarus monster/Boss tables**, per-region `Mon_`/`BossMon_` stat blocks (level, type, weakness, resistance — e.g. the 2nd Harkon Sanctuary's Violent roster Lv 70–140), **522 `Tactics_Mon_` AI-behavior tables**, and the `ESAII_*` family of **monster skill-animation/effect definitions** (500+ skills from Chain Punch to Earthquake to Gellder Hit) — the monster "AI + skill" behaviors the revival wikis describe at case level are fully enumerated in the client. `ChrTypeInfo` confirms the client's nine characters (Rabbit, Buffalo, Sheep, Dragon, Fox, Lion, Cat, Raccoon, **Bear**).

**The AI layer in numbers (client data):** the 522 `Tactics_Mon_` tables hold **1,270 AI rules** between them. Each rule is a conditional: a **FactorType** (the trigger — one dominant type covers 1,234 rules, with rare types 1/3/5/8), a threshold value, an **ActionType** (uniform across the archive), a **Skill_ID + SkillLevel**, a timing field, and an **ActionRatio — the skill's fire probability**, distributed mostly at **90% (444 rules), 50% (260), 80% (114), 70% (153), 60% (35)** with sparse 10–40% rules. In practice: monsters check a condition and roll against a skill's fire chance. The `Mon_`/`BossMon_` tables add the **spawn side** — per-map spawn rows with density **Ratio** (e.g. 2.0), average/maximum concurrent counts (e.g. Avr 10 / Max 10), spawn regions, and retraction behavior; and **10 `MonSpeech_` files give monsters spoken lines** (Cucul, Jellyfish, Mr. Baldy, Persona, Snow…).

**The monster master (client `MonsterParamEx2`, 1,467 rows):** every monster carries **Level, walk/run speeds, stay/chase timers, and per-stat scaling levels** (ApLv/AcLv/DxLv/MpLv/MaLv/MdLv — stats computed from monster level bands, not hand-entered). Levels span **1 to 1005** across 541 distinct values — the 1005-level monster is a Tartarus-era entry. `MonItemDropInfo` (1,091 rows) holds the drop tables (per monster: items with rate + count), `MonsterRegionInfo` binds the 696 maps to their monsters, and `Monster_TacticsEX` (1,706 rows) extends the AI with the advanced behavior set.

**Protection skills and boss immunities (client data):** the `MonProtect_*` tables (P/C/M/S/N — 180 rows) assign monsters **protection-skill ratios by type** (e.g. Charm-type protections at 20% proc), and `MonsterDebuffResist` (7 profiles × 33 fields) gives boss tiers their debuff resistances — the Chaos Tower ≤36F boss profile is fully stun/paralysis/stone/restriction-immune with 50% resistance to stat debuffs ([Chaos Tower](28-chaos-tower.md)).

**Monster data at scale (client):** the archive's monster layer runs ~**97 Tartarus monster/Boss tables**, per-region `Mon_`/`BossMon_` stat blocks (level, type, weakness, resistance — e.g. the 2nd Harkon Sanctuary's Violent roster Lv 70–140), **522 `Tactics_Mon_` AI-behavior tables**, and the `ESAII_*` family of **monster skill-animation/effect definitions** (500+ skills from Chain Punch to Earthquake to Gellder Hit) — the monster "AI + skill" behaviors the revival wikis describe at case level are fully enumerated in the client. `ChrTypeInfo` confirms the client's nine characters (Rabbit, Buffalo, Sheep, Dragon, Fox, Lion, Cat, Raccoon, **Bear**).

Every monster drops its **own card** ([Card Battle](06-card-battle.md) ammunition and the mastery-card economy) plus its Monster Guild quest items; boss kills gate the trial loot (Phantom weapons, uniques, treasure boxes). Monster **cards double as skill mastery items** — the same Clione card masters Power Blow that fights you at Coral Beach.

## Related systems

- [Bosses](27-bosses.md) — the trial circuit; [Skills](03-tm-leveling-and-skills.md) — the shared skill system; [Card Battle](06-card-battle.md); [Quests](25-quests.md) — timed/ranked hunts.

## Sources

- [Tombeth / Tenter Lion / Spicy Dragon — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Tombeth.html) (stat blocks, tolerance tables, skills, summons, Banish)
- [Poppuri Dungeon - Slide Cave / Tower of Chaos floors — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Poppuri_Dungeon_-_Slide_Cave.html) (Shadow/Corrupt/Chaos/Requiem variants)
- [트릭스터(게임)/스킬 — 나무위키](https://namu.wiki/w/%ED%8A%B8%EB%A6%AD%EC%8A%A4%ED%84%B0(%EA%B2%8C%EC%9E%84)/%EC%8A%A4%ED%82%AC) (M-Defense Paralysis, monster skill kit)
- [혼돈의 탑 꼭대기엔… — 경향신문 (2011)](https://www.khan.co.kr/article/201109281518081) (Guard/Buff Canceller/Deadly Poison/Blood Drain)
- [환영학원 퀘스트 공략 — cyan's Trickster blog](https://livehepa.blogspot.com/2020/12/trickster-phantom-school-quest.html) (Wicked Keepers, Mad Ray)
