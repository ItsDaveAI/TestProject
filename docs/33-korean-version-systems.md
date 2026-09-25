# Korean Version — Exclusive & Late-Era Systems

## Overview

The Korean service (2003.4 – 2014.1.28) was the original and longest-running version, and it received endgame content the international releases never saw. This file documents the Korean-exclusive and late-Korean systems, researched from Korean sources (namu.wiki, Inven/Khan/game press releases, and the Korean player-blog archives of cyan, Aeidein, 솔♡ and friends). Korean terminology is given alongside English names.

> Korean counting note: Korean guides call the Lv 60 job change **1차 전직** (first advancement) and the Lv 130 change **2차 전직** (second advancement) — i.e., English "2nd/3rd job."

## Korean service history (context)

- Developed by **Sonori** (손노리)'s online division, published by **Netmarble** as **Trickster AD**; the dev team spun off as **Ntreev** (엔트리브) in 2004. From **2007 Ntreev self-operated Trickster R alongside Netmarble's AD** — two live services of one game competing for the same players; AD still drew ~15,000 daily visitors and 1,000–1,500 concurrent (figures confirmed by Ntreev). When the contract expired and Netmarble refused to hand over the member DB, Ntreev announced **AD's end for September 12, 2008**, refunding paid items as Netmarble cash; TrickWorld ran a 10,000-signature campaign to save the characters, most AD players simply moved to R, and characters and items (cash items excepted — **Netmarble and GameTree's cash terms of service differed**, so paid items could not legally cross) were ultimately migrated — leaving the game consolidated as plain **Trickster** on Ntreev's own **GameTree** portal.
- Open beta (2004) peaked at ~30,000 concurrent users with 3M+ characters created. The Japanese version ultimately out-earned the Korean one. A 2007 **anime adaptation** (Sunwoo Entertainment — the veteran Korean studio whose OEM credits run from The Simpsons to Rugrats — starring cat character Jenny) was cancelled before airing. The main story concluded with **Episode 6** (July 2011 update, OST featuring composer ESTi and vocalist Miya).
- Korean servers: **Cavalier** (까발리에, ~600k characters) and **Giovani** (주반니, ~200k, migrated from classic Trickster AD — its aging population created a notorious new-player barrier).
- An official **480-page guidebook** (트릭스터 AD 공식 가이드북, Jan 2006) covered card battle, pets, drilling, growth compound, personal shops, refine, guild-battle monsters, and TM monster quests.
- A **Trickster comic (manhwa)** was serialized in the Korean comics magazine **Pang Pang (팡팡)** during the Netmarble era.
- Korean **revival servers** keep the game alive today (e.g. **Techichi Trickster**, plus the communities on arca.live's Trickster channel).

## Pola (폴라) — the 9th character

Announced December 20, 2012 (silhouette), revealed January 2–3, 2013, added late January 2013 — **ten years into Korean service**, and the game's final official character.

- **Concept:** a polar-bear girl ("북극곰 소녀") with white twin-tails, deceptively cute; developer quote: "a polar bear is a fierce predator despite its cute looks — we built that reversal into her."
- **Type:** Power (공격형), but unusual: her damage skills scale off **DA (감지력, Detect Ability)**, not just AP — her base growth graph is **Power 4 / Sense 3 / Charm 2**, and DA-focused equipment raises her damage more than AP equipment. Players build full AP / full DP / full HP on top of that.
- **Builds:** Power 4 / Sense 4 with all-AP is the recommended endgame graph; capital-light starts take the default graph or a Charm-4 graph first, switching later (all-DP early, all-AP after gearing up).
- **Weapon:** a giant **hammer**; she **cannot equip shields**, giving low raw defense (compensated by many defense skills and HP management; her skills also cost a lot of MP).
- **Lore:** she boarded the wrong ship trying to reach Alaska to see polar bears, landed on Caballa Island, heard polar bears live at Snow Hill, and became an adventurer.
- **Job tree (pure only, no hybrid):** 동물애호가 **Animal Lover** → 조련사 **Trainer** → 동물학자 **Zoologist**. Her job master is **Animal Trainer Mimi** (Rose Garden Field 3). Bear has her own skill tree — she **cannot learn the shared Power skills** that Bunny/Buffalo use.
- **Signature 0th-job skills** (from the Korean skill guide): a basic attack (AP ×150%), a 2-hit combo, an AP buff, **Concentration** (raises DA), **Mental Breakdown** (stun, up to 5 s mastered), **Shield of Will** (DP buff), and **Party Guard** (shields the whole party against a number of physical and gun attacks, but not magic).
- **Launch event (to Feb 27, 2013):** friend-invite SMS campaign (weapon exchange ticket), Pola 1st-advancement reward (shield skin + Pola's gift box), 3-day attendance + guild join (hat skin + gift box), full participation (pet exchange ticket), and island-wide **Blue Blue Penguin / Pink Pink Penguin** hunt monsters dropping useful items.

## Chaos Tower 2011 overhaul (혼돈의 탑 개편)

The September 28, 2011 Korean update rebuilt the tower (see [28-chaos-tower.md](28-chaos-tower.md)) at massive scale:

- **350 quests** (158 scenario + 192 normal), **180 monsters**, **187 items**, **10 NPCs**; the "find the lost brother" storyline through a staircase maze that grows more ruined toward the top.
- **New monster skill mechanics** — also used by monsters game-wide: **Guard** (nullifies a fixed number of attacks regardless of damage), **Buff Canceller** (strips all buffs and bursts damage), **Deadly Poison** (sustained DoT), **Blood Drain** (lifesteal while active — stop attacking when it appears).
- **New equipment families:** **이계 (Otherworld)** 5-star set gear — six sets from the Lv 110 Spiritual Set to the Lv 335 Crimson Set — plus Lv 350 **혼돈 (Chaos)** and **진혼 (True Soul)** gear added progressively; quest pets **Little Troy** and **Worm**.
- **Chaos Equipment Fusion (혼돈 장비 융합):** at the rest-floor NPC **Professor Komby (박사콤비)**, merge identical tower equipment into stronger copies — the tower's dedicated gear-growth system (full mechanics: [Forging](35-forging.md)).
- **Honor titles (명예 타이틀)** earned by how you complete scenario/monster quests — the title-collection meta.

## True Soul Space (진혼의 공간) & the Melting system (멜팅 시스템)

The December 20, 2012 Korean update (alongside Pola's announcement):

- **True Soul Space:** a 7-floor other-dimensional dungeon reached by defeating the **Chaos Tower 72nd-floor boss** and passing the **Gate of True Soul (진혼의 관문)** — new monsters, quests, and rare-item boss quests beyond the tower's top.
  The client data details its economy: `SourceInfo` defines **24 ranked Soul Sources**, each raising the **soul gauge** by a fixed amount and bound to a **specific guardian** (SourceName / SourceRank / SoulGaugeUp / GuardianID), while `SoulSystemInfo` sets the gauge's machinery — **SoulGaugeMax, SoulGaugeTime, and SoulGaugeDecrease** (the gauge drains over time; sources refill it), with a dedicated **soul potion** item. The True Soul Space was, mechanically, a **soul-fuel economy** for guardian content.
- **Melting system:** combine up to **5 surplus equipment** into a **Melting Box (멜팅 상자)** of grade 1–9, containing galder coupons, **Nate's Special Elixir (네이트의 특별한 비약)** and more. Equipment slots were expanded to 5, and Nate's elixir items expand the slots used to strengthen equipment. (This is the system the OurTrickster wiki lists as "Smelting"/"Expand Slot" web functions.) The client's `MeltingDropInfo` prices the melt by **item value brackets** — nine tiers, each at a flat **60,000-galder melt cost**, mapping the sacrificed equipment's value band (from 1,201–1,500 g up to 2,101–32,000 g) to its distinct drop item — the value-based salvage ladder behind the grade-1–9 boxes.

## Tartarus (탈타로스) — the Korean endgame dungeon

A cage-dungeon (B1–B4) whose entry quest chain begins at the **Tartarus Gate** — choose the **Cage of the Steel God** (B1/B2) or the **Cage of the Ancient God** (B3/B4, level 320+).

- **Equipment penalty inside:** B1/B2 −10%, B3 −50%, B4 −90% of your equipment's stats — only Tartarus-forged **Soul equipment** avoids the penalty.
- **Bosses and ancient-god monsters (고신류):** **Koius (코이오스, Lv 650)** in B2; in B3/B4 — Gazer 진 (618), Ancient Dragon (770), Sisyphus (770), Bijou Golem (760), Ixion (810), Hecate (850), **Tantalus (899)**, **Chronos (950)**, and the final **True Chronos (진 크로노스)**.
- **Gate questline:** King Poppuri (B3 Cage 1) runs an 8-gate qualification system — timed qualification hunts → **prison keys** → each gate's Poppuri boss kill → **certificates** registered at registrar machines; the four key materials combine into the 8th-gate key (Tantalus) → 9th gate (Chronos) → True Chronos. Warden **OkeA** offers the daily "Tartarus subjugation" (kill Koius in 20 min for a rare material). NPC **Robin van Peruoza** relocates by weekday.

  **Tartarus 2's secret cracks (client dialogs):** the deeper floors hide **one-way passages** — a "small crack barely one person wide, connecting somewhere else entirely," with the warning internal monologue on entry: "문득 이곳으로 다시 돌아올 수 없을지도 모른다는 생각이 머리를 스친다" ("suddenly it crosses your mind that you may never be able to return here") before the `Teleport_Start` commit. The same Npc425 dialog is instanced per floor (D10–D15+), each crack sending you to a different destination — the dungeon's hidden-floor network is a scripted one-way maze.
- **Soul Weapons (소울 웨폰):** Tartarus drops **Steel equipment (Lv 320)** and **Chrono equipment (Lv 380)** families — weapon/cane/gun/hammer/hat/shield/accessory (Steelblood, Steelbone Rod, Steelflash, Steelskuller, Steelamet, Steelshield, Steel Collector). Daily **Sky Anvil (하늘 모루)** guide quests collect Tartarus fragments, boss parts (rock fragments/wheel of fate from Sisyphus/Ixion, underground core from Gorgon, proliferating cells, light source from Gazer, black aura from Charybdis) plus **Koius's/Chronos's Souls 1–7** to upgrade them into **Soul equipment**, which can then be **soul-enhanced up to 11 stages**.
- **Absolute Uniques (절대 유니크) — the covenant tier:** alongside Soul equipment, Tartarus-era data adds the **Absolute Unique** class — the Shining Crystal trilogy and the Fallen Watcher's trilogy — with the harshest equip rules in the game: **duty-bound** (the item text demands you "perform the duty entrusted to the equipment" to keep using it), **permanently bound once equipped** (forced removal destroys it), **droppable from your corpse on death**, and **destroyed by disguising** — each at **20% drop probability**, with acquisition scaling to guaranteed at monster Lv 401+ ([Item Encyclopedia](41-item-encyclopedia.md)).

**Tartarus mechanics from the client data:** `TartarosMapSkillInfo` (97 rows) gives **each Tartarus floor its own debuff kit** — four debuff skill slots per map (e.g. the entry floors run skills 5051–5054 at level 1), so the dungeon pressures you differently room by room. `SoulEquipmentInfo` prices the Soul equipment's power: each use of its signature skills (5047–5050, per weapon family) **consumes 10 Soul** — soul as an ammunition resource, replenished via `SoulPotionInfo`. And `Slot_Extend_Item` is the slot-expansion item set (5 items) with **per-slot success ratios** (50% for the first slot, 10% for the second, declining onward) — the Melting-era equipment-slot gamble.

The client tables complete the crafting chain: `SoulEquipmentCraftInfo` (14 recipes) is the **Steel→Soul upgrade forge** (result, required counts, materials), and `SoulLevelIntensifyInfo` (20 stages) prices **every soul-intensify step** — per stage: the target soul level, weapon level, galder **Cost**, and material items with counts. `SoulSeedEventInfo` (55 rows) binds the Soul Seed quest chain's event gates (quest type/ID, level caps, special flags).
- **Soul Potions (소울 포션):** fuel for soul charging, crafting, and enhancement. Managed in **MyView → Guardian menu → Soul Management**: register a **Guardian's Source** item — **Unknown Ore** (+~25% gauge per 15 min), **Shadow Piece** (~60%), **Blue Jewel** (~75%), none (−10%) — the gauge fills even while logged out, and a full gauge produces Soul Potions (5 while logged in, 1 logged out). Sources come from Tiphmont Ktangkong's B4 quest box, spirit monsters, **Antares** exchanges (Shadow Piece = 3 Unknown Ore; Blue Jewel = 5 Shadow Pieces), and Blue Jewels drilled in Tartarus.

## Tapasco Theme Spa (타바스코 테마탕)

**The Spa's story cast (client dialogs):** **Warrior Kei** lurks in the Volcano Town — "내 이름은 전사 케이. 까발라 섬에서 더 이상 적수를 찾지 못해 이리저리 떠돌고 있지. 최강이라는 위치는 언제나 고독한 법인가..." ("My name is Warrior Kei. I wander Caballa Island finding no more rivals — the strongest position is always lonely") — the same Kei who serves as the Buffalo's Job Master ([Job advancement](04-job-advancement.md)), moonlighting in the hot springs. The **Lord of Time and Space** (Npc177) judges those who "protected Tapasco and Caballa Island" and offers to **send them back to the past — to when they first met the Spa** (the Theme Spa's replay/return mechanic in narrative form). And a Spa resident trades for the region's **spicy fragrance** ("알싸하고 화끈한 매운 향기가 그만이군… 같이 먹을래?" — "that tangy, fiery spicy scent is the best… shall we eat together?"), while Snow Hill's dwarf-fairies grumble that their once-peaceful village got noisy when it opened to the public.

A late-Korean hot-spring theme park at Tapasco Volcano (OurTrickster lists its spa as "under construction" — the area never reached the NA version):

- Entry via **Eliza Bath**, requiring **Theme Spa coupons** hunted from Funky Orcs (Tapasco Field 3); the key-quest chain weaves between Tapasco fields and the spa (Al Hauri's red/blue salamander leathers → exclusive bath towel; staff member Minyoung Seo's body-wash/towel quest; chief chef Chaochao's black-pepper quest).
- An in-park shop sells **Theme Spa gacha coupons** — a cheap skin-gacha machine (towel hat, washbasin hat, octopus hat, penguin hat; **Baby Coolem** pet is the chase prize).
- Full NPC cast: general manager Pengdori, cleaners Pingping/Moka, staff Mingminggu, Dr. Goofy, Ice man & woman, Miranda Watty and Mirabo Watty, mermaid baby, the mysterious beautician, pet trainer Shurin and **pet nursery Erin**, apprentice scrubber Kairin, Fabian, wanderer Ian, photographer Ren. Monsters include Magic Green/Yellow/Pink, Chesfill, Cobraro, Herbshell — and the infamous **illegal bath scrubbers** and **nuisance customers**.

## Other Korean/late-era content

- **Black Ash Dungeon (검은재 화산 던전)** — Techichi's volcano dungeon (Woman Who Lost Her Child, Burning Kili, Nameless Warrior, Lion's Envoy; NPCs Shaman Girl Jia, Tango, Al Hauri, Treasure Hunter Reina).
- **Phantom School revamp** — the school dungeon was reworked into a straight-line progression; post-revamp, Cowardly Guard Craven at the entrance teleports you to the **Mongma (몽마)** that drops Janus's Mask (needed for the Dark Lord guardian stone).
- **Trickster Cathedral (트릭스터 성전)** at Mirage Island Field 7 — the Soul Seed quest hub (Shining Egg → Nephtri → Eclipse).
- **Abyss shipwreck (심연 던전: 난파선)** — an unfinished/unimplemented area documented by the Korean community.
- **Regional specialty items (지역별 특산물)** — each region's signature drilled/quest items (Cora Beach cave goods, Desert Beach pyramid jars, Relics era artifacts, Snow Hill jewels) used across quest chains.

## Collaborations (Korean & Japanese)

- **Sanrio collaboration** (Korean): Hello Kitty and Cinnamoroll equipment.
- **Japanese Trickster collaborations** (Japan-only runs): **Shinryaku! Ika Musume (Squid Girl)** items, **Higurashi When They Cry** pet, **Moonlight Acid: Mina (월면토병기 미나)** items.

## Japanese service record (GCREST → Gamepot)

The Japanese service — the version that out-earned its home market — ran a distinct operational history: weekly Tuesday 10:00–16:00 maintenance (the *Trickster+* rebrand launch famously overran into a **26-hour maintenance**), **nProtect GameGuard** from August 22, 2006 with enforcement waves from June 2007 (monthly ban counts published), the **second-job launch of November 14, 2006** that immediately broke and required an emergency maintenance, an item-duplication monitoring sweep from July 21, 2009, and an unauthorized-access incident on August 7, 2009 met with account suspensions and IP restrictions. Registered IDs passed **1.2 million by April 2008**, and on **July 18, 2012** operation passed from GCREST to **Gamepot**, who ran it to the January 28, 2014 shutdown. The service's title itself kept rebranding — 素敵な出会い トリックスター → みみとしっぽの大冒険 トリックスター+ → トリックスター0 -ラブ- (2007) → みみとしっぽの大冒険 トリックスター (2010).

## Korean event calendar highlights (2010–2013)

From the Korean event archive: Valentine's/White Day "Fabian's crush" (2011), Chuseok food-recovery events with songpyeon-rabbit pets (2010–2012), 7th-anniversary musical "Snow White and the Seven Dwarfs" (2010), Tanabata three-part event (2010), Phantom School ghost stories (2010), Halloween pumpkin-village hunts (2010–2012), Summer Camp four-program series (2012), Children's Day (2010), 9th-anniversary parade (2012), Christmas solo-vs-couple events (2012), New Year snake events (2013), and "everyone's summer" (2013, baby Driller-kun pet). **GM culture:** GMs ran OX quizzes frequently, appeared in towns to hand out EXP buffs and chat, and the publisher held annual offline user meetings.

## Related systems

- [Character types](01-character-types-and-creation.md) (Pola)
- [Chaos Tower](28-chaos-tower.md), [Guardians](13-guardians.md), [World & maps](26-world-and-maps.md), [Events](30-events.md)

## Sources

- [트릭스터(게임) — 나무위키](https://namu.wiki/w/%ED%8A%B8%EB%A6%AD%EC%8A%A4%ED%84%B0(%EA%B2%8C%EC%9E%84)) (service history, systems index, character list)
- [트릭스터, 신규 캐릭터 북극곰 소녀 최초 공개 — 인벤 (2012-12-20)](https://www.inven.co.kr/webzine/news/?news=51549) (True Soul Space, Melting system)
- [트릭스터, 새 친구 '폴라'를 소개합니다 — 경향게임스 (2013-01-30)](https://www.khgames.co.kr/news/articleView.html?idxno=61730)
- [MMORPG 트릭스터, 10년 만에 새 캐릭터 등장 — 경향신문 (2013-01-03)](https://www.khan.co.kr/article/201301031718281)
- [트릭스터 新캐릭터 '폴라' — 게임메카](https://www.gamemeca.com/view.php?gid=253931)
- [트릭스터, '혼돈의 탑'이 새로운 모습으로 돌아온다 — 디지털투데이 (2011-09-28)](https://www.digitaltoday.co.kr/news/articleView.html?idxno=21860)
- [혼돈의 탑 꼭대기엔… — 경향신문 (2011-10-10)](https://www.khan.co.kr/article/201109281518081) (tower overhaul details, monster skills, gear families)
- [폴라(북극곰) 스킬 트리 정리 — cyan's Trickster blog](https://livehepa.blogspot.com/2020/10/trickster-paulapolar-bear-skill-guide.html)
- [탈타로스 소울 웨폰 가이드 — cyan's Trickster blog](https://livehepa.blogspot.com/2022/01/trickster-tartarus-soul-weapon-guide.html)
- [코이오스 / 진 크로노스 잡으러 가는 법 — cyan's Trickster blog](https://livehepa.blogspot.com/2022/01/tartarus-boss-quests.html)
- [트릭스터 던전 지도 — cyan's Trickster blog](https://livehepa.blogspot.com/2025/05/trickster-dungeon-map.html) (Theme Spa, Black Ash)
- [타바스코 화산 키퀘스트 — 네추럴트릭스터 blog](https://myashdd.blogspot.com/2020/03/4.html) (Theme Spa entry quests)
- [테마탕 diary — madein2019 blog](https://madein2019.blogspot.com/2019/04/1.html) (Theme Spa gacha, TechichiTO)
- [트릭스터 공략글/이벤트 정리 — cyan's Trickster blog](https://livehepa.blogspot.com/p/trickster-online.html) (collabs, event archive, specialties)
- [트릭스터 AD 공식 가이드북 — 예스24](https://www.yes24.com/Product/Goods/1394098) (TOC: systems, personal shop)
- [트릭스터AD, 넷마블 서비스 종료 발표 — 망상과공상 (2008-06-12)](https://gamelog.kr/205) (AD/R parallel-service war, DB standoff, traffic figures — the TrickWorld operator's firsthand account)
- [한 달 앞으로 다가온 트릭스터AD 서비스 종료 — 망상과공상 (2008-08-14)](https://gamelog.kr/239) (cash refunds, migration to R, signature campaign)
- [트릭스터(MMORPG) — 우만위키](https://www.ggemguide.com/guide_on_view.htm?uid=3934) (character-migration outcome, server demographics)
- [トリックスター (オンラインゲーム) — JP encyclopedia article](https://tsunezu.net/trickster/) (JP service history, maintenance record, rebrands)
- [TricksterWiki (JP community wiki)](https://trickster.wiki/) (shutdown schedule, Gamepot-era records)
