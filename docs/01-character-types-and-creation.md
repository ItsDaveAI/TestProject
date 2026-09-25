# Character Types & Creation

## Overview

Trickster Online characters are divided into **4 types** differentiated by their primary statistics: **Power, Magic, Sense, and Charm**. Each type has a male and a female character (8 total in the international releases). A **9th character — Pola (폴라, "Paula"), a third Power-type polar-bear girl — was added to the Korean service in January 2013**, ten years into its run; she never reached the international versions before the 2014 shutdown (details in [Korean version systems](33-korean-version-systems.md)).

Each character is associated with an **animal and a profession**; the animal is reflected by a set of ears and a tail equipped by default on character creation (per Trickster M's developers, the cast is canonically human — the ears and tails are worn gear). Male and female characters of the same type have identical skills at first job; skills branch apart at the second job, and at the third job each character chooses a "pure" or "hybrid" path (see [Job Advancement](04-job-advancement.md)).

## The four types

| Type | Characters | Focus | Core stats |
| --- | --- | --- | --- |
| Power | **Buffalo** (♂ Fighter), **Bunny** (♀ Schoolgirl), **Pola** (♀ Animal Lover — Korean only) | Close-quarters melee, highest physical damage, high HP | AP, AC, DX (Pola additionally scales on DA) |
| Magic | **Dragon** (♂ Shaman), **Sheep** (♀ Librarian) | Ranged spell damage, largest MP pool, low physical defense | MA, MD (MP) |
| Sense | **Lion** (♂ Engineer), **Fox** (♀ Archaeologist) | Detection, drilling, item acquisition, ranged weapons (guns/knives) | DA, LK, AC |
| Charm | **Raccoon** (♂ Teacher), **Cat** (♀ Model) | Tank/evasion, survivability, dodge | HP, DP, HV |

## Character identities

**Korean-localization personal names** (Korean Wikipedia): Buffalo **닉키 (Nikki)**, Bunny **니아 (Nia)**, Sheep **미코 (Micco)**, Dragon **유혼**, Fox **베로니카 (Veronica)**, Lion **레오 (Leo)**, Raccoon **홀든 (Holden)**, Cat **제니 (Jenny)** — with Pola as 곰. The international releases used the same roster names where localized (Nikki, Nia, Micco…).

- **Bunny** — a lively high-school student and ace of her boxing club, bored with easy victories; came to Caballa Island for the treasure to buy the "world's most luxurious boxing gloves." Master of 1-on-1 combat with the highest single-target damage.
- **Buffalo** — an honest professional fighter cheated by gamblers who gave up his title; fights on Caballa Island to pay a rival's medical bills. Specializes in AoE attacks and is the best physical farmer.
- **Pola** (Korean only) — a polar-bear girl who boarded the wrong ship trying to reach Alaska, landed on Caballa Island, and became an adventurer after hearing polar bears live at Snow Hill. Fights with a **giant hammer and cannot equip shields**; her skills scale on **DA** and her base growth is Power 4 / Sense 3 / Charm 2. Pure-only job tree (no hybrid). See [Korean version systems](33-korean-version-systems.md).
- **Dragon** — the male Magic type; single-target specialist. His Magician advancement forces an **exclusive Light or Dark choice** (the other element's skills become unusable): Light brings defensive barrier skills for safe hunting (the Priest track), Dark hits harder at HP risk (the Dark Lord track). The Light Witch — the Sheep-hybrid route — is the most popular magic build precisely for the barrier.
- **Sheep** — the female Magic type; versatile elemental and healing spells. Her Bard advancement forces a permanent choice of **two of the five elements (Water, Electric, Fire, Earth, Wind) — only adjacent pairs on the element wheel** (Water pairs with Electric or Wind; Water+Fire is impossible). Meta pairs: Water+Electric (the ice-crystal/electric-strike combo, Soul Master favorite), Wind-based pairs (fastest farming — many just chain Wind Blade), Fire+Earth (the AoE pair for fast-spawn spots), Fire+Electric (AoE + multi-hit, the Witch favorite).
- **Fox** — an archaeologist with sharp intuition who came to study the mysterious island; ninja-like shuriken combat, best at drilling (DA focus).
- **Lion** — an eccentric high-school science obsessive who came for Don Giuvanni's weapon designs; uses guns/launchers, AC focus.
- **Cat** — a rising-star model with beauty-contest wins who came to fund lavish costumes for her movie; a **sword**-user built for defense, healing, and evasion on the front line.
- **Raccoon** — a student teacher from a family of teachers, on the island to bring home seven runaway students; a **sword**-user of high-risk, high-reward LK-driven skills (and notably good at compounding).

## Character creation notes

- The default animal ears and tail are equipped on creation (extra ears/tails are also sent via level-up system mail on some servers).
- Type choice fixes the character's stat growth pattern: e.g. Sense types are locked to maximum growth (a "4") in Sense, which is why Fox and Lion are the game's best drillers. Pola is the exception that proves the rule — a Power type whose kit leans on Sense.
- The starting character sprite corresponds to the 1st job (e.g. Schoolgirl, Librarian, Archaeologist, Model); sprites change with each job advancement, and can be reverted cosmetically via Louis Bitton's Fashion Job Change service (50,000 galders).
- **Weapon families:** swords (Buffalo, Cat, Raccoon), knives (Fox), canes (Dragon, Sheep), guns (Lion), and Pola's hammer — town shops stock each family by level bracket side by side (e.g. Lorena's Lv 65 row: Epoch Sword, Dirk, Wood Rod, Metal Gun).

**The creation screen itself (client `CharCreateUIParams`):** pick **type → clothes → hair color → name**, then distribute the **growth-target points** — the Build Graph pips. "Clothes" is the animal cast itself: the eight characters listed by animal (Bunny, Buffalo, Sheep, Dragon, Fox, Lion, Cat, Raccoon) plus **Bear (곰) as the 9th slot** — Pola's creation entry, client-confirmed. Each type's three stats are labeled on screen: Power — attack power / accuracy / agility; Magic — max MP / magic power / magic defense; Sense — weight / detection / luck; Charm — max HP / defense / evasion.

**Character conversion (client data):** the job-change UI carries a character-conversion dialog for the **Witch's Potion (마녀의 묘약)** — "change [character] into [character]." The client's warning is explicit: **dyed hair colors and every worn fashion item become unusable** (`ChangeJobStrings`, `CJ_CHANGE_CHAR`). A drastic remedy for character regret that costs your cosmetics — see [Job Advancement](04-job-advancement.md).

## Related systems

- [Stats & base leveling](02-stats-and-base-leveling.md)
- [Job advancement](04-job-advancement.md)
- [Korean version systems](33-korean-version-systems.md) (Pola)
- [Drilling](05-drilling.md) (why Sense is prized)

## Sources

- [Trickster Online — Wikipedia](https://en.wikipedia.org/wiki/Trickster_Online)
- [Power Type — Trickster Online Miraheze wiki](https://tricksteronline.miraheze.org/wiki/Power_Type)
- [Magic Type — Trickster Online Miraheze wiki](https://tricksteronline.miraheze.org/wiki/Magic_Type)
- [Sense Type — Trickster Online Miraheze wiki](https://tricksteronline.miraheze.org/wiki/Sense_Type)
- [마법형 양, 용 스킬 트리 — cyan's Trickster blog](https://livehepa.blogspot.com/2020/10/trickster-magic-type-sheep-dragon-skill.html) (element adjacency, light/dark exclusivity, meta pairs)
- [Charm Type — Trickster Online Miraheze wiki](https://tricksteronline.miraheze.org/wiki/Charm_Type) (Cat/Raccoon lore, swords)
- [Cyber Hunter (full job table) — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Cyber_Hunter.html)
- [Digging — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Digging.html)
- [트릭스터(게임) — 나무위키](https://namu.wiki/w/%ED%8A%B8%EB%A6%AD%EC%8A%A4%ED%84%B0(%EA%B2%8C%EC%9E%84)) (character roster incl. 곰/Bear)
- [트릭스터, 새 친구 '폴라'를 소개합니다 — 경향게임스 (2013-01-30)](https://www.khgames.co.kr/news/articleView.html?idxno=61730)
- [폴라(북극곰) 스킬 트리 정리 — cyan's Trickster blog](https://livehepa.blogspot.com/2020/10/trickster-paulapolar-bear-skill-guide.html)
- [트릭스터M 캐릭터 가이드 — Game Center](https://game.edu.kg/research/kobs/view-L2tvL2Jsb2cvZ2FtZS1ndWlkZXMvdHJpY2tzdGVyLW0vdHNtLWNoYXJhY3Rlci1qb2JzLWd1aWRlLWtvLmh0bWw) (ears/tail as worn gear)
- Client data: `CharCreateUIParams` (creation-screen flow, type/stat labels, Bear 9th slot), `ChangeJobStrings` (`CJ_CHANGE_CHAR` — Witch's Potion conversion warning)
