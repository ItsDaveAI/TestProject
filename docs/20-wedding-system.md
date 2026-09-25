# Wedding / Couple System

## Overview

The Wedding System launched **June 17, 2010** as a major Ntreev USA content update: two characters (Lv 30+, opposite genders) register as a **couple**, grow **Love Points** together, then complete wedding quests and hold a ceremony with rings, outfits, a hall, and invited guests. Marriage grants a **partner-teleport** ability and special ring abilities.

## Coupling and Love Points

1. Both characters (Lv 30+) go to the **Event Garden** and speak with **Kyu** to register as a couple.
2. Registered couples build **love stats** by playing together: partying (PQs/MQs), sending **memos** and **gifts** to each other, and spending time in a party. Daily status updates and relationship advice arrive while the system tracks progress.

   The client's `CoupleStatusInfo` table gives the **exact point economics** — 11 event types, each adjusting three separate meters (**Relation / Love / Friend points**): positive events pay e.g. **+8 relation, +3 love, +5 friend**, while negative ones claw back −2/−2/−1 — the couple system tracks a friendship axis alongside romance.
3. When Love Points reach the threshold, an in-game notification fires and the **MyView window flashes** — you may begin the wedding quests.

**The couple-stat engine (client couple tables):** the relationship runs on **three separate meters** — Relation, Love, and Friend — where **Love and Friend are each 0–100 scales** and Relation carries **13 descriptor bands** from 처음 만난 듯한 ("like first meeting," 0–5) through 동반자로 여기는 ("regarded as a companion," 96–99) to **영혼의 반쪽 같은 ("like one's other half of the soul," 100)**. The 54-row advice table (`CoupleLoveFriendStringInfo`) prescribes activities by band — party play, party quests, whispers, memos, gifts, and simultaneous play each move a meter, and negative events claw points back (−2/−2/−1 on one event type; another pays +10/+5/−3 — friendship *spent* to buy love). **The couple skill set (client `CoupleDeleteInfo`):** coupling grants a **22-skill set (IDs 5020–5041)** and a five-quest chain (7100–7104) — and **breakup deletes them all**. Divorce rules: the **ring (a skill) is destroyed**, **new bonds blocked for one week**, and **couple skills are unusable while a divorce is in progress**.

## Wedding quests

| NPC | Quest | Notes |
| --- | --- | --- |
| Louis Bitton (Megalopolis Square) | **Pure White** (groom) | 3× Pure White Silk; silk compounded from 5× Pure Silk Thread each, dropped by Loving Torobbie (Lv 35) in **Lovers' Maze** → 2× Pure Wedding Ticket (tradeable) |
| Louis Bitton | **Charming Black** (bride) | Bride's counterpart ticket chain |
| Fusion Master Arlene | **Love Forever** (groom) | Forever Wedding Ticket |
| Fusion Master Arlene | **Promise of Love** (bride) | Promise Wedding Ticket |
| **Kyu** (Event Garden - Ceremonia) | **Two in Harmony** | Turn in the four tickets → choose your **wedding title**, **wedding rings**, and **MyShop outfits** |

## The ceremony

**The officiant's script, verbatim (client `MarriageOfficiateMessage`):** the ceremony runs a scripted service — opening thanks "to the guests who grace this occasion," "today a pair of 선남 선녀 (a fine man and woman) have tied a precious bond," "we are delighted that this precious bond was formed on Caballa Island" — then the **vows**: "신랑은 신부와 영원을 약속하시겠습니까?" ("Groom, do you promise eternity with your bride?") → "네, 약속합니다" ("Yes, I promise") — and the bride's mirror question — closing with the **ring exchange** ("as a token of love, the bride and groom exchange rings"). **Invitation cards** came in three designs (`InvitationCardInfo`): *빛나는 사랑* ("Shining Love"), *귀여운 사랑* ("Cute Love"), and one more — the invitation's visual choices.

- Reserve one of the wedding halls — reached through the **Wedding Hall** hub off Event Garden, with **Megalo Hall** and **Caballa Hall** wings (client `WeddingHallInfo`: exactly two hall zones) — and invite friends to attend. Inside the hall: **Kyu** runs the Wedding Rings & Titles service, **Star Gazer Stella (2)** runs the Wedding Bulletin Board, and Tuxedo T's shop sells **Heart Spring** and **Angel's / Fairy's Fireworks** (10,000 g each) for the ceremony.
- After the wedding, the couple gains the ability to **teleport to wherever their partner is located**.

**Wedding rings (client data):** `WeddingRingInfo` defines **11 rings, each granting gendered skills** — every ring carries a `SkillIdMale` and a `SkillIdFemale`, so husband and wife receive *different* abilities from the same ring.

**Wedding dresses (client data):** `WeddingDressInfo` defines **16 dress items, each with separate male and female dress designs** (DressMale / DressFemale per item) — outfits are couple-paired, not unisex.

