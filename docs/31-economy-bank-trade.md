# Galders, Bank & Trade (Economy)

## Overview

**Galders** are the in-game currency. The economy runs on monster drops, quest coupons, equipment trading between players, and the bank/storage network in the capital. Trading between players happens through **direct trade**, **personal shops**, and the mail system's **Trade Mail** (there is no auction house in the official client; OurTrickster's web Auction House is a server addition).

The black market largely skipped the game: the Korean community record notes that even shops specializing in RMT macros **couldn't find Trickster macros to sell** — the game earned too little per hour to be worth farming, part of why the culture stayed "almost a community game" rather than a gold-sink economy.

## Currency forms

| Form | Value | Notes |
| --- | --- | --- |
| Galder | 1 | Drops from monsters; carried directly |
| 10 / 50 / 100 / 500 Galder Coupons | face value | Common quest/monster-quest rewards; double-click (or spend) to redeem |
| 100k Galder Check | 100,000 | Buy from Andrew (Megalopolis Bank / Azteca) for **105,000** (5% fee); cash by selling back to Andrew; 2nd-job item |
| 1 Mil Galder Check | 1,000,000 | 1,050,000 (5% fee); 3rd-job and tribulation item; also Poppuri Olympics reward |
| 5 Mil Galder Check | 5,000,000 | 5,250,000 (5% fee) |

Checks are **tradable and bankable but not droppable** — the standard large-denomination transfer medium.

## Bank & storage (Megalopolis Bank)

| NPC | Service | Cost |
| --- | --- | --- |
| Andrew | Galder checks (buy/redeem) | 5% fee |
| **Lovely Angelina** | Warehouse service | 50 g |
| **Banker Lisa** | Bank safety service | 100 g |
| **Pia** | Storage service | Free |
| **Pia** | Recharge service (timed items, via Recharge Coupons) | Free |

- **Warehouse/bank** moves items between your own characters (pets are bankable, not tradable — see [Pets](12-pets.md)).
- **Storage** capacity expands with the MyShop **Store-More Permit** (+8 warehouse slots and stored weight, permanent, 4,500 pts).
- Branch services appear in town shops region-wide (e.g. Banker Lisa and Angelina also at Paradise Shop).

## Player-to-player trade

**NPC shop mechanics (client data):** the `ShopItem_*` per-town inventories (Beach, Coral Town, Relics, Beach/Relics Town, the Fiesta shops, Mirage Ep3, a Japanese event shop, and the Cherry-Blossom event shop) price every stocked item with **PurchaseRate and SellingRate multipliers** (buy vs. sell pricing) and an **OutOfStock flag** — NPC shops could run out of items.

