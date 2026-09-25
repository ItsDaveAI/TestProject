# Job Advancement

## Overview

Every character advances through three jobs. The 1st job is the starting sprite; the **2nd job** (base Lv 60 / TM 50) branches male/female skill sets; the **3rd job** (base Lv 130 / TM 120) splits into a **pure** path (deepens the type's skillset) or a **hybrid** path (learns the counterpart 2nd job's skills at +50 TM requirement). The Dragon uniquely gets three 3rd-job options.

**The hybrid skill lists (client data):** the 25 `LimitSkillMaster_P/C/M/S_*` tables are the hybrid-limit rosters — the exact skill IDs each hybrid path may learn from its counterpart's tree (e.g. the Power tree's hybrid set runs skill IDs 1001–1011 plus 4702–4708), the client-side enforcement of the "hybrids learn the 2nd-job line, minus the pure-only exclusions" rule documented in [Skills](03-tm-leveling-and-skills.md).

> Korean guides number these differently: **1차 전직** (first advancement, Lv 60) and **2차 전직** (second advancement, Lv 130).

## Job tree (all 9 characters)

| Character | 1st Job | 2nd Job | 3rd Job (Pure) | 3rd Job (Hybrid) |
| --- | --- | --- | --- | --- |
| Bunny ♀ | Schoolgirl | Boxer | Champion | Duelist |
| Buffalo ♂ | Fighter | Warrior | Gladiator | Mercenary |
| Sheep ♀ | Librarian | Bard | Soul Master | Witch |
| Dragon ♂ | Shaman | Magician | Dark Lord / Priest | Wizard |
| Fox ♀ | Archaeologist | Explorer | Thief Master | Hunter Lord |
| Lion ♂ | Engineer | Inventor | Scientist | Cyber Hunter |
| Cat ♀ | Model | Entertainer | Primadonna | Diva |
| Raccoon ♂ | Teacher | Card Master | Gambler | Duke |
| Pola ♀ (Korean only) | Animal Lover | Trainer | Zoologist | — (no hybrid path) |

- Sheep's 2nd job (Bard) requires choosing **two of five elements** (Water, Electricity, Fire, Ground, Air), which permanently defines her skill tree.
- Dragon's pure options: **Priest** (Light: healing, support, holy DPS) or **Dark Lord** (dark burst DPS and debuffs). The **Wizard** hybrid learns Sheep's elemental spells.
- Examples: Champion (Bunny pure) builds AP with some MA/Fire attribute for Flaming Fist; Gladiator (Buffalo pure) prefers Earth/Water/Wind attribute. Fox pure builds DA with daggers; Fox hybrid builds for guns.
- **Pola** (Korean only) has **no hybrid path** — Animal Lover → Trainer → Zoologist — and her Bear-only skill tree is separate from the shared Power skills Bunny/Buffalo use.

## The advancement interface (client data)

The client's own job-change window (`ChangeJobStrings`) describes every job and its branches — confirming the table above and adding several rules:

- Every hybrid is described the same way: it **"learns the counterpart job's skills,"** letting you "build your own character through the broad combination of two jobs' techniques."
- The **Magician (Dragon)** entry alone lists **three** branch options — **Dark Lord, Priest, and Wizard** — the only three-way branch in the game.
- Two jobs are explicitly billed as **anti-hide counters**: **Gladiator** and **Professor** both carry skills "able to check Thief Master's hiding" — the wide-attack answer to a hidden Fox in PvP.
- **Zoologist** (Pola) is described as learning "hammer-weapon-specific skills with further strengthened attacks."
- Postponing is safe: **"even if you don't advance now, your advancement-quest progress is saved"** (`CJ_CANCEL_CONFIRM`).
- Advancing triggers a public announcement: **"[name] has advanced to [job] — everyone congratulate them"** (`CJNotice`).

## Second job advancement

**Requirements:** base level 60, TM level 50 (you can advance later with no penalty besides delayed skill access).

**Items:**
- 3× **100k Galder Check** — bought from Andrew in Relics Town - Azteca or Megalopolis Bank (105,000 galders each; 315,000 total).
- 1× **Growth Badge** — hunted from the monster **Kaboom** (Lv 80) in Caballa Relics Dungeon 4.

**Process:** deliver to your Job Master — found in Relics Town - Azteca, or Room of Job Master 1/2 in the Garden of Skill Master (portal on the east side of Megalopolis Square).

**Rewards:** 1,000,000 base EXP and 12,000,000 TM EXP, a class **"Sign"** accessory, new sprite art, and the ability to wear **capes**. Louis Bitton (Megalopolis Square fountain, Azteca, Carbigal) can revert you to the 1st-job look for 50,000 galders (and back again).

