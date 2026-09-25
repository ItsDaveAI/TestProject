# Quest System

## Overview

Questing is Trickster's other main progression track: quests award base EXP, TM EXP, galders, coupons, equipment, and unlock content. The community taxonomy (Our Trickster Online wiki) divides quests into the types below; every quest shows its NPC, location, base/TM experience, request, quest cycles (repeat count), and level conditions in the quest log.

## Quest types

| Type | Description |
| --- | --- |
| **Episode quests** | The 6-episode main story. Episode 0 begins in Blooming Cora (deliver the Registration Form to Bunny Maid); Episode 1 "Nefertiti's Necklace" starts at Gate of Caballa Relics (Monkey T, Lv 45+) and chains through Old Artist, Guide Sabrina, and more; later episodes span every region up to Episode 6. Chapter-based with large EXP rewards (~257k base / 121k TM per step at Episode 1). |

**Episode 0's full cast and flow (client dialog data — the tutorial episode as the client tells it):** the game participation paperwork *is* the tutorial. **Esther** (Npc94) — "I normally work at the Megalopolis Guild Office, but was dispatched here to help new participants fill out and file their game application" — sends you to fetch the **participation application from the Bunny Rabbits** ("a basic capability test — don't be fooled by the cute rabbits"), paying a **receipt (접수증)** to hold. **Dorothy** (Npc155) needs **fresh water and cold ice from the Blue Penguins** at Cora Field 3 "for the frail children," plus the **50-galder-coupon stamp paper (인지대)** — she grumbles if you balk: "you're not saying you won't buy the stamp because I upset you, are you?" **Frenchmaid** (Npc12) prints the certificate — after her personal errand: **one pair of Premium Socks from Tottochi** (plus a 10-galder coupon), because "I couldn't spare a pair and can never leave my desk." **Tinny** (Npc97) is the beach-volleyball player whose practice is interrupted by monsters (a timed monster-hunt quest with inline monster-image and count macros), and **Dean/Don Juvanni's chain** (Npc96/2/68) closes it: Juvanni's forced march, then **Robert** (Npc68) — "Megalo Company *secret agent* — shh, don't try to learn more about me… I'm not normally this kind, but I serve under Don Juvanni's special orders *only for beginners*" — gating stage advancement on Lv 15 ("come back after 15 more levels"). A photo-taking NPC (Npc312) collects "handsome adventurer" snapshots for her **mini-homepage** — an in-lore wink at the era's Cyworld culture. The quest scripting embeds inline **monster images, quest references, and reward macros** into the dialog itself (`@img`, `@ref`, `<MonImg/>`, `<Time/>`, `<Cnt/>`) — dialogs are the UI.
| **Key quests** | Region-unlock quests gated by collecting **stickers** (e.g. 10 Caballa Stickers from Relics NPCs → Fortune Teller → Julio) — "Key Quests (Access)". |
| **Monster quests** | Timed hunts from the regional **Monster Guilds**: Hunter Yuri's regional chains, then Assistant Hunter's timed missions (e.g. 10× Mandragora Lv 58 in 20 min, 5 cycles, Lv 50+). Rewards scale by level; galder coupons common. |
| **Card quests** | Card Girl's collect-monster-cards chains — a TM-oriented complement to [Card Battle](06-card-battle.md). |

  (Client registry: `MonsterQuestInfo` — 600 monster quests, each naming its client NPC and position, level band, and per-target source monster / count / time limit / level range — the timed-hunt template at scale.)
| **Normal / Story quests** | Everything else — NPC storylines, item fetches, compound/delivery chains (e.g. Officer Robert's Don's Push stages that teach refining). |
| **Party quests** | Officer Tera's regional dungeon PQs (Desert Beach, Poppuri, Caballa Relics, Oops Wharf, Mermaid Palace, Crystal Copper, Nora Sewer, Vamp Castle, Jade Steel, Blue Ice, Silver Jewel, Snow Field) — sources of [Chaos's Feathers](10-tempering.md). |
| **Daily quests** | Repeatable dailies (e.g. Star Gazer Stella's Megalopolis daily Lv 35; Shadow World dailies Lv 210; region summer dailies). |
| **Skill quests** | Quests that grant skills — Crazy Drilling (Driller Marky chain), [Card Identification](07-card-identification.md) (Fairy Nono), Mind's Eye (Eclipse). |
| **Escort quests** | An engine quest type (client `EscortNpcTalk`): zone-bound, character-type-specific **escort templates** with Start/Fail/Success dialogue — guarding an NPC through a map (shipped in limited use; the engine category exists). |
| **Event quests** | Limited-time chains during [events](30-events.md) (Poppuri quests, wedding quests, Tower of Chaos quests). |

**Scenario/Episode structure** (the level-ordered story spine):

**The starter quest spine (Desert Beach → Paradise → Relics):** Lv 15 at Gate of Desert Beach opens **Don Guivanni's** drilling quest (1 Empty Potion Bottle + 1 Oasis Water — the unlock for Beach Town Paradise's chains) and **Driller Marky's** 2× Tanning Oil dig (reward: the **penguin pet**, serviceable to Lv 25). Paradise adds **Strange Fisherman** (Lv 20; class-split: 5 Salt or 20 Ground Earthworm), the Bunny-only **Octopus Girl** (10 Red Lipstick), and **Card Girl's** first riddle appearances (her later riddles pay TM EXP and Arcana Cards — e.g. Mimic at Lv 45, Chibcha at Lv 55, Chimu at Lv 60). Gate of Caballa Relics chains onward with **Monkey T** (3× Gold Ring, 3× Gold Necklace, 3× Gold Plated Wheel — repeatable **25 times** for TM EXP + galder coupons) and **Wise Hen** (25 Hulled Millet across 5 cycles).

