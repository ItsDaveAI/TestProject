# Interface, Controls & HP/MP Recovery

## Overview

The remaining official function-list items: the **client interface and controls** (menus, quickslots, shortcuts, emotes, movement/rest states, equipment and fashion slots) and the **HP/MP recovery system** (potions, natural rest recovery, recovery skills). An in-game **Shortcut Guide** book (from Lifeguard Bean's request) and a **Recovery Guide** book (from Winnie's Request) taught both to new players.

## Interface

**The Notice (노티스) system (client data):** `SystemHelp` (72 entries) is the game's tutorial-notification layer — a companion that pops exclamation-mark guidance, announces mail deliveries ("Megalo Company has dispatched your Lv 15 gift box and the Conchipachi guide by postbox"), points to per-type skill-card vendors, marks key-quest and Crazy-Drilling quest levels, and can be turned off in the Option window (`O`). It doubles as the beginner-warning channel: Lv 21 (EXP protection ends) and Lv 50 (angel eligibility — see [Mentor systems](44-mentor-and-support-systems.md)).

The windows behind the keys above are their own tables: `QuickSlotWindow` (the quickslot bar with its three alternate sets) and `OptionWindow` / `OptionUIParams` / `OptionUITooltip` (the settings window where the Notice toggle lives).

- **Character information**: HP/MP, level, EXP bar, galders, weight.
- **Mini map** (M opens the full world map of Caballa Island).
- **Day/night clock**: hover the minimap to read the in-game time — **1 real hour = 24 in-game hours**, gating night-only content such as Ray's Phantom School entry ([original-era systems](39-original-launch-era-systems.md)).
- **Ring menu**: right-click your own character for the option ring (MyCamp setup, Pet Item Hunt, drilling, etc.).
- **Chat window** toggles All / Party / Whisper / Guild modes.
- **Main menu** windows: Skill, Card, Item, Equipment, MyView (profile), Quest, Party, Guild, Friend, MyShop.
- **Quickslots**: drag items/skills in; **F1–F8** uses them, **1/2/3** switches between three quickslot sets, **T** toggles the window.

## Keyboard shortcuts

**Client-confirmed shortcuts and rest mechanics (tooltips/SystemHelp):** **R** toggles run/walk; **Z or ~** auto-picks dropped items and galders; **V** opens bonus-point allocation on level-up; **D + click** drills. **Sitting or lying down speeds HP/MP regeneration** (sit via PageUp/PageDown or `/앉기`, `/잠`) — but **items can't be used while resting**, and **casting a magic skill while hit cancels the cast** (spell interruption). One-click attack auto-attacks continuously. The world hides one more: the **emergency slide** — click the ground and press **Page Down** to slide (the in-world "비상 미끄럼틀" sign teaches it). No minimap zoom in dungeons; a **level requirement can gate unequipping**; the ammo slot is level-gated; NPC interaction has a click-range; and **detection can fail** ("감별에 실패하였습니다"). The base **level cap is 400** (the Lv-400 achievement message).

| Key | Function | Key | Function |
| --- | --- | --- | --- |
| M | World Map | F | Friends |
| T | Quick Slot toggle | H | Chat Channels |
| 1–3 | Alternate Quick Slot set | Tab | Whisper |
| F1–F8 | Use Quick Slot item | Q | Quest |
| R | Run / Walk | V | Character Profile (MyView) |
| D | Use Drill | E | Equipment Inventory |
| N | Emote Window | I | Item Inventory |
| Y | MyShop (Cash Shop) | C | Card Inventory |
| O | Options | S | Skill / TM Level |
| P | Party | Enter | Chat |
| ` | Pick up item | Alt | Display item names |
| ESC | Settings / Exit | Page Up / Down | **Stand / Sit / Sleep** |

## Equipment & fashion slots

Core equipment slots: **weapon, hat, shield, innerwear, cape, face, ear, tail, accessory, shoe**. On top of these sits a full **fashion layer** with its own slots — Upper Body, Lower Body, Outer Body, Waist, Head, Face, Hand, and Decoration 1/2 — the slot system behind MyShop fashion, [Item Fusion](11-item-fusion.md) skins, and MyCamp dress-up. The item taxonomy also covers drills, pets, cards (skill/star), ores, ammo, gacha coins, and **Galder Piles** (dropped galders as loot).

## HP/MP recovery

- **Potions** (Item Girl): Pink/Blue Potion A (100 HP / 100 MP), B (200), C (500) — HP potions run 15/60/150 g, MP 20/80/200 g.
- **Natural recovery without potions**: the **Stand / Sit / Sleep** states (Page Up/Down) accelerate HP/MP regeneration — the subject of the in-game Recovery Guide ("the basics about recovering HP/MP without using potions"). Sitting and sleeping restore faster than standing.
- **Pets** carry HPR/MPR ratings (recovery ×N times per tick) that stack with rest recovery.
- **Chakra Balance** — a Timer skill dropped by Chaos Tower monsters above the 36th floor (TM 240, prerequisite Chi Sword, mastery 5× Krybeth Card): recovers HP every 2 seconds for 30 seconds (100→800 recovery by level/master), cancelled by moving or casting.

## Related systems

- [Mail & communication](32-mail-and-communication.md) (chat channels, commands)
- [Stats & base leveling](02-stats-and-base-leveling.md) (HP/MP stats)
- [Pets](12-pets.md) (HPR/MPR), [Skills](03-tm-leveling-and-skills.md) (Chakra Balance)

## Sources

- [Game Interface & Controls — LifeTO](https://lifeto.co/game-interface/) (shortcut table, menus, rest states)
- [Shortcut Guide / Recovery Guide — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Recovery_Guide.html) (the in-game teaching books)
- [Chakra Balance — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Chakra_Balance.html) (recovery skill)
- [Items — LifeTO Knowledgebase](https://knowledge.lifeto.co/items) (item-type and slot taxonomy)
- [Merchant Lorena / Paradise Shop — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Merchant_Lorena.html) (potion prices)
