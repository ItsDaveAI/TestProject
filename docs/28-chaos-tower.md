# Chaos Tower (Tower of Chaos)

## Overview

The **Chaos Tower** (in-game: **Tower of Chaos**; Korean: 혼돈의 탑) is Caballa Island's premier progressive dungeon — "the single most difficult and challenging addition ever released" per its 2008 launch announcement. It debuted with **11 floors** requiring **level 160+** (April/May 2008, Trickster Online Revolution) and was rebuilt in the **September 28, 2011 Korean overhaul** into the full **72-floor** tower.

## Structure

- **A break room every 6th floor** — floors 1, 7, 13, 19, 25, 31, 37, 43, 49, 55, 61, 67.
- **A boss on every 12th floor** — floors 12, 24, 36, 48, 60, 72.
- Floors 1–12 through 61–72 are grouped in the wiki navigation; monsters climb into the Lv 240+ range by the mid floors (e.g. floor 36 hosts Corrupt Freyja Lv 247, Chaos Freyja Lv 249, Corrupt Cone Stone Lv 252).
- Boss floors host **Corrupt/Chaos pairs** of regional monsters, the level ladder climbing ~50 per 12 floors — 12F: Corrupt/Chaos Golden Mole (Lv 147/149) + Corrupt Kheperer (152); 24F: Corrupt/Chaos Naranjo (197/199) + Corrupt Freyr (202); 36F: Corrupt/Chaos Freyja (247/249) + Corrupt Cone Stone (252).
- Each 12th floor also holds a **Chaotic Space** — the dimensional gap — where Poirot's quests send you to kill a **Requiem Spirit** (Lv 297 at 24F) within 5 minutes for a Stage 2 Requiem Box and ~22.5M base / 4.2M TM EXP.
- Entry at the Tower of Chaos entrance (1st floor) via the Caballa Relics quest chain (Poirot - Make a Missing Ed Flyer → Get to the Bottom of the Rumours).
- The tower is **cyclical content** ("순환형 콘텐츠") — any character past first advancement can enter, with boss hunts and rare-item farming scaling upward.

## The 2011 Korean overhaul

The September 2011 update rebuilt the tower at enormous scale — **350 quests** (158 scenario + 192 normal), **180 monsters**, **187 items**, **10 NPCs** — as a staircase maze that grows more ruined toward the top, carrying the "find the lost brother" storyline:

- **New monster skills** (used by tower bosses, requiring party strategy):
  - **Guard (가드)** — nullifies a fixed number of hits regardless of damage; either stop attacking or chip with fast weak hits.
  - **Buff Canceller (버프캔슬러)** — strips every buff on the target and bursts damage — lethal even at full buffs.
  - **Deadly Poison (맹독)** — sustained damage-over-time.
  - **Blood Drain (흡혈)** — heals the monster for a share of damage dealt while active; stop attacking when it triggers.
- **New equipment families:** 5-star **Otherworld (이계)** set-ability gear — six sets from the Lv 110 **Spiritual Set** to the Lv 335 **Crimson Set** (진홍 셋트) — plus Lv 350 **Chaos (혼돈)** and **True Soul (진혼)** gear added progressively. Quest pets **Little Troy** and **Worm**.
- **Chaos Equipment Fusion (혼돈 장비 융합 시스템):** at the rest-floor NPC **Professor Komby (박사콤비)**, merge identical tower equipment (Chaos/Requiem/Altiverse families) into stronger copies — the tower's dedicated gear-growth system that produced some of the strongest equipment in the game. Full mechanics in [Forging](35-forging.md).
- **Honor titles (명예 타이틀):** how you complete scenario and monster quests determines which titles you earn — the title-collection meta lives on the MyView Honor tab.

## True Soul Space (진혼의 공간)

The December 20, 2012 Korean follow-up: a **7-floor other-dimensional dungeon** reached by defeating the **72nd-floor boss** and passing the **Gate of True Soul (진혼의 관문)** — new monsters, quests, and rare-item boss rewards beyond the tower's top. Detailed in [Korean version systems](33-korean-version-systems.md).

## Quests and NPCs inside

- **Poirot** — the tower's storyline anchor (missing "Ed" flyer, dimensional-gap investigations).
- **Wandering Warrior Tan** — mercenary contract tests: timed monster kills (e.g. 50× Mimic in 15 min), survey notebooks, stage proficiency tests, harsh training quests per floor.
- **Intern G** — Chaos Integer collection quests (e.g. Collect Chaos Integer.36Byte).
- Floor climbing runs on **survey notebooks**: each floor's hunting quest (winged Lv 107, platypus Lv 112, the Chaos potato Lv 117, the squirrel...) is exchanged at that floor's Don Giovanni for the next notebook, with curiosities like the **Mysterious Video Disc** unlocking floor 7 — and rest floors let you **register teleports** for future runs.
- **Fairy/assistant NPCs** in break rooms; Poirot teleports quest-qualified players to **Chaotic Space** floors (e.g. 36F Chaotic Space — the Dimensional Gap Investigation is once-per-lifetime, its *Reinvestigation* once per day).

## Titles

The tower introduced the **Title system**: a new "Title" tab in MyView (the **Honor** button) displaying earned titles. The full catalogue runs to **five families**:

- **Honor titles** — the tower's quest ladder: *Oddballs Friend* (understanding Wandering Photographer Ren's hobby), *Nice Adventurer* (getting Professor Komby to tell you his secret), *Mercenary Recruiter*, *Smarty Assistant*, *Committee Volunteer*, *G's Friend*, *2Bit / 4Bit Inventor* (Chaos Integer collection tiers), *Mercenary Trainee*, *Committee Slacker*, and onward up the tower.
- **Stella titles** — from [Star Gazing](16-star-gazing.md): the *The Gods* family and the *Experts* family, the latter earned through card combos (Three / Two Card Combo).
- **Set titles** — granted for collecting **whole equipment sets**: the boss sets (*Pharaoh, Guardian, Dread Pirate, Pirate, Sacrifice, Beast, Cold Hearted, Soki*), the 1st/2nd-job character sets, and others — the long-tail reward for set completionism.
- **Couple titles** — from the [Wedding](20-wedding-system.md) system.
- **Harkon titles** — from the [Harkon Protector](15-harkon-protector.md).

The client's `TitleInfo` table holds **148 titles** — and its first entries are the **fortune-title family** from [Star Gazing](16-star-gazing.md): *별희의 미움을 받은* ("Hated by Byeolhui"), *대흉의* ("of Great Misfortune"), and the planet-shining series (Mercury/Uranus/Neptune/Mars) — confirming the fortune readings as one of the largest single title sources.

**Honor titles, fully conditioned (client `HonorTitleInfo`, 73 titles):** every honor title is bound to its exact source quest with engine conditions — quest type/ID, **ClearCnt** (clear count), **Time**, and **HuntCnt** thresholds. The named examples in the families list above are the visible tip; `HonorTitleGrade` (11 rows) grades them into tiers. (The first entries match the wiki's tower ladder: *4차원 친구* for understanding Wandering Photographer Ren, *사람좋은 모험가* for earning Professor Komby's trust…)

**Boss debuff immunity (client `MonsterDebuffResist`):** bosses carry full **debuff-resistance profiles** — the Chaos-Tower-36-and-below boss profile resists **Stun / Paralysis / Stone / attack-skill-heal restriction at 100%**, and **MagicPoison / Poison / evade-restriction / AP / AC / DX / MA / DA / LK at 50%** — the engine behind why boss debuffing (the guardian meta) needs the right debuff, not just any.

**The set system behind Set titles (client data):** `CMSetItemParam` defines **320 equipment sets**, each binding up to **8 member items** — the job-clothing lines ("2차전직 토끼세트 2차" — 2nd-job Bunny set, "엔지니어 의류세트 1차" — Engineer 1st clothing set), beginner special sets, and the boss sets that pay the Set titles above. The camp-furnishing counterpart (`CampSetItemParamCM`, 74 sets) does the same for [MyCamp](21-mycamp.md) bundles.

**The tower's per-cycle infrastructure (client data):** the **`BossMon_Chaos1–7` families (76 tables, 79 spawn rows)** hold each cycle's per-floor boss spawns; **80 `NpcTalk_Chaos_*` dialog sets** voice the floor NPCs; **51 `R_MapItem_Chaos_*` placement tables** seed the floors' buried items; and each cycle runs its own **support shop** — `Shop_Chaos1–5`, NPC 5001, "here to support those investigating the Tower of Chaos," selling at the standard 0.5 rate from per-cycle `R_ShopItem_Chaos*` stock.

## Other notes

- **Harkon** (the 3rd-job item) can be drilled on the tower's Battlefield floors — one of its farmable sources.
- LifeTO's knowledge base notes the tower among endgame galder/equipment farms (gloom/phantom hunting routes).
- xTrickster built a custom "Lighthouse of Chaos" tower variant — server-specific content.
- The Korean launch event for the overhaul granted items for simply entering the tower, extra items per floor-boss kill, and skull-themed shield/hat/sword chances for first-advancement characters.

## Related systems

- [Quests](25-quests.md), [Job advancement](04-job-advancement.md) (Harkon), [Bosses](27-bosses.md)
- [Korean version systems](33-korean-version-systems.md)

## Sources

- [Trickster Online Revolution - The Chaos Tower is Here — IGN (Apr 2008)](https://www.ign.com/articles/2008/04/28/trickster-online-revolution-the-chaos-tower-is-here)
- [Trickster Online Revolution new content — GamesIndustry.biz (May 2008)](https://www.gamesindustry.biz/trickster-online-revolution-tricky-new-game-content-released-for-the-mmorpg)
- [Tower of Chaos's Quests — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Tower_of_Chaos%27s_Quests.html)
- [Tower of Chaos 36th Floor — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Tower_of_Chaos_36th_Floor)
- [Tower of Chaos 12th / 24th Floor — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Tower_of_Chaos_12th_Floor.html) (floor monster ladders)
- [Poirot - 24th Floor Dimensional Gap Investigation — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Poirot_-_24th_Floor_Dimensional_Gap_Investigation.html) (Requiem Spirit timed kill)
- [Third Job Advancement (Harkon sources) — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Third_Job_Advancement.html)
- [트릭스터, '혼돈의 탑'이 새로운 모습으로 돌아온다 — 디지털투데이 (2011-09-28)](https://www.digitaltoday.co.kr/news/articleView.html?idxno=21860)
- [혼돈의 탑 꼭대기엔… — 경향신문 (2011-10-10)](https://www.khan.co.kr/article/201109281518081)
- [신규 캐릭터 북극곰 소녀 최초 공개 (진혼의 공간) — 인벤 (2012-12-20)](https://www.inven.co.kr/webzine/news/?news=51549)
- [Titles — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Titles.html) (five title families, honor/set/stella examples)
- Client data: `BossMon_Chaos1–7` (per-floor boss spawns), `NpcTalk_Chaos_*` (80 floor-NPC dialog sets), `R_MapItem_Chaos_*` (51 buried-item tables), `Shop_Chaos1–5` / `R_ShopItem_Chaos*` (per-cycle support shops)