Known class Signs (each Job Master's one-time quest): Bunny — **Sign of Fighting Spirit** (Boxer Jeanne); Buffalo — **Sign of Sword** (Warrior Kei); Sheep — **Sign of Sound** (Bard La Fimmel); Fox — **Sign of Excavation** (Explorer Reina); Raccoon — **Sign of Card** (Card Master Taniel).

## Third job advancement

**Requirements:** base level 130, TM level 120. A "3rd Job Guide" book appears in your MyShop inventory when you reach level 120.

**Items** (obtained through the advancement quest chain):
- 1× **Guardian Stone** for your class (from your Job Master's trial — see the Korean locations below)
- 3× Glass Piece (Bone Warrior), 3× Magic Powder (Bone Magician), 3× Magnetite (Iron Knight), 3× Brass (Brass Knight)
- 1× Sacred Water (drilled in Black Swamp fields)
- 1× **Harkon** (drilled at Techichi Volcano / Tapasco Volcano fields, Chaos Tower battlefields, Gate of Abyss and Abyss fields, or via Blacksmith Marx's 5-cycle Snow Hill mine quest)
- 3× 1 Mil Galder Check (from Andrew at Megalopolis Bank)
- 1× Ticket of the Valiant (Clurican Lv 240 in 2nd Closed Lot of Jade Steel, Tenter Lion, or drilled in Swamp Dungeon)

Dark Lord candidates need everything **plus** 1× Adamantite and 2× Alexandrite but **no Harkon**; a 2nd-job Dark Dragon switching to Priest or Wizard does need a Harkon.

**Quest chain:** begins at the **Door of Tribulation / Door of Judgment** in the Garden of Skill Master (Path of Tribulation — Ticket of the Valiant + 3× 1 Mil Galder Check; 10,000,000 TM EXP), continuing through the 16 Rooms of Tribulation and class-specific trials.

**Rewards:** 22,848,875 base EXP and 48,848,875 TM EXP, a class accessory, a Light Compass, and 3× Flower of Revival.

### Korean-service details

- At the **Door of Judgment**, the left path is the **pure (발전형)** advancement and the right path the **hybrid**; the Dark Lord option is marked red.
- **Job Master locations** (each provides the class guardian stone):

| Character | Job Master | Location |
| --- | --- | --- |
| Bunny | Boxer Jeanne (권투선수 진) | Desert Beach Field 3 |
| Buffalo | Warrior Kei (전사 케이) | Oops Wharf Field 4 |
| Pola | Animal Trainer Mimi (동물조련사 미미) | Rose Garden Field 3 |
| Sheep | Bard La Fimmel (음유시인 라 휘멜) | Rose Garden Field 3 |
| Dragon | Magician Louis (마도사 루이) | Pyramid Dungeon 1 (Priest/Wizard); Mermaid Dungeon 2 (Dark Lord) |
| Fox | Treasure Hunter Reina (트레져헌터 레이나) | Caballa Relics Dungeon 1 |
| Lion | Inventor Gale (발명가 게일) | Oops Wharf Field 4 |
| Cat | Entertainer Elisha (연예인 엘리샤) | Rose Garden Field 3 |
| Raccoon | Card Master Taniel (카드마스터 타니엘) | Megalopolis forest path 3 |

- The **Dark Lord guardian stone** is special: after the Snow Hill steps, Blacksmith Marx in the Snow Hill mine points you to a hidden NPC inside **mine shaft 2** (through the wall) who wants **Janus's Mask** — dropped by the **Mongma** in Phantom School's annex (post-revamp, reached via Cowardly Guard Craven at the school entrance) — then 5× Titanium ore and 5× Gold-green stone (both drilled in mine shafts 1–2), rewarding the Light and Dark **Alexandrite**. Happy Stollon at Snow Hill's gate handles the intro quest.

## Notes

- Each job has its own **hair dye** state; MyShop Hair Dye items (e.g. 2,700 points) set a persistent color per job.
- On PandaTO, pure-path skills can additionally be learned by hybrids via the server's custom Rebirth/Avataring system (server-specific).

## Related systems

- [TM levels & skills](03-tm-leveling-and-skills.md)
- [Character types](01-character-types-and-creation.md)
- [Korean version systems](33-korean-version-systems.md)

## Sources

- [Second Job Advancement — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Second_Job_Advancement.html)
- [Third Job Advancement — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Third_Job_Advancement.html)
- [Cyber Hunter — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Cyber_Hunter.html) (complete job table, hybrid +50 TM)
- [3rd Job — PandaTO Wiki](https://pandato.fandom.com/wiki/3rd_Job) (pure/hybrid builds, Avatar Skills note)
- [Magic Type / Power Type / Sense Type — Miraheze wiki](https://tricksteronline.miraheze.org/wiki/Magic_Type)
- [전직/카드식별/영혼의 씨앗/각성 퀘스트 — cyan's Trickster blog](https://livehepa.blogspot.com/2020/11/trickster-job-change-card.html) (Job Masters, Dark Lord stone, Door of Judgment)
- [폴라 스킬 트리 — cyan's Trickster blog](https://livehepa.blogspot.com/2020/10/trickster-paulapolar-bear-skill-guide.html) (Pola's pure-only tree)
- Client data: `ChangeJobStrings` (per-job advancement UI descriptions, hybrid cross-learning, three-way Magician branch, saved quest progress, public announcement), `LimitSkillMaster_*` (hybrid skill rosters)
