# Guild System (incl. GvG)

## Overview

Guilds are player communities with privileges: a shared identity, weekly **ranking EXP bonuses**, and the **Guild versus Guild (GvG)** colosseum battles. Guild administration happens at the **Megalopolis Guild Office**.

## Creating and joining

- **Create:** level 35+, **2,000,000 galders**, talk to **Andrew** at the Megalopolis Guild Office → "create a new guild," then name it.

**The guild rulebook (client `GuildUIParams` / `GuildSetupInfo` / error tables):**

- **Membership:** guild cap **64 members**; join applications require Lv 35+; **one guild-master character per account**; withdrawal locks you from joining another guild for **1 week**; dissolution blocks creating a new guild for **1 month** (with a dated expiry shown).
- **Grades and activity points:** members are graded, each grade's **activity-point threshold is configurable 0–10** (strictly increasing by grade; grade 7 is fixed) — and the points are **sourced from memo counts and login counts**. The **guild master password** system defaults to "0000" (16-char max).
- **Guild level curve (`GuildLevelInfo`):** 950 / 2,000 / 4,100 / 8,300 / 12,500 / 24,850 / 37,250 / 50,350 / 76,000 / 99,650 points for levels 1–10 — points accrue **live** from logins, GvG, and quest completion, and the **weekly rank pays a percentage EXP bonus** ("%s guild ranks %d this week — %d% bonus EXP applied").
- **GvG conduct:** **spectating costs 1,000 galders**; a no-show opponent is an **automatic win**; the **out-count must exceed participant count**; room creation requires **officer rank**, and official-match participation is **guild-master-only**; timeout awards the **higher score**; a full retreat is a **forfeit loss**; players already in or watching another match can't be invited; and the **league system** has schedule windows with **playoff-qualified guilds barred from creating casual games**.
- **Emblems:** template changes are limited to **once per day**, permission-gated, and purchased through the guild shop; **guild-depot storage** is location-gated, item-type-restricted, and expandable by purchase.

  **Guild infrastructure (client data):** the guild **warehouse (길드창고)** is zone-restricted — the depot's own error messages include "길드 창고 이용이 불가능한 지역입니다" ("this zone does not allow guild-warehouse access") and data-request states; **guild emblems** run on **10 templates × 16 colors** (`GuildEmblemTemplateInfo`/`GuildEmblemColorInfo`) — the emblem designer's palette system, purchasable through the guild shop above.
- **Join (two ways):**
  1. Talk to **Guild Clerk Esther** at the Guild Office, browse the guild list, and apply (leader approves).
  2. Right-click any guild member → **Guild Information** → Join.

## Guild ranking system

Guilds earn score through activity; rankings **reset every Monday at 00:01** (ties broken by which guild reached the score first). Members of ranked guilds earn bonus EXP from monster kills:

| Weekly rank | EXP bonus |
| --- | --- |
| 1st | +20% |
| 2nd | +10% |
| 3rd–10th | +5% |

Check weekly and current rankings with **Guild Clerk Esther → Guild Weekly Ranking**. (This bonus guild-ranking system is documented from the Thai official service; revival servers implement equivalents.)

## GvG — Guild Battles

Guild Colosseum battles are large-scale PvP (see also [PvP](19-pvp.md)):

- Entry: talk to **Guard Gilbert**, pay **50 galders**; level 2+ required. Spectators can enter the Colosseum too.
- A **guild master (or equal authority) must be present** on the battle map, with a **minimum of 5 guild members**.
- **Cumulative level caps (client data):** `GuildGameLimitLvInfo` sets four total-level brackets per battle — with 3 members the team-level caps run **300 / 600 / 900 / 1200**; with 5 members **500 / 1000 / 1500 / 2000**; with 8 **800 / 1600 / 2400 / 3200**; with 10 **1000 / 2000 / 3000 / 4000** — GvG modes were tiered by the team's combined levels, matching teams against content their level-sum could face.

**The full GvG mode and arena system (client `GuildGameTypeInfo`):**

