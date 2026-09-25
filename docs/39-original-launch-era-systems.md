# Original Launch-Era Systems (2002–2004)

## Overview

Before the patches that shaped the later game, launch-era Trickster ran on a different system design — documented in a **September 2002 developer preview interview** (경향게임스, pre-dating even the closed beta) and in namu.wiki's system-history sections. Several of these systems were patched away entirely, and others transmuted into the features the game is remembered for.

## The three original pillars (as pitched in 2002)

### Combat — the MAB system (Multi-Activity Battle System)
Combat was designed as more than weapon attacks: **items found in the game could be applied in combat in various ways**, including **casting magic from cards dug out of the ground** and **setting traps in the ground against monsters**. The island hosted 40+ monster species at launch scale.

### Cards — the TCC system (Trading Card Collection System)
The original card system went far beyond the [Card Battle](06-card-battle.md) that survived:

- **150+ kinds of cards hidden underground** across Caballa Island.
- Cards were used to **cast magic** or to **learn magic permanently** — the defining rule being that **casting magic required magic cards** (a launch-era signature that was removed through later patches, per namu.wiki).
- Cards could be **raised and combined** (카드 육성/조합).
- **Cards containing living creatures transformed the user** — and collecting/raising such cards let them **walk alongside you**, the conceptual ancestor of the pet system.
- In the island's **neutral zones**, collected cards were played in a trading-card game; the **card collection book (카드도감)** let players show off and curate their collections.

### Drilling — the ATD system (Active Time Drilling System)
The real-time drill minigame, implemented exactly as the pitch describes — the one original pillar that survived to the shutdown and became the game's signature (see [Drilling](05-drilling.md)).

## Other original-era concepts

- **Transform into monsters, raise monsters, own and decorate dungeons** — the "R2 MMORPG" pitch explicitly listed monster transformation, monster raising, and **dungeon ownership/decoration**; the last evidently transmuted into [MyCamp](21-mycamp.md) housing, and creature-transformation survived as event [Disguise Kits](22-myshop.md) and Card ID transformation frames.
- **Charm type's seduction abilities (유혹 능력)** — the original Charm concept included charm/seduction skills usable **both in combat and in card battle**.
- **Magic types excelled at magic and transformation** — the original Dragon/Sheep concept bundled shapeshifting with spellcasting.

## Patched-out history (namu.wiki's system-transition sections)

- The **magic-card casting requirement** was removed through repeated patches.
- The **skill system was reworked** (스킬 시스템 패치) into the TM skill-card system documented in [Skills](03-tm-leveling-and-skills.md).
- The **job advancement system itself was added via update** (전직 시스템 패치; Game Dong-Archive headlines record "'트릭스터', 전직 시스템 추가") — the launch game shipped **without** the modern job tree, which later became the 1st→2nd→3rd job structure in [Job Advancement](04-job-advancement.md).
- **Region patches** reshaped the map and monster layout mid-service.

## The community's critique (namu.wiki's "problems" chapters)

The Korean wiki's most-cited complaints, each corroborated elsewhere in this documentation:

- **Event-item controversies** (이벤트 아이템 논란) — event gear sliding into MyShop-tier power; the era verdict in English guides was blunter: "PvP/GvG = 99% MyShop players only."
- **Homogenized builds** (획일화된 캐릭터 육성) — the all-points-into-one-stat convention ([Stats](02-stats-and-base-leveling.md)) left each class with one "correct" build.
- **Party-share design** (파티 플레이 문제) and **drop rates & quest repetition** (드롭율/퀘스트 문제) — the 5×-cycle quest grind and gathering walls (250 grass by Oops Wharf).
- **Chaos Tower** (혼돈의 탑) complaints after the overhaul.
- **The Driller Boy "macro pet"** (매크로 펫, 드릴군) — AFK auto-drilling sold as a paid pet ([Drilling](05-drilling.md)).
- **The Giovani server** (돈 주반니 서버) — the migrated classic-AD population's max-level density, quest-item price spikes, and the notorious new-player barrier.

## A survivor: the day/night cycle

Trickster runs an in-game **day/night cycle where 1 real hour = 24 in-game hours**, read by hovering the minimap clock. It gated content through the whole service — most famously **Ray (레이)**, the night-only NPC (7:30 PM–5:30 AM game time, roughly 10 real minutes per window) through whom [Phantom School](25-quests.md) is entered.

The client carries the cycle's full visual layer: `DailyColor` is a **690-row palette table giving every map value four tint colors — Noon, Evening, Night, and Dawn** — the data behind the world's gradual shade shifts, surviving from the launch era's day/night design into the final client.

## Related systems

- [Card Battle](06-card-battle.md), [Drilling](05-drilling.md), [Pets](12-pets.md), [MyCamp](21-mycamp.md) — the survivors of this era
- [Skills](03-tm-leveling-and-skills.md), [Job Advancement](04-job-advancement.md) — the patched-in successors

## Sources

- [[트릭스터] 전설 속 '고대 영웅'을 찾아서 — 경향게임스 (2002-09-03)](https://www.khgames.co.kr/news/articleView.html?idxno=) (MAB/TCC/ATD systems, magic cards, transformation, dungeon ownership, seduction, 40+ monsters, 150+ cards)
- [트릭스터(게임) — 나무위키](https://namu.wiki/w/%ED%8A%B8%EB%A6%AD%EC%8A%A4%ED%84%B0(%EA%B2%8C%EC%9E%84)) (magic-card removal, skill/job/region patch sections)
- ['트릭스터', 전직 시스템 추가 — 게임동아 archive](https://game.donga.com/) (job system added by update)
- [환영학원 퀘스트 공략 — cyan's Trickster blog](https://livehepa.blogspot.com/2020/12/trickster-phantom-school-quest.html) (day/night cycle, Ray's hours)
