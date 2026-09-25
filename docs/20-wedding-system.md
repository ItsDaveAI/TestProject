# Wedding / Couple System

## Overview

The Wedding System launched **June 17, 2010** as a major Ntreev USA content update: two characters (Lv 30+, opposite genders) register as a **couple**, grow **Love Points** together, then complete wedding quests and hold a ceremony with rings, outfits, a hall, and invited guests. Marriage grants a **partner-teleport** ability and special ring abilities.

## Coupling and Love Points

1. Both characters (Lv 30+) go to the **Event Garden** and speak with **Kyu** to register as a couple.
2. Registered couples build **love stats** by playing together: partying (PQs/MQs), sending **memos** and **gifts** to each other, and spending time in a party. Daily status updates and relationship advice arrive while the system tracks progress.

   The client's `CoupleStatusInfo` table gives the **exact point economics** — 11 event types, each adjusting three separate meters (**Relation / Love / Friend points**): positive events pay e.g. **+8 relation, +3 love, +5 friend**, while negative ones claw back −2/−2/−1 — the couple system tracks a friendship axis alongside romance.
3. When Love Points reach the threshold, an in-game notification fires and the **MyView window flashes** — you may begin the wedding quests.

## Wedding quests

| NPC | Quest | Notes |
| --- | --- | --- |
| Louis Bitton (Megalopolis Square) | **Pure White** (groom) | 3× Pure White Silk; silk compounded from 5× Pure Silk Thread each, dropped by Loving Torobbie (Lv 35) in **Lovers' Maze** → 2× Pure Wedding Ticket (tradeable) |
| Louis Bitton | **Charming Black** (bride) | Bride's counterpart ticket chain |
| Fusion Master Arlene | **Love Forever** (groom) | Forever Wedding Ticket |
| Fusion Master Arlene | **Promise of Love** (bride) | Promise Wedding Ticket |
| **Kyu** (Event Garden - Ceremonia) | **Two in Harmony** | Turn in the four tickets → choose your **wedding title**, **wedding rings**, and **MyShop outfits** |

## The ceremony

- Reserve one of the wedding halls — reached through the **Wedding Hall** hub off Event Garden, with **Megalo Hall** and **Caballa Hall** wings — and invite friends to attend. Inside the hall: **Kyu** runs the Wedding Rings & Titles service, **Star Gazer Stella (2)** runs the Wedding Bulletin Board, and Tuxedo T's shop sells **Heart Spring** and **Angel's / Fairy's Fireworks** (10,000 g each) for the ceremony.
- After the wedding, the couple gains the ability to **teleport to wherever their partner is located**.

**Wedding rings (client data):** `WeddingRingInfo` defines **11 rings, each granting gendered skills** — every ring carries a `SkillIdMale` and a `SkillIdFemale`, so husband and wife receive *different* abilities from the same ring.

**Wedding dresses (client data):** `WeddingDressInfo` defines **16 dress items, each with separate male and female dress designs** (DressMale / DressFemale per item) — outfits are couple-paired, not unisex.
- The **rings** chosen during the quest grant further special abilities.
- Ntreev marked the launch with a Wedding Screenshot Forum Event: the 5 best hall screenshots won 3 Gacha Coins and a GM-signed wedding illustration poster.

## Related systems

- [Party system](17-party-system.md) (Love Points from partying)
- [Mail & communication](32-mail-and-communication.md) (memos and gifts)
- [MyShop](22-myshop.md) (wedding outfits)

## Sources

- Trickster Online Korean client data tables (user-provided `xml.zip`, 2026-09): `CoupleStatusInfo.xml` (11 event types, relation/love/friend point deltas), `WeddingRingInfo.xml` (11 rings, gendered skills), `WeddingDressInfo.xml`, `WeddingHallInfo.xml`

- [Ntreev Announces Big Content Update For Trickster Online - The Wedding System — IGN (June 2010)](https://www.ign.com/articles/2010/06/21/ntreev-announces-big-content-update-for-trickster-online-the-wedding-system)
- [Trickster Online Revolution Wedding System — GamesIndustry.biz](https://www.gamesindustry.biz/trickster-online-revolution-wedding-system-on-the-way)
- [Trickster Online Update: The Wedding System — Lore Hound](https://lorehound.com/news/trickster-online-update-the-wedding-system/)
- [Wedding — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Wedding.html)
- [Wedding Hall — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Wedding_Hall.html) (hall services, ceremony shop)
