# Egg Shop & Pet Breeding (Bonus Eggs)

## Overview

The **Egg Shop** is the MyShop **mileage system**, listed on the ggFTW main page as a top-level system alongside MyShop and Gacha: spending MyShop points earns **Bonus Eggs**, which buy Gacha boxes and the game's only **growable pets** — Egg Pets — via the **Pet Breeding System**.

## Bonus Eggs (MyShop mileage)

- Earned at **1 Bonus Egg per 5,000 MyShop points spent**; **Double Egg events** awarded 2 per 5,000 (announced on the official site).
- **Bankable but not tradable/droppable** — eggs move between your own characters only.
- On LifeTO, the **Daily Rewards** spin (once per day per master account/IP) also pays a Bonus Egg plus a random item — a revival-server source for the same currency.

## The Egg Shop (Leonardo)

Exchanged with **Leonardo at Megalopolis Shop** (LifeTO names him Leonard):

| Purchase | Cost |
| --- | --- |
| Gacha-town boxes (Beginner/1–4/Special town boxes, rotating contents) | 5 Bonus Eggs |
| **Egg Pets** (recommended around Lv 60–170) | 10 Bonus Eggs |

(On PandaTO's VIP Egg Shop the 250-egg tier items were never meant to be obtainable.)

## Egg Pets & the Pet Breeding System

Egg Pets are unique among pets: instead of fixed stats, they **level up alongside the player** through the **Pet Breeding System**, run by **Pet Breeder Erin** with **Growth Vitamins**.

- Egg pets come in tiers — **T1 → T4**, plus **VR** variants — e.g. Baby Spicy Dragon, Willow Puppy, Aunty Moon, Assistant Hunter, Apprentice Marx, Shaman Girl Jia, Moon Rabbit, Cheerleader Stella, Maid Minnie, Noxx/Nyxx, Snow Fairy Chris.
- Scale: ggFTW documents **55 hatchable eggs** and **200+ Egg Pets**.
- Erin also handles [Pet Fusion](12-pets.md) (appearance) — the breeding service is her second role.

**The breeding engine is client-confirmed:** Erin's **Growth Vitamins** are the **Pet Growth Vitamin (펫 성장 비타민)** — the single catalyst behind all **483 upgrade rows** of `PetLevelUpInfo` ([Pets](12-pets.md)). The egg-pet tier ladder above (**T1 → T2 → T3 → T4**) is exactly that table's **T-track**, and its **E-track (E1 → E4)** is the egg-pet form-change line — the two tracks of the breeding system in one registry. `PetComposingPresentInfo` (2 rows) gates the hatching present — usable on pets **Lv 1–400**, under both pet-type flags.

## Related systems

- [MyShop](22-myshop.md) — the point spending that generates eggs
- [Pets](12-pets.md) — egg pets in the star/origin taxonomy; Pet Fusion
- [Gacha](23-gacha.md) — the boxes eggs can buy

## Sources

- [Bonus Egg — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Bonus_Egg.html) (mileage rate, Double Egg events)
- [Category:Egg / Category:Egg Pet — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Category_Egg.html) (hatchable eggs, tiered pets)
- [ggFTW Trickster Wiki: Main Page](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Main_Page.html) (Egg Shop as a top-level system)
- [VIP Egg Shop — PandaTO Wiki](https://pandato.fandom.com/wiki/VIP_Egg_Shop) (prices, Pet Breeding with Growth Vitamins)
- [New Tricksters' Guide — LifeTO](https://guides.lifeto.co/t/new-tricksters-guide/14) (daily-reward eggs, Leonard)
- Client data: `PetLevelUpInfo` (the T/E upgrade graph behind egg-pet tiers and evolutions, catalyzed by the Pet Growth Vitamin), `PetComposingPresentInfo`