**The story frame:** billionaire game-company founder **Don Cavalier** dies and his will reveals a contest — whoever wins the "Trickster" game on **Caballa Island**, the stage he built in secret in the Pacific, inherits his entire fortune ("a story you've heard somewhere before," as the Korean wiki jokes). The 2002 pre-launch interview adds the lore spine: the **"trickster"** is the ancient hero and **messenger connecting the forgotten ancient world to the present** — the game-creator Don Cavalier mirroring that role as the bridge between reality and the buried ancient city-state — which is what the island's relics, episodes, and the "more than a treasure hunt" six-episode plot slowly unearth. The main story concluded with **Episode 6** (July 2011 update, OST by ESTi × Miya); only event content followed. Episode 6 wrapped the main *line*, but the Korean wiki keeps a standing **"unresolved threads" (미해결 떡밥)** list for it — and Trickster M's marketing leaned on exactly that, promising to complete "the ending the original never got to show" through serialized episode quests ([Trickster M](34-trickster-m.md)).

**Episode 6's dramatis personae (client `ScrollText_Cast_EP6`):** the finale's cast roll names the story's principals — **Don Cavalier, Don Juvanni, Don Danihen** (the three Megalo powers), **Rosalind Gracia, Nefertiti, Encladus, Fortina, Giska, Rosaspina** (the ancient-world line), **Love Hunter Robin, Robin van Peruoza, Assistant Hunter Poppuri** (the island's recurring faces) — the concluding episode's cast, straight from the client's credits. The companion `ScrollText_StaffList_EP6` (161 entries) preserves the finale's production credits — **Producer 최유다, Director 오인근** and the staff roll — the last team record from the story era.

**The story in the client's own words (Episode 0, Don Juvanni's dialog tree):** the game opens with Don Cavalier's *vice-president* seizing the frame — "돈 까발리에는 회사의 경영 현실과는 상관없이 제 마음대로 그 따위 유언을 했던 무책임한 회장이야. 그가 없는 지금 회사의 최고 실권자는 나다!" ("Don Cavalier made that ridiculous will of his regardless of the company's reality — an irresponsible chairman. With him gone, *I* am the company's true power holder!") — and, not yet even confirmed as chairman: "게임의 우승자는 내가 가린다" ("the game's winner will be chosen by me") — followed by his **forced march (강행군)** training quest for impatient beginners. The dialog trees carry branching codes (`S_Quest_Check`, `S_ActiveQuestID`, `S_CheckQuestState`, `S_Quest_Complete` with per-option jump targets) — quests *are* dialog state machines in the client.

**The Poseidon thread runs through the dialogs:** **53 NpcMsg files mention Poseidon (포세이돈)** and **109 mention the Megalo Company (메갈로컴퍼니)** — the ancient-guardian mythos isn't confined to the awakening quests; Alteo Empire NPCs bless you in his name: "저는 저주받은 운명에 언제까지나 끌려다니지 않고… 상냥한 모험가님에게 언제나 포세이돈의 축복이 함께하길…" ("I won't be dragged along by a cursed fate forever — may Poseidon's blessing always be with you, kind adventurer…").