- **Team Match (팀 매치)** — first guild to the configured out-count (or highest out-score) wins; **outed members auto-respawn after a timer**.
- **Team Death Match (팀 데쓰 매치)** — first guild to out the *entire* opposing roster wins; a KO'd player **automatically switches to spectate**.
- **Monster Match (몬스터 매치)** — race to a target score by **hunting monsters**; fighting the opposing guild is allowed alongside, KOs respawn after a time — fought on a modified **Flame arena with a platform for selecting boss monsters**.

**Six named arenas**, each with the client's own tactical blurb: **Natural Cave** (wide corridors — encirclement viable), **Phantom School** (small and frantic — "a map where you can hear the haunted school's wails"), **Flame** (open volcanic field), **Nora's** (the cramped sewer maze — "treat the narrow passages as cover"), **Soccer** (built to commemorate the World Cup — a full pitch to sprint across), and **Grudge (원수)** ("enemies meet on a narrow bridge" — the single-log bridge map for choke-point tactics).

**Rewards and the guild shop (client data):** `GuildGameRewardInfo` pays **score-threshold item rewards** (1,100 / 1,300 / 1,500 score → items 7100/7102/7101), `GuildGamePresentInfo` lists 15 present entries, and the **guild shop** (`GuildShopGoodsTable`) sells guild infrastructure for points: **member expansion (1,000), guild warehouse (1,500), warehouse expansion (1,500), emblem (500), emblem package (1,000)** — GvG score converts into guild capacity. `GuildRankBonusExp` (10 rows) and `GuildLevelInfo` (11 levels) drive the weekly ranking EXP bonuses.
- Victory awards a **GB point**; guilds are ranked by points; **1,000 galders** transfer from the losing guild to the winner.
- **Space** shows the current war situation during battle.

**Battle modes:**

| Mode | Rules |
| --- | --- |
| **Team Match** | Two guilds accumulate KOs; defeated sides respawn |
| **Team Death Match** | KO'd players are permanently removed; last side standing wins (eliminated players may observe) |
| **Boss Battle** | Fight boss-class monsters (mirroring real bosses); scored on kill speed; 5 boss types spawn in level order (Tutankhamen G first, Spicy Dragon last); **Recall Tiles** let a guild member spawn a chosen boss (stand 5 s); each boss scores differently |
| **Level Battle** | Level-restricted battles; no GB points awarded |

**Battle maps:** School Coliseum, Cave Coliseum, Volcano Coliseum, Nora Sewers Coliseum, Boss Battle Coliseum, Oriental Coliseum.

**The lobby and its robot (client dialog):** the guild-battle lobby is staffed by **GB-01**, a beeping robot ("반갑습니다. 삐리~ … 삐리리릿~") that opens **three separate registration lobbies** — **guild battle** (`GuildGame_ShowLobby`), **level battle** (`LevelGame_ShowLobby`), and **guild-battle events** (`EventGame_ShowLobby`) — plus a plain-language rules briefing. The level-battle brackets are fixed in `LevelGameInfo`: **Lv 0–99 / 100–149 / 150–199 / 200+** — four score-separated war divisions behind the mode's no-GB-points rule above.

## Guild events

Ntreev USA ran **Guild vs. Guild tournaments** (e.g. Dec 16, 2009 – Jan 13, 2010) monitored in four categories — Most Active Guild, Most New Members, Most Guild Battle Wins, Most Completed Quests — with a **Dragon Helmet** (bonus-stat item) for winning guild members.

## Related systems

- [Party system](17-party-system.md)
- [PvP](19-pvp.md)
- [Events](30-events.md)

## Sources

- [Guild guide — Guwnteen blog (Thai)](http://guwnteen.blogspot.com/2011/06/tricksterguild.html) (creation, joining, ranking bonuses)
- [GvG — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/GvG.html)
- [Trickster Online Revolution GvG tournament — GamesIndustry.biz (Dec 2009)](https://www.gamesindustry.biz/trickster-online-revolution-guild-vs-guild-tournament-begins-today-christmas-event-launches-tomorrow)
- [Guild Clerk Esther's Quests — Trickster Online Tips blog](http://tricksteronlinetips.blogspot.com/2009/06/trickster-online-guild-clerk-esthers.html)
