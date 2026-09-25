# Card Battle

## Overview

The Card Battling System is one of Trickster's defining non-combat systems: two characters duel with **collectible card items** found during normal gameplay (mainly as monster drops). Battles award EXP, points, galders, and items. Card Battle is also a route to level up outside grinding.

## Obtaining cards

- **Each monster drops a card of its type.** Character Cards come from quests; Neutral Monster Cards come from monster-hunting quests and NPC quests.

**Card collection sets (client data):** beyond battling, cards feed a **collection-bonus layer** — `Card_SpecialSet` defines **37 themed card sets**, each a named combination of up to **5 specific monster cards at a grade** (e.g. *테치치의 혼령* "Spirits of Techichi", grade 14 = cards 24019 + 24119 + 24217) paying up to **4 present items at set rates** (20% / 20% …) when assembled. The in-game card **album books** (the `Item_BookParamExt` book-UI family, with its own count/Life display strings) are where sets are registered — collecting lines of the island's monsters, not just battling with them.
- Card categories: **Power / Magic / Sense / Charm / Neutral** monster cards, plus **Character, Skill, and Etc. cards**.
- Cards have a **rank (1–15)** and an **MP value**; cards of extreme rank (close to 1 or 15) are generally preferred.

## Starting a game

- Right-click another player who has agreed to battle and choose **Card Battle** (they receive an invitation to accept or decline), or
- Type `/card (game name)` and wait for players to click to join.

## Rules

**Deck construction:** each side picks **5 cards** — at most 2 of any type, at most 2 of any rank, and at most **1 Neutral card**. The first two chosen cards are turned face-down so the opponent can't see them.

**The two rule sets** (the challenged player, or the previous round's loser, picks):

| Rule set | Card types match | Card types differ |
| --- | --- | --- |
| **Don Giovanni** (young vice president) | Higher rank wins | Lower rank wins |
| **Don Cavalier** (elder gentleman) | Lower rank wins | Higher rank wins |

**Common rules:**
- If the two played cards' ranks match, the card with the **higher MP** wins; equal MP is a tie and neither side gets the win.
- If time runs out, choices are made randomly.

**Gameplay:**
- Each of 4 plays: both players choose a card; cards are revealed; the winner gains a win + points, the loser loses points.
- **Chance button:** if the opponent is ahead and you hold your Neutral card, you can play it on a Chance — if it wins you take the round win **plus one of the opponent's wins**; if it loses, the Neutral card is forfeited to the opponent at round end.
- Ending conditions: if wins are equal after 4 plays, the fifth cards are played; if the fifth cards are equal in rank and MP, random cards are played until someone wins. Ties trigger extra rounds with remaining/new cards until a winner is declared.

## Rewards

**Reward caps (client `CardBattleStrings`):** three anti-farming limits governed card EXP — **repeat battles against the same opponent stop paying EXP/points** past a threshold, a **daily unique-opponent cap** limits rewarded opponents per day, and **consecutive rematches are capped** ("%d consecutive plays max"). One physical rule: **your inventory must hold ≤288 items to battle at all** — a full pack locks the minigame.

- The battle winner earns **experience points proportional to points won** — more wins and points means more EXP.
- Additional prizes: **items, cards, and galders**.

## Card combos

Certain card pairs/triples/quads form named **combos** with score multipliers when played together:

- 2-card examples: *Power Type* (Bunny + Buffalo, ×1.175), *Charm Type* (Cat + Raccoon, ×1.175), *Harpy Sisters* (Nephthys + Isis, ×1.100), *Healthful Couple* (Mandragondra + Simbatta, ×1.100)
- 3-card examples: *Insect Empire* (Forest Mantis + Forest Tickler + Forest Wasp, ×1.175), *Ruler of IceBerg* (Queen Odinea + Snow Lady + Icicler), *Vamp Servant* (Count Blood + Maid Lydia + Mr. Freaks)
- 4-card examples: *Bear Family* (Bug Bear + Goma + Polar Bear + Santa Bear)

## The ranked ladder (client UI data)

Card Battle kept a **persistent per-player record** (`CardBattleUIParams`): the battle window shows each player's **Lv, win count, loss count, battle points, grade, and accumulated galders/EXP** — and the server runs a **Card Battle Rank board** (`CardBattleRankUIParams`) with four record categories: **most wins (최다승리), highest points (최고포인트), most matches (최다전적), and best win rate (최고승률)** — rank, grade, and type per entry. The lobby QoL: **auto-select (자동선택)** for deck picking, an **exit reservation** ("나가기 예약") that queues your departure after the current battle, and a final-battle display. Card selection tabs split the five card families — Attack / Magic / Sense / Charm / Neutral.

## Related systems

- [Card Identification](07-card-identification.md) (hidden secret cards)
- [Quests](25-quests.md) (Card Girl card-collection quests)

## Sources

- [Card Battle — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Card_Battle.html)
- [Card Combo — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Card_Combo.html)
- [Trickster Online: Card Battle — InspireMari](https://inspiremari.nl/trickster-online-card-battle/)
- [Trickster Online Peek #3 — IGN (June 2008)](https://www.ign.com/articles/2008/06/26/trickster-online-peek-3)
- Client data: `CardBattleUIParams` (per-player record: wins/losses/points/grade/galders/EXP, auto-select, exit reservation), `CardBattleRankUIParams` (four-category rank board)
