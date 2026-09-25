# TM Levels & Skills

## Overview

Alongside base levels, Trickster Online has a **TM (Type Master) leveling system**. TM EXP is displayed as a green bar (in the Skills window, under the base bar). Each TM level grants **1 TM point** used to learn a skill, raise a skill's level, master a skill, or save for later.

TM levels grow independently of base levels — a character can be high base level with low TM, which matters because every skill has a TM level requirement.

## Earning TM EXP

The client's `TM_LEVEL2` table is the **complete TM EXP curve — 601 rows, TM levels 0 through 600** (the first steps: Lv 0→1 costs 320 TM EXP, then 460, 680, 1,000, 1,440, 2,020, 2,760 …, steepening thereafter). TM 400+ exists in data because late-era guardians, Tartarus, and 3rd-job mastery kept raising the ceiling.

**The complete skill registry (client data):** `SkillParam2` defines **all 402 skills in 45 fields each** — every skill's ID, type, name, icon, descriptive text, **SkillCardID (its mastery card), MaxSKLV (max level), MasterTMPoint (TM points to master), and QuestID — the quest through which it is learned** — plus element, spell type, up to three assist-skill references, skill-EXP, and grade. The per-level numbers live in `SkillParam_Item`, and the `SkillMasterInfo` table (230 rows) maps the skill-card shops, with `SkillShopItem_*` pages per town (Relics Town 1–9, Cora 1–4, the Skill Shrine) and `SkillScroll_Info` (82 skill scrolls). Even "발굴 삼매경" (Invincible Drill) is here with its learning quest (QuestID 13) — the registry is the spine behind every tree in this file.

**Skill-teaching scrolls (client `SkillScroll_Info`, 82 entries):** a second way to learn — consumable **scroll items that grant a specific skill at a fixed level** (item 37000 → skill 7001 Lv 1, and so on). These are the **Secret Scrolls** the [Recycle shop](24-recycling.md) pays out and the event-distributed learnables — one item ID per skill, at one fixed skill level each.

The client's `TM_LEVEL2` table is the **complete TM EXP curve — 601 rows, TM levels 0 through 600** (the first steps: Lv 0→1 costs 320 TM EXP, then 460, 680, 1,000, 1,440, 2,020, 2,760 …, steepening thereafter). TM 400+ exists in data because late-era guardians, Tartarus, and 3rd-job mastery kept raising the ceiling.