| Stage | Level | Content |
| --- | --- | --- |
| Episode 0 | 1+ | Tutorial chain at Blooming Cora (Bunny Maid registration) |
| Scenario 1, Ch. 1 — Nefertiti's Necklace | 45 | 8-step Relics chain (~180k EXP / 85k TM per step) ending in the **Aquamarine Pendant 50** (AP 80, DX −1, DA +5, HV +5, 2 compound slots) |
| Ch. 2 — Unidentified Ancient Box | 50 | Indiana John's Oops Wharf piece-gathering (~232k / 264k per step; Light and Soil attribute stones) |
| Ch. 3 — The Harkon Seekers | 52 | From Tango at the Wharf gate; requires Ch. 2's document file (~254k / 300k per step); the Harkon necklace comes from Constone drops or double-clicked Harkon Relics |
| Episode 2 | 80+ | Mirage Island — the Necklace of Fate chain |
| Episode 3 | 130+ | Mirage Island — the Hero's Testament against a Lv 300 rock colossus (best banked and done in one pass); completion awards the **Dev Room Card Key** for the next story step |
| Episodes 4–6 | 200+ | The later regions, concluding with Episode 6 (July 2011), which wrapped the main story |

## Structure notes

**The scenario-quest engine (client data):** `ScenarioQuestInfo` (221 quests) is the story-quest registry — each entry carrying a quest name, **client NPC and position**, level band, EXP, and reward-table reference (e.g. *로잘린의 근심* "Rosalind's Worry," client Rosalind Gracia at Oops Wharf, level-banded with fixed EXP). `ScenarioQuestEpisode` (42 chapters) is the **episode arc registry** — the named chapters behind Episodes 0–6: *메갈로컴퍼니의 초대* (Megalo Company's Invitation), *모험의 시작* (The Beginning of Adventure), *우리들의 프롤로그* (Our Prologue), *돈 까발리에의 방* (Don Cavalier's Room), *돈 주반니의 강행군* (Don Juvanni's Forced March), *네페트리의 목걸이* → *네페트리, 그리고 엔키클라두스* (Nefertiti's Necklace → Nefertiti and Encladus), *정체불명의 고대 상자* (The Unidentified Ancient Box), *하르콘을 찾는 이들* (Those Who Seek Harkon), *복수의 칼* (Sword of Revenge) with *로잘린, 그리고 돈 다니헨* (Rosalind and Don Danihen), *수수께끼의 석관* (The Mysterious Sarcophagus), *기억의 노래 / 기억의 재생* (Song of Memory / Memory's Regeneration), *알테오 최후의 날* (The Last Day of Alteo), *영웅의 등장* (The Hero's Appearance), *개발실 괴담의 정체 / 게임개발일지* (The Dev Room Haunting / Game Dev Diary), plus **bonus chapters** (*분실된 설계도를 찾아라* Find the Lost Blueprints, *타우와 차강의 이야기* The Story of Tau and Chagang) — the main story's table of contents, preserved.

**Regional missions (client `MissionInfo` + `MissionMonster_*`):** a twelve-territory **mission system** — Blooming Cora, Desert Beach, Megalopolis, Caballa Relics, Oops Wharf, Ghost Blue, Event Garden, Rose Garden, Black Swamp, Snow Hill, Seabed, Volcano — each "령 미션" (territory mission) bound to its own `MissionMonster` table of regional targets: a repeatable regional hunt layer distinct from the episode and monster-guild quests.

**The memory puzzle (client `MemoryPuzzleParam` + 2 object tables):** a scripted **statue-order minigame** — five statues appear in sequence ("5개의 석상이 등장합니다. 석상의 등장 순서에 맞춰서 파괴해 주세요" — "five statues appear; destroy them in the order they appeared"), you're **locked from acting while they spawn**, **normal attacks only**, **60-second limit**, warping out on clear (portal map 656) — the Sphinx-style pattern test embedded in late-game content.

**The quest-reward schema (client data):** each `QuestResult_` row pays up to **4 item slots, galders, a granted Skill + SkillLevel** (skill quests in raw form), **10 message slots**, **up to 3 random-reward table references** (random rewards are first-class), and fixed **Exp + Tmxp**. The archive holds **4,464 reward rows across 2,075 quest tables**, plus 622 monster-quest and 80 party-quest result tables.

**The quest data layer (client):** quest content is table-driven at overwhelming scale — **2,074 `QuestResult_` reward tables**, **622 `MonsterQuestResult_`**, **80 `PMonQuestResult_` (party-quest)** results, plus `QuestDetail_Map_` (64) location bindings and the `NpcMsg_*` dialog trees (~500 files) that carry every NPC's branching conversation. Officer Tera's 30 party quests and the episode chains in this file are the surface of that dataset.

