# Maturing Compound

## Overview

Maturing Compounding (usually just "compounding") **adds extra stats to equipment** using compound items and the equipment's open **slots**. Each compounding item has its own **stat range**, the result is heavily luck-based, and the slot is consumed. Service is provided by **Alchemist Nate** (Paradise Shop, Aquarius, and Carbigal Shop).

## How it works

1. Bring equipment with **one or more open slots** that accepts the stat you want to add.
2. Bring a compound item of the desired stat type (e.g. stones, crystals, plants — many drilled or dropped).
3. Nate charges a fee — generally **5× the equipment's value** (MyShop equipment compounds free of charge); the price is shown before confirming.
4. The compound rolls a value within the item's stat range; the slot is then used.

**Level restriction:** the compound item cannot be *above* the equipment's level. Example: Copal is for level-50 equipment — usable on anything Lv 50+, not on lower-level gear. (The reverse — low compound items on high equipment — is fine.)

**Luck:** the formula is unknown; community belief is that **LK** (or DA) has a slight influence, but it is mostly real-world randomness.

## Compound items (per-stat ladders)

Every compoundable stat has its own item ladder (ggFTW's per-stat compound pages: item | level requirement | quantity | stat range, with an elixir-boosted range alongside). The AP ladder as an example:

| Item | Lv. req. | Qty | AP range | Source |
| --- | --- | --- | --- | --- |
| AP Stone | 0 | 5 | +4~16 | Coral Beach monsters |
| AP Magic Stone | 0 | 1 | +6~16 | MyShop (900 pts) |
| Sharp Leg | 0 | 5 | +16~33 | Forest Mantis |
| AP Stone 20 | 20 | 3 | +18~52 | Desert Beach monsters |
| Crow's Claw | 30 | 5 | +30~65 | Crow, Rookie Compound Box |
| AP Stone 50 | 50 | 3 | +42~100 | Forest/Poppuri monsters, Card ID |
| AP Stone 65 | 65 | 3 | +52~122 | Relics monsters, Card ID |
| AP Stone 80 | 80 | 3 | +60~147 | Oops Wharf / Phantom School 1F / Mermaid Palace |
| AP Stone 95 | 95 | 3 | +68~171 | Phantom School 2F, Mermaid paths |
| AP Stone 110 | 110 | 3 | +74~193 | Phantom School 3F / Mirage fields |
| AP Stone 125 | 125 | 3 | +80~215 | School annex / Ghost Blue |
| Whetstone | 130 | 1 | +78~201 | Drilled at Tapasco fields |
| AP Stone 140 | 140 | 3 | +84~235 | Crystal Copper moles / Rose Garden |

Monster-part compounds (Sharp Leg, Crow's Claw, Jackstone, Swamp Shark Teeth, Fresh Bone, Orc's Bat) roll **wider ranges** than the stones of their level. Magic Stones cost 900–1,300 pts by tier; **Compound Elixirs** raise a range's floor and ceiling. The same ladder shape exists for AC/DX, MP/MA/MD, WT/DA/LK, HP/DP/HV, every elemental attribute and resistance, and Critical/Block probability.

## Compoundable stats

- **Basic stats:** AP, AC, DX, MP, MA, MD, WT, DA, LK, HP, DP, HV — all twelve.
- **Elemental attribute and resistance** compounds (attack attributes and elemental resistances).
- **Status probability:** Critical Probability, Block Probability.

## MyShop compound items

| Item | Use |
| --- | --- |
| Magic Stones | Add basic stats |
| Capsules | Add elemental attribute stats |
| Compound Elixirs | Increase an item's maximum/minimum stat range |
| Nate's Bottles | Remove an item from a slot, freeing it for a new compound |

Pet stats can be increased with the parallel **Pet Reinforce** service (see [Pets](12-pets.md)).

## Notes

**Compounder shops (client data):** the `Compounder_*` family (~40 tables) maps the service's full footprint — per-region **compounder spots** (Beach, Relics, Rose, Snow, Swamp, Wharf, Seabed, Mirage, Abyss, Volcano, Techichi, Path/Wharf), special **event compounder shops** (Halloween, Pepero Day, the 9th-anniversary shop, wedding shops 1/2, Tango, Chinese New Year), the **3rd-job compounder shop line** (six pages), the Tartarus compounder — and a **Cuisine spot** (`Compounder_Cuisine_Spot`) with **Hidden-flagged recipes**, confirming secret cooking compounds existed in the official data.

**The recipe format, exactly (client data):** `Compound_Rare` (187 recipes) and `Compound_Potion` (155) define the non-Nate compound economy — each recipe carries up to **3 result items at a result level**, up to **5 request items with counts**, a **Probability (percent)**, a **Fee in galders**, and a **WasteItem** — the byproduct you're left with on failure. One verbatim example: **힘을 주는 반지 ("Strength-granting Ring")** = Addax's Horn ×4 + Steel Fragment ×4 + Crystal ×3 + Gold Ring ×2 + Ampoule ×5, at **30% success, 700 galders fee**. `Compound_Throw` (19) covers the throwing-weapon recipes.

- **Compounder Paul** in Megalopolis Square / Azteca is a separate crafting NPC: he compounds *items* into other items (potions, teas, sticks) rather than stat-slotting equipment — a common point of confusion.
- Poppuri events historically awarded **compounding cost discounts** (e.g. 2 weeks at stage 3).

## Related systems

- [Refinement](08-refinement.md) and [Tempering](10-tempering.md) — the other two equipment modification systems
- [MyShop](22-myshop.md) — elixirs/bottles
- [Pets](12-pets.md) — Pet Reinforce

## Sources

- [Maturing Compound — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Maturing_Compound.html)
- [Mature Compound — PandaTO Wiki](https://pandato.fandom.com/wiki/Mature_Compound)
- [Merchant Lorena — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Merchant_Lorena.html) (Paul's item compounding materials)
- [AP Compound — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/AP_Compound.html) (per-stat compound ladder format, magic stone pricing)