The `R_ShopItem_*` family (~40 tables, e.g. Snow's 75 goods) extends the same schema to **every region's general stores** — bullets, empty cards, and the Pink Potion B/C consumable staples across the island — and `TeleportInfo` (225 rows) prices **level-gated teleport destinations** (per destination: minimum level, zone, cost) alongside Pachi's dialog menus.

**Commerce rules (client strings):** personal shops are searchable via the **`/상점검색` (shop-search) command** — 2+ characters of an item name returns every shop stocking it **with map coordinates** ("[%s]님의 상점 — 좌표(%d,%d)"). NPC shops flag item classes on sale (**cash / refined / compound / quest items**), and **cash items can be sold to NPCs — with an extra confirmation warning**. The **warehouse has a maximum slot count** with expansion coupons ("창고의 최대 슬롯 갯수인 %d개를 넘어가므로…"), and ghost-exchange enforces **per-item possession limits** ("소지한도를 초과하였습니다").

**Street-stall mats (client `VisualMatUIParams`):** personal shops render as street stalls with **six selectable stall visuals** — none, **Tiphmont's Begging Mat**, **Seth's Elegant Mat**, **Tiphmont's Fraud Mat**, **Ian's Pauper's Straw Mat (거적대기)**, and the **Tenterion and Baby-Spica character carpets** — the joke shop-front skins for your sidewalk business.

- **Direct trade** window between characters (a listed in-game function).
- **Personal shops (개인상점):** player-run stall shops were a launch-era system — the 2006 Korean official guidebook carries a dedicated personal-shop chapter, and Korean players still shorthand them as **"갠상"** when advising where to buy drills, skins, and gear. Era mechanics (where/how you open one) are thinly documented in surviving sources, but they functioned as the browsing-based player market alongside direct trade.
- **Trade Mail** (see [Mail](32-mail-and-communication.md)): attach an item with a price; the buyer pays on delivery; the seller receives the price minus the mail fee.
- Revival-server marketplaces: OurTrickster's website Auction House/Marketplace (galders or MyShop points) and LifeTO's control-panel marketplace.

## Earning galders

- Selling monster loot to NPCs (weight-limited; see [stats](02-stats-and-base-leveling.md)).
- Galder coupons from Monster Guild quests and event boxes. **500 Galder Coupons are worth stockpiling** — beyond face value they serve as exchange currency and entry fees for specific maps (Korean quest-archive advice).
- Farming sellable equipment: on LifeTO, **gloom equipment** (Path to Caballa Relics, via Mind's Eye) and **phantom equipment** (Phantom Dungeon) are the two named income engines; on the late Korean service, **Otherworld (이계) gear** from the Chaos Tower played the same role.
- The **Black Market** is a secret shop area reached with **Weird Treasure Maps** — every region hides one (except Phantom School, which has no map tier). Four NPCs run it:
  - **Dark Dealer Rat** — sells Sharp / Moon / Art / Artisan / Strong equipment, pouches, and stat-bearing ears and tails; buys items.
  - **Compounder Vin** — compounds old equipment with **Nikarium** into Powerful equipment.
  - **Trader Pav** — exchanges old equipment for **Morph** equipment and upgrades region-set gear with Region Refining Coupons.
  - **Great Chef Sid** — compounds HP/MP potion items from gathered ingredients.
- xTrickster advertises boosted galder drop rates — server-specific tuning.

## Related systems

- [Mail & communication](32-mail-and-communication.md) (Trade Mail)
- [MyShop](22-myshop.md), [Gacha](23-gacha.md), [Recycling](24-recycling.md)
- [Quests](25-quests.md) (coupon rewards)
- [Korean version systems](33-korean-version-systems.md)

## Sources

- [Megalopolis Bank — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Megalopolis_Bank.html)
- [100k / 1 Mil Galder Check — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/1_Mil_Galder_Check.html)
- [Store-More Permit — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Store-More_Permit.html)
- [100 Galder Coupon / 100K Galder Check — Trickster Online Tips blog](http://tricksteronlinetips.blogspot.com/2009/08/trickster-online-items-100-galder.html)
- [New Tricksters' Guide — LifeTO](https://guides.lifeto.co/t/new-tricksters-guide/14) (gloom/phantom farming, marketplace)
- [OurTrickster Online (website marketplace)](https://www.ourtrickster.com/)
- [Functions list — Our Trickster Online Wiki](https://oto.fandom.com/wiki/Episode_Quests)
- [트릭스터 AD 공식 가이드북 — 예스24](https://www.yes24.com/Product/Goods/1394098) (personal-shop chapter)
- [초반에 구매하면 좋은 마이샵템 — arca.live Trickster channel](https://arca.live/b/trickster/107457369) ("갠상" usage)
- [지역별 특산물/퀘스트 아이템 — cyan's Trickster blog](https://livehepa.blogspot.com/2022/02/trickster-online-specialties.html) (coupon stockpiling)
- [Black Market — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Black_Market.html) (four NPCs, Weird Treasure Maps)
- [Megalopolis - Black Market — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Megalopolis_-_Black_Market.html) (Morph equipment, Vin's compounding)
