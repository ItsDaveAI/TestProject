# Item Encyclopedia — Unique-Use Items

## Overview

**The master item table (client data):** `ItemParam2` enumerates **8,584 items across 76 fields each** — every item in this encyclopedia is one row there, carrying class/type/subtype, Korean *and English* names, comments, use-text, icons, and full stat blocks. The family around it: `Item_Attribute` (908 item-attribute rows), `Item_GunParam2` (**599 guns**, each with a gun type, gauge speed, and a **min–max attack power range** — gun damage varies within a band, not a fixed value), `Item_BookParamExt`/`Item_BookRefExt` (232+174 books), `Item_SkillCardParam` (305 skill-card items), `Item_ExpParam` (**32 EXP/TM boosters** with exact ratios — the 1.5× EXP / 1.8× TM tier, 1.2×/1.3× tiers, each with separate penalty fields), `Item_MemoryPortParam` (portable-memory teleports), and `Item_SpeedParam` (51 speed values). The 100-item VIP exchange catalogue and unique-item broadcast tier are documented above.

**The timed economy (client `GeneralTimerItem`, 1,286 rows):** every timed item carries an exact duration in minutes — from **60 minutes** to **259,200 minutes (180 days)** — the complete rental ladder behind the 7-day/15-day/30-day tiers described throughout this encyclopedia. `PresentItemParam2` (1,364 rows) is the gift-box/present family that delivered them by mail.

**The box loot engine and the branching bonus (client data):** every present box runs the same loot table — up to **4+ possible contents with percent rates** (one verbatim box: 40% / 50% / 100% / 30% across four drops), and the `BonusPresentItemInfo` family adds a **choose-your-bonus mechanic**: one documented box (431762) contains a selectable item (71915) where **claiming the bonus yields one present ID (431763) and declining yields a different one (431764)** — pick-or-skip boxes with different rewards either way.

**Item-class scale (client `ItemParam2`, 8,584 rows):** the master table splits **6,998 use/etc. items (Class 1), 1,464 equipment (Class 2), and 122 Class 3 items** (the card/special families) — with the ~6,136-row `ItemParamCM2` growth-compound line and 1,219-row `ItemParamEx` unique/effect line alongside.

**The random-stat engine (client `RandomStatValueTable`, 3,141 rows):** every randomized-stat item — box equipment, Ultimate/Chaos/Master gear, the uniques — draws from a per-item row holding **each stat's Min–Max range plus an Up/Down import flag** (verbatim: item 32700 rolls AP 1–37 and DX −3 to −7, both "Down"-typed) — the engine behind tempering's special case for randomized gear. `Equip_Property` (5,603 rows) is the companion **per-item applicability matrix** (ApplyRatio + enabled properties) — equipment's counterpart to the pet property table.

Trickster Online's item taxonomy (per the ggFTW/LifeTO classifications) spans **equipment** (weapons: swords/knives/canes/guns/special + ammunition; armor: hats/shields/innerwear/capes/face items; accessories incl. **Speed Acc.**, Head/Face Acc.; drills; pets; soul guardians), **Use items** (boxes, books/letters, galder coupons, HP/MP recovery, teleport devices), **Etc.** (compound materials, ores/gems, hardants, job-change items, mastery items, quest items, throwing weapons), and the **card** families (skill, star, monster, character, secret, fortune, etc.). This file catalogs the items with a *unique* use — the ones you can't guess from the sprite — with cross-references to their systems.

## Equipment modification catalysts

