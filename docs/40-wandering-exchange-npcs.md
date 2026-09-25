# Wandering Exchange NPCs (Lorena, Eugene, Aria, Lavida)

## Overview

**The exchange economy at scale (client data):** `ExchangeShopContents` is the master table behind every exchange vendor in this file — **2,066 exchange recipes**, each with a result level requirement, up to **3 result items**, up to 3+ request items with counts, and per-recipe failure paths. The per-NPC `Exchange_Shop_*` catalogs — **88 files in all** (the Chaos Tower's 22 exchange-shop files plus 12 ChaosJ pages — Professor Komby's forging counter — 9 Jump-NPC pages, and the per-event shops) — are paged views into it, including a typo'd `Exchang_Shop_*` subfamily (the 2009 New Year, 3-month, and test shops) preserved from development. `GhostExchange_RefineLevel` adds a refine-level gate on ghost-equipment exchanges.

A family of **weekday-relocating exchange NPCs** forms Trickster's barter economy: they aren't marked on the minimap, sometimes hide behind background objects, and each offers a different exchange chain that converts farmed junk into elemental crystals, attribute weapons, and treasure boxes — the main non-MyShop route to elemental gear.

## Merchant Lorena — 500 Galder Coupons → elemental crystals

Lorena exchanges **500 Galder Coupons for elemental crystals**, one element per weekday, relocating daily:

| Weekday | Element | Location |
| --- | --- | --- |
| Mon | Dark | Phantom School - 1F Toilet |
| Tue | Fire | Tapasco Mine - Silent Lava |
| Wed | Water | Mermaid Palace Field 2 |
| Thu | Air | Caballa Relics Field 1 |
| Fri | Electric | Pyramid Dungeon 5 |
| Sat | Soil | Poppuri Dungeon - Spore Cave |
| Sun | Light | Coral Beach Field 3 |

**Coupon cost by crystal level:** Lv 80–140 crystals cost 1 coupon; 155–215 cost 2; 230–290 cost 3; 305–365 cost 4; 380–395 cost 5. (She also keeps fixed shop/exchange schedules in Azteca and Mirage Island per the ggFTW archive.)

## Card Hunter Eugene — arcana cards → hunter crests

Eugene trades **Arcana cards** (Dream, Love, Brave, Smart — the Card ID prizes) plus character and monster cards for the **Card Hunter's Crest** family, and supplies the **Developer Photo No. 2** needed for the Underground Dev Room quests. His request combinations rotate by weekday (e.g. character-card requests on Mon/Wed/Fri/Sun use Buffalo+Brave, Dragon+Smart, Lion+Dream, Raccoon+Love; Tue/Thu/Sat use Bunny/Bear+Brave, Sheep+Smart, Fox+Dream, Cat+Love), while monster-card requests (B/C/F) ask for region monsters like Cannon Shell, Leaf Bird, and Crow. Locations: Mon Gate of Desert Beach; Tue Relics Field 4; Wed Oops Wharf Field 3; Thu Gate of Mermaid Palace; Fri Aquarius; Sat Black Swamp Field 3; Sun Rose Garden Field 1.

## Aria — crests → attribute weapons

**Aria** exchanges the Card Hunter's Crests for **elemental attribute weapons (속성 무기)** — the end of the chain that starts with Card Identification's Arcana cards and Lorena's crystals. Attribute weapons carry elemental percentages that multiply elemental skill damage (e.g. Fire attribute for Champion's Flaming Fist builds).

## Lavida & the Pirate Coin boxes (Oops Wharf)

**Pirate Coins (해적주화)** are drilled in Oops Wharf or dropped by Black Foe/Master Foe in Wharf Field 4. **Lavida** (southeast of Wharf Field 4 — clear the aggressive monsters first) trades **10 coins → 1 Pirate Gift Box**, which opens into one of three coin types sold to the Oops Wharf Item Girl:

| Item | Drop | Sale value |
| --- | --- | --- |
| Old Coin | 2–10 per box | 200 g each |
| Shiny Silver Coin | rare | 10,000 g |
| Shiny Gold Coin | very rare | 100,000 g |

Community odds: about one silver per several boxes makes the exchange profitable — a small lottery that turns Oops Wharf quest overflow into galders. Lavida also narrates the pirate-treasure lore for anyone who asks.

## Related systems

- [Card Identification](07-card-identification.md) — the Arcana card source
- [Economy](31-economy-bank-trade.md) — the coupon economy feeding Lorena
- [Quests](25-quests.md) — Dev Room photo chain

## Sources

- [카드헌터 유진, 상인 로레나 위치, 아리아 교환 아이템 — cyan's Trickster blog](https://livehepa.blogspot.com/2021/01/card-hunter-eugene-merchant-lorena.html) (weekday tables, coupon costs, crest recipes)
- [해적주화 사용해서 돈 벌기 — cyan's Trickster blog](https://livehepa.blogspot.com/2020/10/trickster-online-tip-pirate-coin.html) (Lavida, box odds, coin values)
- [Merchant Lorena — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Merchant_Lorena.html) (fixed shop schedules)