**Wedding-exchange recipes (client `ExchangeMarriage`, 27 entries):** the wedding economy had its own exchange counter — 27 recipes trading result items for request items (the ceremony goods, outfits, and ring materials) inside the general exchange framework ([Wandering Exchange NPCs](40-wandering-exchange-npcs.md)).

**Couple titles (client `MarriageTitleInfo`, 21 templates):** marriage grants **prefix titles carrying the partner's name** — *천상까지 %s의 연인* ("%s's lover to the heavens"), *사랑의 열병 속 %s의* ("%s's, in love's fever"), *%s의 절친한 연인* ("%s's dearest lover"), *%s만 바라보는* ("looking only at %s"), *%s 뿐인* ("%s's one and only"), *%s 달링* ("%s darling") — the Couple title family of the [title system](28-chaos-tower.md), rendered with your partner's name.
- The **rings** chosen during the quest grant further special abilities.
- Ntreev marked the launch with a Wedding Screenshot Forum Event: the 5 best hall screenshots won 3 Gacha Coins and a GM-signed wedding illustration poster.

## The marriage meta (community guides)

**Why marry (the three real benefits, per the Korean community):**

- **Love Crazy Drilling (러브 크레이지 발굴, "럽크발")** — with your partner **on the same field**, the Crazy Drill jackpot fires almost constantly (hearts pop while you drill); it even triggers while the partner lies dead on the same map. A Fox's 1st-job passive extends the duration, and a higher Crazy Drill stage lengthens it — Fox × spouse is the drill-meta's core combo.
- **Couple teleport (결혼 텔레포트, "결텔")** — a **no-cooldown teleport to your partner**, used to park an alt on a farming map and hop back and forth (dual-client players alt-tab both teleports at once to swap positions). It cannot penetrate the Theme Spa's 4th floor or the Chaos Tower interior.
- **Cash wedding rings** — using the ring skill on your partner grants **LK +10% for 120 seconds** (cash dresses are looks-only).

**Requirements:** both characters **Lv 30+**, an **opposite-gender pair** (male/male and female/female impossible), both online — hence the standard advice to marry your own alt on a second client.

**The quest chain in practice (Korean walkthrough):** Kyu sends the pair to **Baron Andrew (앙드레 남작)** at the Megalopolis fountain — the **Love's Maze (사랑의 미로)**, where **Star-Gazing Byeolhui random-teleports you for 2,000 galders per hop** until you land on monster/drill rooms; the **groom** collects white-silk threads (5 threads → 1 white silk ×3) from Love's Bunnies and the **bride** charm silk from Love's Tottocchi, each quest paying 2 Wedding Tickets. **Artisan Araine (금속공예사 아레인)** in Megalopolis Shop runs the ring half the same way — 5 ores → 1 Eternal Metal (groom) / Promise Metal (bride) ×3, 2 Ring Tickets each — and **the couple swap one of each ticket** before returning to Kyu.

**The ceremony's fine print:** the reservation board supports **private weddings by password**; **book the Megalo Hall — ceremonies started in Caballa Hall never begin (era bug)**; up to **100 guests** register through the board; the rite **auto-starts 5 minutes** after entry; if either newlywed leaves the hall, **everyone is ejected**; hosts can expel unwanted guests.

**Title churn:** couple titles rotate at noon and midnight as you play together — unhappy with yours, the community's remedy is breaking the couple (instant, free) and re-forming; **divorce** after the wedding is the 7-day-blocked version above.

## The marriage office (client dialog scripts)

The couple/marriage service hub NPC (wandering NPC295 of the northeast path) speaks the full ruleset in data:

- **Forming a couple (`MakeCouple`):** "to escape solo life, tell me you'll form a couple and designate the partner you like — **I'll convey your heart with this arrow of love and peace**. If they refuse, nothing can be done — but that's still better than never trying and spending your life in love with a PC monitor."
- **Divorce (`BrokenMarriage`), the complete rule:** "**divorce requires the partner's consent** — I deliver the consent message, and a refusal blocks it. **If the partner doesn't answer for one month, the divorce proceeds anyway.** On divorce you **return the wedding ring, the title, every anniversary gift received so far, and the Love-Love Big Bang mode**, and **cannot form a new couple for 7 days**."
- The office also runs **`BrokenCouple`** (uncoupling), **`ExchangeMarriage`** (the wedding-goods picker — items gated by date count, "the choosing partner brings the set of two"), **`CheckMarriageOption`** (marriage preparation), and the **`OpenMarriageBoard`** marriage-promotion bulletin board — plus the wedding-hall teleport.

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
- [결혼은 왜 하는 게 좋고, 어떻게 하는가? — arca.live 트릭스터 채널 (레이븐우드)](https://arca.live/b/trickster/116952961) (Love Crazy Drill, couple teleport, quest chain, Megalo-Hall bug)
- [트릭스터 결혼하기 / 이혼하는방법 — 네이버 블로그 솔라 (2019)](https://m.blog.naver.com/dara77/221574003173) (full ceremony walkthrough, 100-guest cap, ticket swap)
