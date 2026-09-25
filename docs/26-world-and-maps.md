# World & Maps

## Overview

Trickster Online takes place on **Caballa Island** (Korean: 까발라섬), a Pacific island bought and stage-built by the late Don Cavalier for his final contest, with the beginner area on neighboring Coral Island. The world is organized into **regions**, each containing a town, gate, numbered **fields**, **dungeons**, and **mines**. Megalopolis is the capital and service hub.

## Regions

| Region | Town | Notes |
| --- | --- | --- |
| **Coral Beach** (Korean: 코라비치) | Coral Town - Blooming Cora | Starter island area, Lv 1–15 monsters; Coral Dungeon connects toward Desert Beach |
| **Desert Beach** | Beach Town - Paradise ("Paradise of Beginners") | Beginner hub; **Pyramid Dungeon** (7 halls + Tutankhamen's Trials); Crystal Copper Mine; Sand Alert Fiesta zone |
| **Megalopolis** | Megalopolis (capital) | Square, Shop, **Bank**, Monster Guild, **Guild Office**, Skill Shrine / **Garden of Skill Master** (job rooms, guardian rooms, tribulation rooms), four forests, **Poppuri Dungeon** (trials, Mysterious Space, Black Market), Closed Amusement Park/Megalo Land, Rose Garden secrets |
| **Caballa Relics** | Relics Town - Azteca | Ancient-sunken-civilization ruins; 4+ Relics Dungeons; Job Masters; drilling heartland |
| **Oops Wharf** | Oops Wharf | Wharf region; **Phantom School** dungeon (PvP skirmish access via Shaman Girl Jia; classroom/annex GPS quests; the hidden **Mad Ray laboratory** behind a 2F-bathroom rift; revamped late-era into straight-line progression) |
| **Mermaid Palace** | Aquarius | Undersea mermaid home; Mermaid Palace fields/dungeon |
| **Ghost Blue** | Ghost Blue Seabed Town - Aquarius | "Devil's Zone" ship graveyard, Lv 95–110; **Nora Sewer** dungeon |
| **Rose Garden** | Event Garden - Ceremonia | Event hub (Colosseum waiting room, O/X quiz, Kyu wedding registry); Rose fields/maze; Withered/Secret Rose Gardens; Vamp Castle sits beyond |
| **Black Swamp** | Swamp Town - Carbigal | Swamp fields, Swamp Dungeon (Tenter Lion), Jade Steel mine |
| **Snow Hill** | Snow Hill Town - Laplanoel | Snow region (Pola's polar bears, per her lore); Blue Ice Dungeon; Snow Hill mine (Harkon); shopping mall |
| **Techichi Volcano** | Techichi Town - Neil's Camp | Volcano region; Harkon drilling fields; **Black Ash Dungeon** (검은재 화산 던전 — Woman Who Lost Her Child, Burning Kili, Nameless Warrior, Lion's Envoy; NPCs Shaman Girl Jia, Tango, Al Hauri) |
| **Tapasco Volcano** | Gate of Tapasco Volcano | Volcano endgame region; Spicy Island boss; Silent Lava mine; the late-Korean **Theme Spa (테마탕)** hot-spring theme park with its own skin-gacha |
| **Mirage Island** | Alteo City | Mirage fields; the **Trickster Cathedral** (Soul Seed/awakening quest hub); gacha-adjacent treasure content |
| **Alteo Empire** | — | High-level empire region (quest tables Lv 220–279) |
| **Abyss** | Abyss Town - Platonia | Endgame region (Lv 300+ content); Vamp Castle; the community documents an unfinished **shipwreck dungeon** |
| **Underground Dev Room** | — (entrance via Megalopolis Square statue; Dev. Room Card Key 156,000 g) | Developer-themed dungeon region |
| **Tartarus** | — | Korean endgame cage-dungeon (B1–B4): Koius / Chronos / True Chronos, Soul Weapons, equipment stat penalties inside (see [Korean version systems](33-korean-version-systems.md)) |
| **Tower of Chaos** | — | The 72-floor tower (see [Chaos Tower](28-chaos-tower.md)) |
| **Lovers' Maze** | — | Wedding-material hunting ground (Loving Torobbie) |
| **Janus's Secret Hideaway** | — | Secret Space area for the Guardian chain |

### Korean naming notes

Korean guides call the island **까발라섬** (Caballa Island), Coral Beach **코라비치** (Cora Beach), Phantom School **환영학원**, and Techichi's dungeon **검은재 화산** (Black Ash Volcano). The community also documents an **Abyss shipwreck** dungeon that was never fully implemented.

**Classic region progression** (per the Korean community): Coral Beach → Desert Beach → Poppuri Dungeon → Caballa Relics → Oops Wharf → Mermaid Palace (dungeon) → Mirage Island → Ghost Blue → Rose Garden → Vamp Castle (dungeon) → Black Swamp → Snow Hill → Techichi Volcano → Tapasco Volcano → Abyss. Drilling depth climbs along it — Desert Beach fields are ~10 m (hold-click works), Poppuri 20–30 m, and by Oops Wharf the grass-gathering quests jump to 10×25 = 250 items.
The community quest-band mapping runs Coral Beach 1–19, Desert Beach 20–39, Megalopolis 40–59, Caballa Relics 60–79, Oops Wharf 80–99, Phantom School 100–119, Mermaid Palace 120–139, Mirage Island 140–159, Ghost Blue 160–179, and Rose Garden 180–199, with the late regions (Alteo Empire, Techichi, Tapasco, Abyss) covering the 200+ bands (per the community quest-by-location tables).

## Map anatomy

- **Gates** link regions; **fields** are numbered per region (Beach Field 1–7...); **dungeons** are themed multi-floor instances; **mines** hold refine ores; special rooms (trials, guardian rooms, coliseums) hang off towns. Each region also hides a **Black Market**, reachable only with Weird Treasure Maps (see [Economy](31-economy-bank-trade.md)).
- The **World Map** function is a listed in-game system for navigation.

## Teleportation

**Client data:** `TeleportAdvInfo` enumerates the region-gate teleport menu — **31 zone destinations** (Desert Beach gate, Ghost Blue gate, Caballa Relics gate, …) — and `TreasureMap_Item` defines **67 treasure maps, each naming 5 candidate dig spots** (`SpotMap0–4`) plus time limits: the treasure-hunt layer of [Drilling](05-drilling.md) in raw form.

- **Kochi & Pachi** (Megalopolis Square) sell region teleports for 300–5,000 galders by destination (e.g. Gate of Desert Beach 300 g; Gate of Techichi 5,000 g).
- **Wing Ports** from Item Girl: single-region scrolls (e.g. Wing Port (Paradise) 1,000 g Lv 15; Wing Port (Caballa Relics) 3,000 g Lv 45).
- **Portable Ports (PP/PPAD)**: consumable teleports to gates and towns; the advanced **Portable Port AD** covers nearly the whole island.

## Related systems

- [Quests](25-quests.md), [Bosses](27-bosses.md), [Drilling](05-drilling.md) (mines)
- [Korean version systems](33-korean-version-systems.md)

## Sources

- [Trickster Online Maps — InspireMari](https://inspiremari.nl/trickster-online-maps/)
- [Main Page (zones list) — Trickster Online Miraheze wiki](https://tricksteronline.miraheze.org/wiki/Main_Page)
- [Desert Beach — T.R.I.C.K.S.T.E.R. Wiki](https://tricksterstory.fandom.com/wiki/Desert_Beach)
- [Megalopolis Bank (Megalopolis tree) — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Megalopolis_Bank.html)
- [Megalopolis Square (teleports, Dev Room) — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Megalopolis_Square.html)
- [Paradise Shop (region tree) — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Paradise_Shop.html)
- [Merchant Lorena — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Merchant_Lorena.html)
- [Trickster Online — Wikipedia](https://en.wikipedia.org/wiki/Trickster_Online)
- [트릭스터 던전 지도 — cyan's Trickster blog](https://livehepa.blogspot.com/2025/05/trickster-dungeon-map.html) (dungeon/monster/NPC tables incl. Black Ash, Theme Spa)
- [트릭스터(게임) — 나무위키](https://namu.wiki/w/%ED%8A%B8%EB%A6%AD%EC%8A%A4%ED%84%B0(%EA%B2%8C%EC%9E%84)) (regions index)
- [트릭스터 공략글 정리 — cyan's Trickster blog](https://livehepa.blogspot.com/p/trickster-online.html) (Abyss shipwreck, cathedral, specialties)