| Item | Unique use |
| --- | --- |
| **Repair Powder** | Repairs equipment **broken by failed refinement** (Marx reports the exact powder count). The **Phantom Repair Powder** variant (Mad Ray quest) works identically but stacks only with itself. Common gacha/event filler. |
| **Chaos's Feather** (tiers 20–185) | The **tempering** catalyst — 3 per temper at Alan, matched to the equipment's level bracket; sourced from Party Quests, Treasure Hunts, Keeper Julio missions, and Card Identification ([Tempering](10-tempering.md)). |
| **Anvils / Refine Fortune Cards** | Refining assistants used at Blacksmith Marx to **raise refinement success rates**; Anvil Stones (+50% for refine Lv 5–13) are the documented booster form. |
| **Artisan's Flame** (장불) | The [fusion/defusion](11-item-fusion.md) catalyst — fuses an image item onto stat gear; also consumed to defuse back into a tradable Form item. |
| **Nate's Bottle** | Frees **one compound slot**, deleting the compound material inside — the redo button for [Maturing Compound](09-maturing-compound.md) (MyShop 3,600 pts, Lv-Up boxes, compound events). |
| **Black Elixir** | Compound assist: **raises the minimum** compound roll by 20% (MyShop 2,700; Lv-Up boxes). |
| **Green Elixir / White Elixir** | The companion elixirs raising the **maximum** compound roll (Elixir Boxes from the Treasure Hunt minigame hold Green/White/Black). |
| **Black Green Elixir** | Both elixir properties at once, with the green (max) effect 10% stronger than standalone; cannot combine with either (MyShop 3,600). |
| **Magic Stones / Capsules** | MyShop compounding: stones add basic stats, capsules add elemental attributes (tiered 0–400 by equipment level; 900–1,300 pts). |
| **Gold Gems** | Increase the tempering range for certain stats (PandaTO's documented route: Level Up Gift Boxes). |
| **Region Refining Coupons** | Trader Pav's Black Market currency for **upgrading region-set equipment**. |
| **Sharp / Moon / Art / Artisan / Strong equipment** | Dark Dealer Rat's Black Market stock — the buyable stat-gear families of the secret shops. |
| **Compound item ladders** | Per-stat monster parts and stones (AP Stone → AP Stone 140, Sharp Leg, Crow's Claw, Whetstone…) — the stat-compound materials themselves ([Compound](09-maturing-compound.md)). |
| **Refine stones** | Fragment/Impure/Pure/rare ores (physical) and the Quartz→Cassiterite magic family, drilled in mines ([Refinement](08-refinement.md)). |

## Character-building consumables

| Item | Unique use |
| --- | --- |
| **Master's Authority** | Deletes **one skill** and refunds its TM points (prerequisites must be deleted first) — MyShop 4,500 pts; the Poppuri event's stage-4 prize. |
| **Skill Reset Set** | 3× Master's Authority at 20% off (10,800 pts). |
| **Build Graph Reset** | Resets the **4-digit Build Graph** and its bonus stats (21,900 pts) — how Magic types migrate from M4/S3/C2 to the M4/S4 glass build. |
| **Point Back 40 / Point Back All** | Refunds 40 / all allocated bonus stat points (4,500 / 19,800 pts). |
| **Skill cards** | Learned at the four Garden of Skill Master masters — Master Louis (Power), Magician Sephira (Magic), Genius Cochma (Sense), Glamour Tiphreth (Charm) — who also perform **skill mastering**. |
| **Mastery cards** | Per-skill master items, mostly monster cards ×2–40: Clione (Power Blow, Shockwave, Mana Arrow, Sixth Sense/Stone Strike), Hula Octopus (Bull's Eye, Cure, Heavy Carrier, Dodge Master), Mummy (Pumping Heart, Shield All), Nephthys (Burning Rave, Mana Ring, Mana Reflector), Koom (Upper Smash, Mist of Mana, Skunk Pouch/Titanium Wrist), Quiem (Uppercut/Lacerator, Item Detector/Power Shot), Ironclad Turtle (Bolster Ballad, Card Strike, Volley Kick), Crow (Berserker ×3, Piercing Wave ×18), Lima (the Bard element spells), Royal Jelly ×55 (Lucky Fist), Book of the Dead ×20 (Sense Breaker, drilled), Malachite ×10 (Dark Barrier, drilled), Nephthys Song ×40 (Siren Song). |
| **Potion ladder** | Pink/Blue A → B → C (100/200/500) from Item Girl; MyShop tiers beyond: **WF (400), G1 (600), G2 (1,100), Hyperium (4,000)** potions. |
| **Booster Bracer Ex** | A timed accessory that **multiplies EXP and TM EXP ×3** (Lv 100/180 gift boxes, Gacha Town SP Tapasco) — not a speed item. |
| **Star Tears / Star Tears EV** | Extend [Star Gazing](16-star-gazing.md) fortune durations; earned from Shadow dailies or MyShop. |
| **Scroll family** | Secret Scrolls (AP/MA/LK/HV/DA, personal + party, scaling with level), detection scrolls (Basic 80 m/Super/Party), Warp Defense, Resolute, Illumination, Rejuvenation — MyShop buffs also obtainable via [Recycling](24-recycling.md). |
| **Seal family** | MyShop useable boosters: stat seals (AP/DA/DP/HV/MA) and effect seals — **Drop Rate Seal, EXP Seal, Speed Seal, GP Seal**. |
| **Rune family** | MyShop useables named for the Skill Masters — **Louis' Rune, Cochma's Rune, Sephira's Rune** — plus **Auto Defense Rune** and **Multi Mark Rune** (era-wiki function details sparse). |
| **Soul Feather Pen / Soul Ticket** | The Soul-system useables of the MyShop usable category. |
| **Hair Dye** | Per-character/per-job color dyes (e.g. Raccoon Hair Dye, ~2,700 pts) — a new color applies per job form. |
| **Secret Scroll (Power/Magic/Sense/Charm)** | Type-stat scroll: e.g. Power boosts **AP & AC by 70% of your level** for 300 s (egg shop/event). |
| **Ultra Pink/Blue Potion** | The Poppuri event's premium potion tier (50× as stage rewards). |

## Movement & travel

| Item | Unique use |
| --- | --- |
| **Speed accessories (Sprints, Wing Charms, Objet d'Art)** | The MyShop speed ladder: Levitation Charm +30% → Dashing Sprint +60% → Stallion/Gallant/Snappy Sprint +70% → Mystic Favor, Sign of Charisma, Kid Angel/Demon's Wing Charms +80% → Speedy Wing/Mega Kid Charms +90% (Lv 150–170) → Objet d'Art +90% (Lv 190) and beyond toward +100% at Lv 270 — timed ~7 days, compoundable. **Stallion Sprint** also comes from the Lv 40 (3-day) and Lv 140 (7-day) gift boxes. Each tier ships in **paired variants** for physical (AP/AC/LK/HV) and magical (MP/MA/DA/LK) stat blocks — the Lv 140 event Stallion even splits by type (15-day) — and **free event versions** ran alongside: the **Feather Charm** (the free Levitation Charm), the 3-day **Poppuri Sprint**, and the *permanent* **Kitty Earrings** (Special Film events, variable stat ranges) and **Princess's/Queen's Anklets** (Odinea boxes). |

**Speed data (client):** `SpeedItemParam` enumerates **56 speed items with their exact AddSpeedRatio values** (0.6 for the Dashing tier, 0.7 for Stallion-class, … up to 1.0) — the ladder above is confirmed by the client's own numbers, not just wiki text.

**The Unique equipment tier (client data) — two distinct classes:**

- **Legendary Uniques (전설 유니크)** are the **boss-legend equipment line**: Gold Sword and Pharaoh Hat (Tutankhamen's theme), Blood Sword, Vampire Mark, and Blood Shield (Count Blood), White Gun, Red Eyepatch, and Black Hat (Captain Skull's pirate line), Tenterion's Tail Spear (Tenter Lion), Golden Lion Shield, Ankh Pendant, and Earring of Sacrifice — each flagged "전설 유니크" in the item master. Collecting them feeds the boss **Set titles** ([Chaos Tower — Titles](28-chaos-tower.md)), and Tapasco NPCs **recognize the gear by sight and gate quests on it** — see [Bosses](27-bosses.md).
- **Absolute Uniques (절대 유니크)** are the Tartarus endgame tier — exactly **two trilogies**: the **Shining Crystal set** (Sword/Helmet/Shield, "pure-white steel radiating a soft light, blessed with holy power") and the **Fallen Watcher's set** (Cane/Helm/Shield, "the fallen soul of the Watcher who spectates the world, sealed — carrying the power to see through everything"; the Watcher being Chronos-adjacent Tartarus lore). Their item text carries a unique covenant: **"you must perform the duty entrusted to the equipment to keep using it"** — duty-bound gear.

  **Legendary drop tables (client `LegendItemGroup`/`LegendItemList`):** each boss owns a legendary pool with exact rates — e.g. the Tutankhamen group (monID 2097) drops items 50001/54001/56001/50017 at **20% / 30% / 30% / 20%** per kill — the 63-item `LegendItemList` behind the boss-legend line above.

**Repair costs (client `RepairInfo`, 182 rows):** broken-equipment repair is table-priced — per refine level and equipment type/subtype, the exact **repair item ID and count** (e.g. refine-0 headgear → item 64799 ×1); the data behind Marx's "I'll tell you how many Repair Powders you need."

**Absolute Unique covenants (client `UniqueItemUIParams`):** equipping one triggers a red-letter warning — **once equipped it cannot be unequipped; forced removal destroys it**, and **an equipped Absolute Unique can drop from your corpse on death**. **Disguising (변장) force-removes and destroys it** (the disguise system asks for confirmation first). They carry their own refine display tier (`RefineLevelTable` lists "절대 유니크"), and acquisition scales with monster level (`UniqueItemCountTable`: the Lv 1–60 band at 0.001 rising band-by-band to **1.0 at Lv 401–999** — Tartaurus-tier monsters), with the six Absolute pieces each at **20% drop probability** (`UniqueItemDropProb`). The tier has its own UI with server-wide **broadcast on pickup** ("%s 님이 %s 아이템을 획득했습니다") and **despawn warnings** ("%s 아이템이 소멸되었습니다").

  The duty covenant, made precise (`UniqueItemStrings`): **failing the Absolute Unique's duty destroys *all* your Absolute Uniques** ("절대유니크의 의무를 수행하지 않아 모든 절대 유니크가 사라집니다") — total-loss enforcement, not per-item. Spawn and destruction each carry tagged server-wide notices (**[절대 유니크 출현] / [절대 유니크 소멸]** — "Absolute Unique appeared / destroyed"), event items get the same broadcast treatment, and **honor-title acquisition is broadcast too** ("%s 님이 %s 타이틀을 습득 하셨습니다").

**Transformation items:** the **Mermaid Transformation Potion** (인어 변신약 — "eat it to become a mermaid; a side effect may steal your voice," the Mermaid Palace quest chain's potion, brewed from sea-spirit Lumo's elixir), the **13 transformation picture frames (변신 액자)** — baby-rabbit/baby-buffalo and the rest, the Card Identification Special-table prizes ([Card ID](07-card-identification.md)) — sold in a 13-frame box and a Special box, and **82 transformation scrolls** (`TransScrollInfo`). The **Disguise (변장) system** is the appearance-change layer over these — its own UI ("choose the appearance to disguise as"), with a 2nd-job restriction message and the Absolute-Unique destruction rule above.

**Defusion dummy skins (client `DecompoundDummyItem`):** decompounding (defusing) fused gear substitutes a **placeholder skin per slot** — weapon 87003, gun 87501, hat 88002, shield 88502, head 441078, face 441509, cape 442081, hammer 92024 — the visual aftermath of [Fusion](11-item-fusion.md)'s reverse operation.
| **Mega / Giga / Tera Brand** | The *unlimited-duration* speed accessories exchanged from Harkon Protector drops ([Harkon Protector](15-harkon-protector.md)) — +40% → +70%. |
| **Broken Speed Charm** | Free +30% unlimited speed accessory every character receives at creation. |
| **Wing Port** | Single-region teleport scrolls sold by Item Girl (1,000–3,000 g). |
| **Portable Port / Portable Port AD** | Consumable teleports to gates/towns; the AD version covers nearly the whole island (MyShop/event). |
| **Weight accessories (무게부)** | Capacity boosts — generally skipped by the meta for occupying the accessory slot. |

## Death & recovery

| Item | Unique use |
| --- | --- |
| **Flower of Revival** | Usable **at 0 HP**: recovers 20% HP and MP and — uniquely — **preserves your in-progress Monster Quest** on death. Grown only in Carbigal; quest/event reward; untradeable (a 3rd-job chain reward, 3×). |
| **Resurrect Scroll** | Standard revival scroll (Lv 120 gift box; sold at Item Girl on some servers). |
| **Chakra Balance** | The HP-regen *skill* rather than item: +100→800 HP per 2 s for 30 s, dropped by Chaos Tower 36F+ monsters (see [Recovery](37-interface-controls-and-recovery.md)). |
| **Beginner's Scroll of Revival** | The newbie-tier revival scroll. |

## Currency & tokens

| Item | Unique use |
| --- | --- |
| **Galder Coupons** (10/50/100/500 + 1k–30k denominations) | The coupon economy: quest rewards, [Lorena's crystal exchanges](40-wandering-exchange-npcs.md), and map-entry fees. |
| **Galder Checks** (100k/1M/5M) | 5%-fee large-denomination transfers via Andrew; 2nd/3rd-job items. |
| **Galder Pile** | Dropped galders as ground loot. |
| **Gacha Coins** | 1,000 pts each — the [Gacha](23-gacha.md) dig currency. |
| **Bonus Eggs** | MyShop mileage (1 per 5,000 pts; 2× during Double Egg events) for the [Egg Shop](36-egg-shop-and-pet-breeding.md). |
| **4G Cards** | Gacha set-completion prizes → Solar/Nocturnal equipment at Rosemary; questable on LifeTO. |
| **Fiesta Ticket / Fiesta Marbles** | Fiesta entry; marbles drop inside for Heidi's TTX Pet/Jasmine gear ([Fiesta](29-fiesta-zone.md)). |
| **O/X Ticket** | GM quiz entry (60 distributed per event). |
| **Poppuri Driller/Hunter Boxes, Poppuri Tickets** | The community-goal event currency ([Events](30-events.md)). |
| **Pirate Coins → Pirate Gift Box → Old/Silver/Gold Coins** | The Oops Wharf lottery at Lavida (200 g / 10k g / 100k g payouts). |
| **Recycling Tickets** | MyShop-item recycling currency for the [Recycle Shop](24-recycling.md). |
| **Harkon Coins / Harkon Exchange Tickets** | The Korean Harkon-defense event attendance currency (up to 500 by cumulative attendance). |
| **GM Gift Certificate** | The O/X quiz prize. |
| **Caballa Stickers** | Key-quest tokens (10 to the Fortune Teller unlock a region). |
| **Evil Thought Mass / Corrupted Soul** | Harkon-defense drops that buy the Brand speed charms. |
| **Love Points (memos & gifts)** | The wedding-gauge currency ([Wedding](20-wedding-system.md)). |
| **Weapon / Pet Exchange Tickets** | Pola-launch event rewards — trade for gear/pets of choice. |

## Access & key items

| Item | Unique use |
| --- | --- |
| **Growth Badge** | 2nd-job item from Kaboom (Relics Dungeon 4). |
| **Ticket of the Valiant** | 3rd-job item (Clurican, Tenter Lion, or drilled in Swamp Dungeon). |
| **Guardian Stone** | The per-class 3rd-job stone from each Job Master (Dark Lord's runs through the Snow Hill mine + the hidden shaft-2 NPC). |
| **Harkon** | 3rd-job material + Enlightenment currency — drilled at volcano fields/Chaos Tower battlefields, or Marx's 5-cycle Snow Hill mine quest. |
| **Sacred Water, Adamantite, Light/Dark Alexandrite** | The remaining 3rd-job materials (Alexandrite from Janus's Mask + mine ores for Dark Lord). |
| **Secret Cards ×16 → Secret Space Map** | The awakening chain keys — found via Card ID and Nephtri's Dimensional Card Pack, assembled into the map that opens the hidden space ([Guardians](13-guardians.md)). |
| **Dimensional Key** | Eclipse's key to the Mind's Eye quest space. |
| **Questionable Letter / Eclipse's Message** | The mailed chain-starters at Lv 135 / Lv 180 — discard them and the chain stalls. |
| **GPS-1 ~ GPS-4** | Radar items for the Poseidon's-treasure digs — Monster Quest drops that count down (1 = nearest) to a buried chest. |
| **Worn / Old / Weird Treasure Maps** | The treasure-hunt tier ladder; the Weird tier opens each region's [Black Market](31-economy-bank-trade.md). |
| **Brick / Chaotic / Fractal Guide Stones** | The Tombeth 11-room maze navigators (+1 room / random / +4 rooms). |
| **Dev. Room Card Key** | Underground Dev Room entry — 156,000 g at Monkey T, or the Mirage Island episode reward. |
| **Boss entry items** | 3× **Addax Horn** to Monkey T for the Lv ≤30 Master Mong bout (Coral); 2× **Spicy Egg** to Cletta for Spicy Dragon; 1× **Pink Potion A** for the Colosseum; 1× **500 Galder Coupon** for Tombeth's path. |
| **Wedding tickets** (Pure/Charming/Forever/Promise) | The four quest-built tickets Kyu takes to issue rings, titles, and outfits. |
| **Compound Waste** | The **duel entry item** — 3× to Don Giuvanni for the Battlefield of Duel. |
| **Spicy Egg / Fried Egg** | Dual-use: 2× Spicy Eggs open the Spicy Dragon trial, and 10× each feed the Janus-messenger guardian quests. |
| **Silver Aquamarine / Peridot** | Fox's 3rd-job class stones (Thief Master / Hunter Lord), paired with Sacred Water at Reina. |
| **Weird Box + "Vendetta"** | The Relics Dungeon password box guarding Scenario 1 Chapter 2's documents. |
| **Coin (동전) ×15** | The universal quest staple dug on every field — bank 15 before anything. |
| **Harkon Relic** | Double-click **lottery**: chance at the Harkon necklace (Chapter 3) or Harkon shards spilling sellable gems. |
| **Sage's Stone Shard** | The famous **junk trap** — looks like a Harkon shard, does nothing. |
| **Sign of X / Light Compass / Marble of Triumph** | The advancement reward accessories: class Signs (Fighting Spirit/Sword/Sound/Excavation/Card) at 2nd job, the Light Compass + accessories at 3rd job, the Marble from the Door of Tribulation. |
| **Tower chain items** | Survey Notebooks 1–6 (exchanged per floor), **Chaos Integers** (12/36 Byte…), the **Mysterious Video Disc** (floor-7 unlock), and the **Requiem Box** (Stage 2+, from the dimensional-gap timed kills). |

## Card & mastery items

| Item | Unique use |
| --- | --- |
| **Monster/Character/Neutral cards** | [Card Battle](06-card-battle.md) ammunition — each monster drops its card; extreme ranks (near 1 or 15) preferred. |
| **Skill cards** | Learned into the C-window skill tab; the mastery cards above finish them. |
| **Star Cards / Star Card Packs** | Fortune-fuel, numbered by stat+power (AP = No.2–9 … EXP = 103–107) from packs No.1–7 + themed packs. |
| **Secret Cards** | Card ID's rare pulls — the awakening keys above. |
| **Arcana Cards** (Dream/Love/Brave/Smart) | Eugene's crests → Aria's **attribute weapons** ([Exchange NPCs](40-wandering-exchange-npcs.md)). |
| **Mystery Card** | The wildcard in Eugene's Special request recipes. |

## Pet & guardian items

| Item | Unique use |
| --- | --- |
| **Protein Candy / Lock Candy** | [Pet Training](12-pets.md) — reroll a pet's stats / lock a stat during the reroll (MyShop + events). |
| **Hardants** | Pet Reinforce compound items, typed per stat into open Talent Slots. |
| **Growth Vitamins** | Level up **Egg Pets** alongside you at Pet Breeder Erin. |
| **Pet Rice Ball / Drink / Ice Cream** | Fuel a pet's [Item Hunt](12-pets.md) — the consumable type sets the hunt speed and item cap. |
| **Erin's Secret Book** | Unlocks Pet Fusion (stats pet + image pet). |
| **Poseidon's Seed** | The maturing seed that hatches into your Guardian; the **Dimensional Card Pack** that follows drops Secret Cards. |
| **Guardian's Source** (Unknown Ore / Shadow Piece / Blue Jewel) | Registered in Soul Management to passively generate **Soul Potions** (+25/60/75% gauge per 15 min, even logged out) — fuel for Tartarus's [Soul Weapons](33-korean-version-systems.md). |
| **Koius's / Chronos's Souls 1–7 + Tartarus fragments 1–10K + boss parts** | The Sky Anvil's Soul Weapon recipes (rock fragments, wheels of fate, underground cores, proliferating cells, light sources, black auras). |
| **Guardian Guide / Summon Guardian / Gift from Danihen / Don Danihen Card** | The awakening-chain tokens and its consumables (10× Spicy/Fried Eggs, 10× Great H/M Potions, 3× Candied Apples). |

## Drills, ammo & throwables

| Item | Unique use |
| --- | --- |
| **Drill taxonomy** (131 documented) | NPC drills are **soil-typed** — Sand / Land / Rock, plus Sea, Ice, and Snow families — in Regular and Neo grades No.1–8 by depth, alongside **Multi Drills** (all soils) and a **Stage 1–12** rating that sets drilling EXP. MyShop drills are **All-Types**: Bubble/Propeller (120 m), Flicker (300 m), Angel Jr., then the 60/120/180 **specialty quartets** — **Crazy** (stress rate ↑ for Crazy Drilling), **Novice** (gauge window ↑), **Speed** (+30% drill speed), **Tank** (extra lifespan) — up to Hot/Ice Cream (350 m, stage 9), Bling (400 m), Puppy (420 m), Thiefmon (500 m, stage 12); named specials include Angel Drill 500, Chaos, Diamond, Marble, Mirage, Musume, and Cleaner/AD drills. The gacha **Flicker Drill** guarantees rares; the event **Super Poppuri Drill** and **Treble** round out the specials. |
| **Empty Card** | **Ammunition for Card Strike** — Raccoon's AoE consumes one per cast (10 g at Item Girl). |
| **Throwing weapons** | Bone Needle, Double-Shielded Marble etc. — the thrown-weapon arsenal (Throw AP). |
| **Gun ammunition** | Ammo items for Lion's gun attacks. |

## Equipment star ranks & refinement math

Equipment carries a **star rank** — 0★ Old, 1★ Normal, 2★ Special, 3★ Rare, 4★ Unique, 5★ Legend — that gates its refinement magnification. Refinement success declines per level (100% at Lv 1 → 90/80/70/60/50/40% by Lv 7+), while the magnification ratio climbs (Lv 1 ×1.10 → ×1.20 for 4–5★; ×1.20 → ×1.40/×1.60 at Lv 2–3 for 4–5★, reaching ×2.74 at Lv 7 for 4★). Anvils and Refine Fortune Cards bend the odds; failures **break** the item (hence Repair Powder). Timed gear (7/15/30-day) is recharged with [Recharge Coupons](22-myshop.md) via Pia.

## Unique named gear

| Item | Unique use |
| --- | --- |
| **Golden Sword** | Tutankhamen's low-rate legendary drop — the early-game status weapon. |
| **Solar / Nocturnal sets** | 4G Card exchanges (Lv 100 Solar / Lv 180 Nocturnal families). |
| **Chaos / Requiem / Altiverse / Otherworld (이계) / True Soul gear** | The tower-forged families — forgeable ([Forging](35-forging.md)), Lv 110 Spiritual → Lv 335 Crimson sets, Lv 350 Chaos/True Soul. |
| **Morph / Powerful equipment** | Trader Pav's old-gear upgrades / Compounder Vin's Nikarium forgings at the [Black Market](31-economy-bank-trade.md). |
| **Gloom / Phantom equipment** | The Shadow World and Phantom Dungeon farm gear — LifeTO's galder engines. |
| **Attribute weapons** | Aria's crest exchanges — elemental percentages multiplying element skills. |
| **Boss uniques** | Boss-pet/treasure-box exclusives (LifeTO raises their drop odds; PandaTO allows tempering them). |

## Books & letters

The readable layer: **Refining Guide** (Marx), **Recovery Guide** (Winnie), **Shortcut Guide** (Lifeguard Bean), **Stars and Fortunes Book**, **Crazy Drill User Manual**, per-class **2nd/3rd Job Guides**, Drilling for Dummies, Adventurer's Books, **Legendary Recipe** — plus the story letters (Director's, Child's, Unsealed, Questionable, D's, Nefertiti's) that carry the quest chains.

## Novelty & social items

| Item | Unique use |
| --- | --- |
| **Disguise Kits** | Transform into a monster — Poppuri, (Shadow) Poppuricia, Blue Penguin, Cora, Young Lady/Madame Snow, Al Hauri, Maid Lydia, Thiefmon, Rudolph, Ice Cream, Master Mong… The disguise **cancels on fainting or logout, and you cannot use skills while disguised**. Sourced from MyShop/events (3 Recycling Tickets + 200,000 g in the Recycle Shop). |
| **Transformation picture frames (변신 액자)** | The Card ID reward pool's transformation items. |
| **Poppuri Surprise Scroll** | Summons a Poppuri to **shock and surprise your victims** — the prank item. |
| **Megalo UFO** | The reward for Genius Cochima's giant Relics quest chain (with a Caballa Sticker). |
| **Mic** | The MyShop social usable. |
| **Heart Spring / Angel's Firework / Fairy's Firework** | The wedding-hall ceremony consumables (10,000 g each at Tuxedo T). |
| **Level Up Gift Boxes** | The milestone reward channel — see [Stats & leveling](02-stats-and-base-leveling.md). |

## Related systems

Every section above cross-references its system file; the taxonomy maps to [Interface & slots](37-interface-controls-and-recovery.md), [MyShop](22-myshop.md) for the purchase layer, and [Economy](31-economy-bank-trade.md) for the trade layer.

## Sources

- [ggFTW Trickster Wiki item pages](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Flower_of_Revival.html) (Flower of Revival, Black/Green/Black-Green Elixir, Elixir Box, Nate's Bottle, Booster Bracer Ex, Stallion Sprint, Lv Gift Boxes)
- [MyShop / In-Game Event / MyShop Event Speed Accessories — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/MyShop_Speed_Accessories.html) (sprint stat blocks, type pairs, permanent event earrings — sister pages linked therein)
- [MyShop Potions List — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/MyShop_Potions_List.html) (reset items, potion tiers)
- [MyShop Speed Accessories — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/MyShop_Speed_Accessories.html) (sprint ladder)
- [Card Quest & Skill Mastery Items List — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Card_Quest_%26_Skill_Mastery_Items_List.html) (mastery cards by region)
- [Category:MyShop Usable — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Category_MyShop_Usable.html) (Seal/Rune/Soul/Mic/Hair Dye families)
- [MyShop Drills — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/MyShop_Drills.html) (drill roster with specialties)
- [Category:Drill / Drills Chart — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Category_Drill.html) (131 drills, soil families, Stage 1–12)
- [Garden of Skill Master — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Garden_of_Skill_Master.html) (skill-mastering NPCs)
- [Refinement / Customizations — PandaTO Wiki](https://pandato.fandom.com/wiki/Refinement) (star ranks, success/magnification table, anvils, Refine Fortune Cards, Anvil Stones)
- [Items — LifeTO Knowledgebase](https://knowledge.lifeto.co/items) (type taxonomy)
- [Trickster Online Tips blog](http://tricksteronlinetips.blogspot.com/) (Master Mong's Addax Horn entry)
