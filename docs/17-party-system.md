# Party System

## Overview

Trickster's party system multiplies EXP (up to **2.5×**) based on party **type** and size. Parties have at most **6 members**; characters must be **level 5+** to create or join. The system rewards mixed groups and coordinated grinding.

## Creating and managing

- Press **P** (when not typing) → Create Party, then select another character who accepts. Or right-click a player → Party Request (if they lead a party, this becomes a join request).
- Leader options (Manage Party): **party name**, **leader transfer**, **EXP share** and **item share** settings, member list.
- **EXP share modes:** no-share (the killer keeps everything — the most popular for grinding), equal split, level-weighted split, and **manual** custom ratios (used to power-level a chosen character).
- **Item share:** killer-only pickup or party-wide pickup.
- **Party Bulletin** boards advertise/locate parties (listed among the in-game functions on community wikis).

## Party types

| Type | Composition | Max EXP multiplier |
| --- | --- | --- |
| **Normal** | Any mix that fits nothing else (6 members) | ~1.5× (per-member chart rises 1.2×→1.8×) |
| **Beginner** | At least one member Lv 30 or below, no member gap ≥ 100 levels; no customization until all pass 30 | ~1.2×–1.8× |
| **Type** | 4+ members all of one type (Power/Magic/Sense/Charm) | 2.0× |
| **Royal** | 4+ members covering **all four types** + any others (must not be all-one-gender or it becomes Special) | 2.5× |
| **Special** | All one gender with at most 2 of the opposite | 2.5× |

**Exact per-member multipliers** (ggFTW archive charts):

- **Normal / Beginner:** 2 members 1.2×, 3–4 members 1.3×, 5 members 1.4× EXP / 1.5× TM, 6 members 1.5× EXP / **1.8× TM** — the TM curve overtakes the EXP curve from 5 members.
- **Type:** 4 members 1.4×, 5 members 1.7× EXP / 2.0× TM, 6 members 2.0× EXP / **2.5× TM**.
- **Royal / Special:** +80%/+80% at 4 members, rising to **+150% EXP / +200% TM at 6** (the archive's 5-member value is not preserved).

**Rules of thumb:**
- The multiplier only counts members **on the same map** — a 6-person royal at 2.5× drops to 2.0× while someone is elsewhere. Leaving the map reduces the multiplier; leaving the party changes the type.
- Large level gaps downgrade a party to **Normal** (Thai-era guide: gap over ~31 levels; ggFTW's beginner rule uses 100) and disable EXP sharing in the gap case.
- A 6-member Royal/Special at full attendance is the classic grinding setup (up to +150% EXP / +200% TM boost).

**Party Quest scaling:** Officer Tera's repeatable dungeon PQs pay on a **decaying per-cycle ratio** — 1.8× on cycle 0, stepping down through the 1.2 and 1.1 bands to 0.5× by cycle 25 and just 0.1× past cycle 49 — with the payout further scaled by party size (`Earned XP = ratio × XP × (0.25 + (members − 1) × …)`). PQs are repeatable group content by design, not an infinite farm.

## The party system in client data

**The party-type rulebook (client `PartyTypeComment`, 8 rows):** the UI's own conditions —

| Condition | Effect |
| --- | --- |
| Under 4 members, or any member on a different map | no bonus |
| 4 members of **all four different types** | "최상급의 파티" — the top-grade (Royal) party |
| All 4 the **same type** | EXP ×1.05 |
| All 4 the **same gender** | **HP/MP recovery speed +20%** — a regen bonus, not EXP |
| A **full** party of 4 | EXP ×1.05 |
| All 4 the **same level** | EXP ×1.2 |
| 4 members' levels in a **multiple (배수) relation** | EXP ×1.2 |

(These are the 4-member baselines shown in the UI; the per-size charts above — up to 2.5× at six members — scale on top. The table also carries a styled **SEPARATE (세퍼레이트)** header, a party-type label of its own.)

**The complete PQ decay curve (client `PartyQuestExpTable`, 50 rows):** the payout ratio steps down in bands **with a milestone bonus every 5th cycle** — 1.8 → (1.2 ×3) → **1.7** → (1.2 ×4) → **1.6** → (1.1 ×4) → **1.5** → (1.1 ×4) → **1.4** → (1.0 ×4) → **2.0** → (0.5 ×4) → **3.0 — the peak, at cycle 30** → (0.3 ×9) → (0.2 ×10) → 0.1 at cycle 50. The flat-decay description above misses the 5th-cycle spikes and the 3.0× peak; the client curve rewards persistence to the 30th run before collapsing.

**The PQ catalogue (client `PartyMonQuestInfo`, 78 quests):** one party quest per region and dungeon, all issued by **Security Officer Tera (치안담당요원 테라)** — Desert Beach Lv 1+, Pyramid Dungeon 25+, Poppuri Dungeon 30+, Caballa Relics 50+, Underground Relics 55+, Oops Wharf 60+, Mermaid Palace 70/75+, Ghost Blue 95+, Nora Sewers 100+, Rose Garden 115+, Vamp Castle 125+, onward to the late regions — each with its own **time limit** and **weighted monster quotas** (up to eight monster slots with per-monster counts and weights).

**Party zones (client `PartyZoneInfo` / `PartyZoneBossInfo`):** the 32 party-zone maps carry **closing teleports** (a 30–33 s countdown that ejects the party to a fixed destination zone) and **re-entry cooldowns of 10–45 minutes**. The 31 party-zone **bosses have entrance and exit voice lines with voice files** — Tutankhamen ("Who dares disturb my peaceful rest… may **Tutankhamen's curse** be upon you!"), Vlad of Vamp Castle ("may **Vlad's curse** be upon you!"), a Latin-chanting guardian ("WhO.EccilLum.VIgilo.CuratoRia! OoOOo!"), and a growling beast ("크르르르~").

## Related systems

- [Guild system](18-guild-system.md)
- [Quests](25-quests.md) — Party Quests and party-scaling quests
- [Fiesta Zones](29-fiesta-zone.md) — party-friendly bonus maps

## Sources

- [Party — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Party.html)
- [Trickster (MMORPG) — Wikipedia 2007 archive](https://wikipedia2007.classicistranieri.com/en/t/r/i/Trickster_%28MMORPG%29_504d.html) (type/multiplier definitions)
- [Party tip article — Guwnteen blog (Thai)](http://guwnteen.blogspot.com/2011/05/trickstertiptrick.html) (share modes, level-gap rule)
- [Party Quests (cycle ratios & formula) — Our Trickster Online Wiki](https://oto.fandom.com/wiki/Party_Quests)
- [Functions list — Our Trickster Online Wiki](https://oto.fandom.com/wiki/Episode_Quests) (Party Bulletin)
- Client data: `PartyTypeComment` (8-row type rulebook incl. same-gender regen +20%, same-level/multiple-level ×1.2 bands), `PartyQuestExpTable` (50-cycle curve with 5th-cycle bonuses, 3.0 peak at cycle 30), `PartyMonQuestInfo` (78 Tera PQs), `PartyZoneInfo`/`PartyZoneBossInfo` (closing teleports, re-entry cooldowns, 31 voiced zone bosses)