- Quests commonly require **drilled or compounded items** (e.g. Ginseng Tea is compounded at Paul's from Ginseng + Honey + Distilled Water), tying quests into [Drilling](05-drilling.md) and [Maturing Compound](09-maturing-compound.md).
- **Love Hunter** quests are a classic early TM-EXP farm (Yuri gives base EXP, Love Hunter gives TM EXP).
- Repeating quest chains ("cycles") — many quests repeat 5× for full rewards; a few repeat up to 25×.
- Episode/level coverage spans Lv 1–400 (quest-by-level tables on OTO run 1–19 through 340–400).
- The Korean service wove the systems into a level-ordered chain: **1st advancement (Lv 60) → Card Identification (Lv 65) → 2nd advancement (Lv 130) → Soul Seed (Lv 135) → Awakening (Lv 180) → Shadow World/Mind's Eye** — see [Guardians](13-guardians.md) and [Korean version systems](33-korean-version-systems.md).
- Korean quest-prep advice centers on **regional specialty items (지역별 특산물)**: stockpile 15 coins, 5× 50-galder coupons, and 2× 500-galder coupons everywhere; diamonds/rubies/sapphires from Rose Garden onward; open **Harkon Relics** near a shop (the gemstones they spill are heavy); the Mirage Island episodes hand out the **Dev Room Card Key** needed for the next story step.
- The **Phantom School** dungeon was revamped late-era into straight-line progression, moving the Mongma (Janus's Mask drop) behind the entrance guard — see [World & maps](26-world-and-maps.md).
- **Timed monster quests fed rankings** — the Japanese launch-era press describes monster-slaying quests ranked by shortest clear time and hunt count.
- **Mad Ray chain (Phantom School):** entered at night — the ghost **Ray** appears only between 7:30 PM and 5:30 AM game time ([day/night cycle](39-original-launch-era-systems.md): 1 real hour = 24 in-game hours) at Oops Wharf, Aquarius, or Ceremonia; bring a Neo Stone Drill No. 4 (the school ground is wood/stone, 80 m deep). Corridors are patrolled by unkillable one-shot **Wicked Keepers (Lv 400)** you must walk around. Jia's 30-minute blessing quest targets **Mad Ray (Lv 150)**; Momo's four-step chain (1F → 2F → 3F corridors → annex passage, teleporting you to random classrooms for GPS digs, ghost drops, and the music/art/science/machine rooms) assembles the **laboratory map** pieces and **Yin-energy crystals**, and the completed map opens the **rift** to the boss (it warps away if your opening burst fails). Rewards: **Phantom Repair Powder** (works like Repair Powder but stacks only with itself) and Ray's research journal. School quests are **once per day**; the Korean revival server Natural Trickster restored this chain's rewards.

## Related systems

- [World & maps](26-world-and-maps.md) — where quests live
- [TM leveling](03-tm-leveling-and-skills.md)
- [Job advancement](04-job-advancement.md) — quest-driven

## Sources

- [Episode Quests (quest-type taxonomy) — Our Trickster Online Wiki](https://oto.fandom.com/wiki/Episode_Quests)
- [Episode 1 Quests — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Episode_1_Quests.html)
- [Assistant Hunter — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Assistant_Hunter.html)
- [Caballa Relics walkthrough (key quests) — Trickster Online Tips blog](http://tricksteronlinetips.blogspot.com/)
- [Alan (party quest feather sources) — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Alan.html)
- [Beginner's Guide — PandaTO Wiki](https://pandato.fandom.com/wiki/Beginner%27s_Guide) (Love Hunter TM quest tip)
- [지역별 퀘스트 아이템/특산물 — cyan's Trickster blog](https://livehepa.blogspot.com/2022/02/trickster-online-specialties.html)
- [전직/카드식별/씨앗/각성 퀘스트 — cyan's Trickster blog](https://livehepa.blogspot.com/2020/11/trickster-job-change-card.html)
- [매드레이 공략 (1)(2)(3) — 네추럴트릭스터 blog](https://myashdd.blogspot.com/2020/07/1.html) (GPS hunts, Mad Ray chain, Phantom Repair Powder)
- [PCファーストインプレッション「トリックスター」 — Game Watch Japan (2005-02)](https://game.watch.impress.co.jp/docs/20050202/trick.htm) (ranked monster quests, thorough tutorial)
- [시나리오1 퀘스트 Chapter 1~3 — 류나곰's Naver blog](https://m.blog.naver.com/red_oasis/221343902366) (chapter steps, levels, rewards)
- [지역별 퀘스트 아이템 — cyan's Trickster blog](https://livehepa.blogspot.com/2020/11/trickster-online-quest-item.html) (episode 2/3 structure, Dev Room key)
- [Card Girl Quests — PandaTO Wiki](https://pandato.fandom.com/wiki/Card_Girl_Quests) (riddle chains, Monkey T, Wise Hen)
- [Trickster Online Tips — Happy Blogger](https://tricksteronlinetips.blogspot.com/) (starter quest spine, penguin pet)