- **Hunting monsters** (notably ones below your level) and **quests** (monster quests, card quests, and TM-focused quests such as Love Hunter's).
- **Drilling** — you gain base EXP on every drill attempt, but **TM EXP only when you actually dig up an item** (formula in [Drilling](05-drilling.md)).
- **Card Battles** award EXP in proportion to points won.

## Learning and using skills

1. Buy **skill cards** from your type's Skill NPC (located in Desert Beach Town/Paradise, Relics Town - Azteca, and the Garden of Skill Master in Megalopolis).
2. Open the Cards window (**C**), switch to the Skill tab, and double-click an unshaded card to learn it (costs TM points).
3. Open the Skills window (**S**) to raise skill levels with TM points, and drag skills to the quickslot bar.
4. Skills level 1–10, then can be **mastered** using extra TM points plus a **mastery item** — e.g. Power's Power of Unity (혼신의 힘) needs 2× Crione Card; Card Strike needs 2× Ironclad Turtle Card; Bolster Ballad needs 3× Ash Soldier Card. Many skills also require **prerequisite skills at a given level** (Super Hips needs Dodge Master Lv 10; Uppercut needs the Lv 40 uppercut starter).

## Skill types

| Type | Behavior | Examples |
| --- | --- | --- |
| Timer | Applies attribute changes for a duration to self/others | buffs, Mind's Eye |
| On/Off | One-time-use attack skills and spells | Card Strike, attack spells |
| Passive | Always in effect without MP | Heavy Carrier, Super Hips |

## Skill tiers

Korean guides organize every character's kit in three tiers:

- **0th-tier (0차)** — the base skills every character of a type shares from level 1.
- **1st-tier (1차)** — the 2nd-job skill tree, learned by the pure class; the **counterpart hybrid** learns the same tree at **+50 TM levels** (e.g. Boxer skills at TM 51 for a Bunny but TM 101 for a Mercenary-hybrid Buffalo).
- **2nd-tier (2차)** — the 3rd-job (pure/hybrid) skill trees.

## Example: the Power ladder (Bunny / Buffalo)

The Korean skill wiki documents the shared Power 0th tier and the Boxer (Bunny) 1st tier — a representative picture of how a Trickster skill tree is actually built (TM requirement in parentheses; Mercenary-hybrid numbers alongside):

**0th tier (shared Power skills — Pola cannot learn these):**

| Skill | TM | Effect |
| --- | --- | --- |
| Power Punch (기운찬 주먹) | basic | Fixed 100-damage starter attack, abandoned as you level |
| Power of Unity (혼신의 힘) | 1 | +15% per level, 300% at master; mastery needs 2× Crione Card — mostly a prerequisite skill |
| Bull's-Eye (백발백중) | 10 | +36% (45% mastered) accuracy — the "all-accuracy" build's core; prerequisite of Heartbeat and Hawk Eye |
| Tenacity (불굴의 투지) | 20 | 2-hit strike that deals 1-hit damage with near-zero cooldown — the actual early main attack |
| Shake Attack (흔들어택) | 20 | Lowers the target's hit rate (%) |
| Sabotage (방해공작) | 20 | Lowers the target's DA |
| Heartbeat (고동치는 심장) | 25 | +AP% (20% mastered) — Power's must-master buff |
| Disarm (무장해제) | 30 | Lowers monster DP (era-bugged with no debuff indicator; now considered dead weight) |
| Unlucky Fist (불운의 주먹) | 30 | −51% LK at master; a debuff players skip but **guardians learn for Chaos Tower bosses** |
| Quick Motion (빠른 몸놀림) | 30 | Reduces DX (faster attacks); Guard's prerequisite |
| Uppercut Starter (올려치기) | 40 | The cross-counter setup; prerequisite of Uppercut — only Duelist-track Buffalo and pure Bunny take it |
| Whirlwind Attack (회오리 어택) | 50 | 3–5 hit multi-strike; luxury pick |

**1st tier (Boxer — Bunny; Mercenary-hybrid Buffalo in parentheses):**

| Skill | TM | Effect |
| --- | --- | --- |
| Defense Paralysis (방어마비) | 51 (101) | Chance debuff; when it lands, your hits near-always **critical with ~100% accuracy**. The monster version (M-Defense-Paralysis) is one of the most dangerous debuffs in the game — 90%+ of its hits on you crit and can one-shot |
| Dash (대쉬) | 60 (120) | Rushes toward the clicked direction; cancels mid-dash; staple for hunting and PvP (declined once speed charms became farmable) |
| Uppercut (어퍼컷) | 60 (110) | Boxer's first main nuke — strong but 11 s cooldown even mastered; enhanced by Counter Punch |
| Chain Punch (연속펀치) | 85 (135) | 4 consecutive hits, 4 s cooldown — replaces Tenacity as the field skill; out-damages a non-crit Uppercut, but the long animation means you can be beaten to death mid-cast (Guard during it) |
| Counter Punch (카운터 펀치) | 100 (150) | Chance follow-up that boosts Uppercut's damage |
| Guard (가드) | 110 (160) | Blocks up to **5 physical attacks 100%** at master — the boss-fight staple (stacks with HV evasion);Defense-Paralyzed monsters shred the stacks |
| Hawk Eye (매의 눈) | 110 (160) | +AC (22% mastered) **for the whole party** |
| Combo Punch (콤보펀치) | 120 (170) | Doubling-damage chain; a miss keeps the multiplier but wastes the hit |

Every other type follows the same shape (Magic's Bard/Magician trees, Sense's Explorer/Inventor trees, Charm's Entertainer/Card Master trees — e.g. Card Strike consumes an Empty Card for splash AoE scaling on AP + HV×8).

## Type scaling and the Charm 0th tier

Each type's kit scales on different stats, with its own default growth graph: **Magic** — Magic 4 / Sense 3 / Charm 2, scaling on **MA with LK governing spell hit rate** (bonus points conventionally all into MA; the M4/S4 high-hit glass build is usually reached with a graph-reset item); **Sense** — DA (Fox), AC (Lion guns), and LK; **Charm** — Power 3 / Sense 2 / Charm 4, scaling on HV, AP, and HP.

The **Charm 0th tier** (Cat/Raccoon shared) shows how formula-driven the kits are:

| Skill | Effect |
| --- | --- |
| Power Blow | Basic hit — Lv 30–: level + 120 + AP; Lv 31+: 150 + AP, ×multiplier (boosted by Titanium Wrist) |
| Dodge Master | +% HV (HV × increase %) |
| Magic Meltdown / Magic Defense Breaker | Lower the target's MA / MD by HV-derived amounts (MD −= HV × % × 16) |
| Mana Reflector | Reduces **and reflects** magic damage: reduction % = (30 + HV) × duration ÷ 100 |
| **Galder Thrower** | Consumes **100 galders** for **fixed damage** (800 at master); accuracy = 32.5 + target HV × 2.5 — the anti-defense money attack |
| Shield All / Sturdy Shield | Party DP buff (DP × %) stacking with the personal DP buff |
| Skunk Pouch | Chance **stun** |
| Physical Training | +2,360 HP at master |
| Final Blow | Damage scales with missing HP: {AP + (max HP − current HP) ÷ 10} × multiplier × 2/3 |

Magic's 2nd tier adds the element system: Bard picks **two adjacent elements from the wheel of five** and Magician an exclusive Light/Dark choice — see [Character types](01-character-types-and-creation.md). The pairings settled into a meta (cyan's guide): **Water + Electric** for its burst combo (the popular Soul Master pick), **Fire + Electric** combining AoE with multi-hit (the common Witch pairing), and **Wind** alone as the fastest farmer via Wind Blade spam — while Sheep Witches overwhelmingly chose **Light** over Dark, because Light Witch learns Magician's shield skills where Soul Master gets no defense line at all.

**Magic & Sense skill rosters** (mastery cards in parentheses — one card can master several skills): Magic carries Shockwave and Mana Arrow (Clione), Cure (Hula Octopus), Bottle of Mana + Aura of Mana + Luck Breaker (Silver G), Mana Web + Rust (Gold G), Mana Ring (Nephthys), Mist of Mana (Koom), Mana Storm (Larva), and Mana Shield (Turvy) — and **one Relics card, Lima, masters all five Bard element basics** (Drip Bomb, Electro Attack, Whirlwind Blaze, Cleaving Terra, Wind Blade). Sense carries Sixth Sense + Stone Strike (Clione), Heavy Carrier (Hula Octopus), Shuriken Master (Oran G), Sticky Foot (Silver G), Shockvibe (Gold G), Lucky Seven + Tornado Bomb (Guiana), Basic Detection (Larva), Armor Breaker + Gun Booster (Turvy), Lucky Fist (Royal Jelly ×55), and Sense Breaker (Book of the Dead ×20, drilled).

## The Sense 0th tier — DA, AC, and the gun

The Sense kit (Explorer, shared Fox/Lion) doubles as the game's utility layer:

| Skill | Effect |
| --- | --- |
| Stone Shower | Starting skill (granted at creation, never sold) — fixed 75 damage at TM 1, MP 20, 2 s cooldown |
| Invincible Drill | Passive — being attacked no longer cancels drilling (cannot be leveled) |
| Sixth Sense | DA buff: DA × 45% |
| Stone Strike | Single-target: (DA + 1) × (multiplier × 10 × 2/3) |
| Gun Carrier | Passive enabling gun use (cannot be leveled) |
| Heavy Carrier | +3,360 WT at master |
| Shuriken Master | Throws a shuriken **loaded into the gun's "bullet" slot**: {(DA + shuriken AP ÷ 10) × (multiplier × 10 × 2/3)} − 1 |
| Sticky Foot | Lowers the target's HV by a DA-derived amount |
| Invincible Reload | Being hit no longer cancels gun reloading |
| Gun Booster | AC buff while gunning — directly raises gun damage |
| Basic Detection | Marks buried items up to **110 m deep** with red circles — position only, not identity |
| Armor Destructor | Lowers the target's DP |

**The gun formula** is the Lion's defining mechanic — a gun's damage rides the wielder's AC (with LK on hits/crits), not body AP: **gun AP = (AC − 48) × 20 + the gun's own AP**. Hence Lion builds go all-AC, and the Fox splits by job: Thief Master stays all-DA (detection plus Stone Strike/Shuriken damage), Hunter Lord goes all-AC to gun — the DA Fox being the classic drilling/storage alt.

(The full shared 0th tier per the ggFTW archive is **16 skills** — everything in the table above plus **Quick Reload**, **Lucky Seven** (the LK buff, Guiana mastery), **Anger Management**, and **Compound Mastery**.)

## The 2nd-job (1차) signature skills

Each type's 2nd job opens its signature line (hybrids learn the same skills at **+50 TM**, and each type keeps a few skills **pure-only**). The TM-41 tier universally masters via **Ironclad Turtle ×2**; TM-55 skills scatter across Quiem / Requi / Chibcha cards:

| Tree | Skill (TM) | Effect |
| --- | --- | --- |
| **Bard** (Sheep) | Bolster Ballad (40) | **Party MP-cost aura** (10.5% at master) — active only while the caster *stands still*; moving makes it self-only |
| | Elemental Boost (210) | +% to **all five elements**; requires Bolster Ballad mastered — the late-era capstone |
| **Magician** (Dragon) | Hinder Snare (41) | Chance to **root** all enemies around the caster (cannot be leveled) |
| | Light Pact / Dark Pact (55) | Gate passives for the Light/Dark lines — **mutually exclusive** |
| | Arrow of Light (55) / Hellfire (55) | The line's first attacks, both on (MA − 49) × Power ÷ 10 (pillars of light / dark hellblazes, master power 470) |
| **Explorer** (Fox) | Precise Pitch (41) | Empowers Shuriken Master for 120 s: with both mastered, **(DA × 33) + (Throw AP ÷ 10 × 79.2)** |
| | Item Detector | The deeper detection skill (Quiem ×2) |
| **Inventor** (Lion) | Butt Plate (41) | **Rifle-butt melee** for a gunner: (DA + AC − 49) × ratio − 1, master ×3.55 |
| | Power Shot (55) | [(GunAP − 11) + 20 × (AC − 48)] × ratio — the skill-level echo of the gun formula; needs Gun Booster Lv 10 |
| **Entertainer** (Cat) | Volley Kick (41) | **[AP + (HV × 16)] × (m ÷ 8)**, master ×2.325 — the Cat's bread-and-butter single hit |
| | Galder Barrage (55) | Galders → **fixed damage on three targets** (100 galders per the ggFTW archive; the Korean guide recorded 150): ignores DP and physical resistance, **bypasses Shield of Heaven**, blocked only by Guard; targets must stand within one character-width. Needs Galder Thrower Lv 10 |
| | Evolution / Beast Claw / Fatal Wound / Sumo Suit (135) | The pure-Cat line — **excluded from the Diva hybrid** (who learns Sumo Suit only at TM 185) |
| **Card Master** (Raccoon) | Card Strike (41) | Consumes **1 Empty Card** for ranged splash AoE: (AP + HV × 8) × m, master ×2.65 |
| | Super Hips (55) | Passive **critical-hit immunity** (needs Dodge Master Lv 10) — the boss-tank staple |
| | One Pair (120) / Metamorphosis / Wild Nail | The pure-Raccoon line — **excluded from the Duke hybrid** (Duke gets One Pair at TM 175) |

The same pages document the hybrid +50 TM rule in practice: every skill above carries a second (higher) TM number for the hybrid class — Duelist learns the Boxer line at +50, Duke the Card Master line, and so on.

## Monsters use the same skills

Monster skill tables reuse player skills by level — e.g. boss Tombeth (Lv 121) casts Power Blow 4, Final Blow 4, Super Hips, Sturdy Shield 6, Mana Reflector, Magic Meltdown, Cure 6, and Enhanced Resistance; the 2011 Chaos Tower monsters added Guard / Buff Canceller / Deadly Poison / Blood Drain (see [Chaos Tower](28-chaos-tower.md)). Debuff skills that players skip are frequently **learned by Guardians** for bossing instead.

## Related systems

- [Stats & base leveling](02-stats-and-base-leveling.md)
- [Job advancement](04-job-advancement.md) (new skill trees per job)
- [Drilling](05-drilling.md) (TM EXP source)
- [Card Battle](06-card-battle.md) (EXP source)

## Sources

- [Trickster Online — Wikipedia](https://en.wikipedia.org/wiki/Trickster_Online)
- [How to Raise Your TM Level in Trickster Online — HT Games](https://www.htfbw.com/Internet-Games/Online-Games/2825.shtml)
- [Card Master Skills — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Card_Master_Skills.html) (skill types, mastery items, formulas, prerequisites)
- [Beginner's Guide — PandaTO Wiki](https://pandato.fandom.com/wiki/Beginner%27s_Guide) (skill NPCs, C/S windows, quickslots)
- [Cyber Hunter — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Cyber_Hunter.html) (hybrid +50 TM rule)
- [트릭스터(게임)/스킬 — 나무위키](https://namu.wiki/w/%ED%8A%B8%EB%A6%AD%EC%8A%A4%ED%84%B0(%EA%B2%8C%EC%9E%84)/%EC%8A%A4%ED%82%AC) (0th/1st/2nd tier structure, Power and Boxer skill tables, guardian debuff meta)
- [Tombeth — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Tombeth.html) (monster skill levels)
- [매력형 고양이, 너구리 스킬 트리 — cyan's Trickster blog](https://livehepa.blogspot.com/2020/10/trickster-charm-type-cat-raccoon-skill.html) (Charm 0th-tier formulas, type graphs)
- [마법형 양, 용 스킬 트리 — cyan's Trickster blog](https://livehepa.blogspot.com/2020/10/trickster-magic-type-sheep-dragon-skill.html) (Magic graph, MA/LK scaling, element rules)
- [감각형 여우, 사자 스킬 트리 — cyan's Trickster blog](https://livehepa.blogspot.com/2020/10/trickster-sense-type-fox-lion-skill.html) (Sense 0th-tier kit, gun formula, DA/AC builds, element meta)
- [Sense Skills — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Sense_Skills.html) (Stone Shower, Invincible Drill, Gun Carrier specifics)
- [Bard / Magician / Explorer / Inventor / Entertainer / Card Master Skills — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Bard_Skills.html) (2nd-tier skill tables, formulas, mastery cards, hybrid exclusions; per-class pages at `Magician_Skills`, `Explorer_Skills`, `Inventor_Skills`, `Entertainer_Skills`, `Card_Master_Skills`)
- [Engineer — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Lion.html) (the complete 16-skill shared Sense 0th tier)
