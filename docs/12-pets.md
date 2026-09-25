# Pets

## Overview

Pets are companions that boost your stats and provide utility. Equipped pets grant passive stat bonuses; special pets add services (auto-drilling, item hunting). Pets carry a **star rating (1–5)** that gates the advanced pet systems:

- **4-star pets** — from MyShop boxes and [Gacha](23-gacha.md) towns.
- **5-star pets** — boss pets, 1st-job character pets, and voice pets.

Pets are typically **bankable but not tradable/droppable** (so they move between your own characters via the bank).

## Pet sub-systems

### Pet Synergy
Merge **two identical pets of the same level** into one stronger pet. Service: **Pet Trainer Shara** (Paradise Shop, Megalopolis Shop, Carbigal Shop); free of charge.
- **4-star synergy:** the synergized pet keeps the main pet's higher stats; for any stat where the assistant pet is higher, the result rolls randomly within the range between the two pets' values.
- **5-star synergy:** the final pet simply takes **the higher of both pets' stats** for every stat (main + assistant).
- You cannot synergy two same pets of different level brackets (e.g. Rook 140 with Rook 240).

### Pet Fusion (appearance)
**Pet Breeder Erin** (Megalopolis Shop) fuses two pets: one provides the **stats**, the other the **image**. Requires **Erin's Secret Book** (MyShop, 1,800 points). The stats pet goes in the yellow slot, the image pet in the blue slot; a preview confirms the result before fusing.

### Pet Item Hunt
Send a pet out to **collect items from a map by itself** — items are randomly drawn from that map's drilling table.
- Only pets with **3, 4, or 5 stars** can hunt; stars determine carry capacity, speed, and find rate. Higher-level pets can hunt higher-level maps.
- Consume a **Pet Rice Ball / Pet Drink / Pet Ice Cream** to start a hunt (the consumable type sets the speed); the number of consumables used caps the items returned.
- You can stay on any map while the pet hunts, but you cannot equip that pet while it is away. Start from the map you want farmed (right-click your character → Pet Item Hunt window).

### Pet Reinforce & Pet Training (Pet Trainer Shara)

**Pet compounding (client `Maturing_CompoundPet`, 88 rows):** pets run on the **same compound engine as equipment** — hardants carry `EnableProperty` + **MinAbility–MaxAbility roll ranges**, `ItemNum` counts, and pet-level gates — 88 pet-compound recipes in the identical format to the equipment master.
- **Pet Training** re-rolls a pet's stats exactly like equipment tempering — fueled by **Protein Candy** (reroll) and **Lock Candy** (lock a stat while rerolling), from MyShop and events.
- **Pet Reinforce** is the pet equivalent of Maturing Compound: pets equip **Hardants** into open **Talent Slots**, each hardant typed to a stat the pet accepts, and slots are consumed like compound slots.

### Pet origins and grades
The pet chart organizes pets by **origin** — In-Game (store/quest/monster-drop), In-Game Event, Gacha, **Egg**, MyShop, MyShop Event, and **Crystal** pets — across level brackets up to 280. The **5-star** class (200+ entries on ggFTW) covers **character pets** (Boxer Lina, Bard Amelie, Card Master Roan, Warrior Bika, Magician Azhi, Inventor Singha, Explorer Zorra, Entertainer Jen — NPC-styled versions of the eight classes, plus Divine variants), **boss pets** (Count Blood, Captain Skull, Admiral Skulley), **voice pets**, and **collaboration pets** (e.g. Akane Isshiki in all four type variants, and the Higurashi pair Ensaki Mion & Shion) — everything eligible for top-tier Synergy. **Egg Pets** are the exception to fixed stats — they grow with you via the Pet Breeding System (see [Egg Shop & Pet Breeding](36-egg-shop-and-pet-breeding.md)).

### Auto-driller pets
**Driller Boy** (Lv 10) / **Driller Girl** (Lv 45) — timed 15-day MyShop pets (2,900 pts; Super versions 3,900 pts / 30 days) that enable automatic drilling (see [Drilling](05-drilling.md)). Timed pets are recharged with **Recharge Coupons** via Pia's Recharge Service (LifeTO excludes Driller pets from recharging).

## Stat pets

**Pet stat structure (client data):** `Pet_Property` (1,161 rows) defines every pet's stat applicability — each pet carries an **ApplyRatio** and up to **10 EnableProperty slots** (which of the twelve stats that pet can raise). The 463 `Pet_*` files around it carry the per-pet blocks; 440 of them have speech tables (see above).

**Pets talk (client data):** the `PetSpeech_*` family holds **440 pet-speech tables** — five speech lines per pet (`Speech0–4`), each paired with a **voice-audio file reference and a trigger ratio** — pets had spoken lines with actual voice clips, fired probabilistically. Angel-family speech tables (Angel, Black Angel, Black Angel Jr., the Hanbok Black Angel) cover the mentor system's mascots too.

Regular pets simply add stats while equipped, e.g. Driller Girl (AP 96, WT 800, DA 6, LK 5, HP 300) or Super Driller Boy (MP 240, MA 11, MD 64, WT 1,280, DA 12, LK 9, HP 240). Pets have 1 compound slot on some servers for Pet Reinforce.

Late-era additions (Korean service): the Chaos Tower overhaul introduced the quest pets **Little Troy** and **Worm**, and Pola's 2013 launch events awarded a **pet exchange ticket** and the **Baby Driller-kun** event pet. Pet nursery **Erin** and pet trainer **Shurin** also staff the Korean Theme Spa (see [Korean version systems](33-korean-version-systems.md)).

## Related systems

- [Gacha](23-gacha.md) and [MyShop](22-myshop.md) — pet sources
- [Guardians](13-guardians.md) — the separate combat-familiar system
- [Drilling](05-drilling.md) — auto-drill pets

## Sources

- [Synergy — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Synergy.html)
- [Trickster Online: Fusing Pets — InspireMari](https://inspiremari.nl/trickster-online-fusing-pets/)
- [Pet Item Hunt — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Pet_Item_Hunt.html)
- [Driller Boy / Driller Girl / Super Driller Boy — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Driller_Boy.html)
- [Paradise Shop — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Paradise_Shop.html) (Shara services)
- [Pet — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Pet.html) (Training candies, Hardants/Talent slots)
- [Pets Chart — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Pets_Chart.html) (stat tables, origins)
- [Category:5 Stars Pet — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Category_5_Stars_Pet.html) (character/boss/voice/collab pets)
- [Pet Synergy — Our Trickster Online Wiki](https://oto.fandom.com/wiki/Pet_Synergy)
