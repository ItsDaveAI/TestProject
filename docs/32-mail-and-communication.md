# Mail & Communication

## Overview

Trickster's social infrastructure: an in-game **mail system** with item/galder attachments and trade-by-mail, a **friend list**, **memos**, chat channels, and a rich set of slash commands. All are client-native functions of the official service.

## Mail system

Open mail via the envelope icon (top-left, below HP/MP), the Mail icon in the bottom bar (between Friend and MyShop), or press **A** (QWERTY) / **Q** (AZERTY). Three sections:

- **Mailing List** — letters sent (red arrow; showing the recipient's name until read, then your own) and received (blue arrow; unread highlighted). The envelope counter shows unread mail; recipients see new mail on map change or relog.
- **Compose** — title, recipient (or pick from your friend list by right-clicking), and a message up to **300 characters**. You may attach **an item and/or galders**:
  - Galder-only: fee of **500 g** for amounts 1–500,000; above that, 0.1% of the amount (e.g. 1,000 g per million).
  - Item: flat **500 g** fee; item + galder costs the galder fee plus an extra 10 g.
- **Trade Mail** — attach an item and set its price; the buyer pays on opening, and you receive a receipt with the money (minus the mail fee). The core async selling mechanism (see [Economy](31-economy-bank-trade.md)).
- **System Mail** — where level-up gift boxes and important quest letters arrive (Nefertiti's, **Eclipse's Message** at Lv 180, the Questionable Letter, D's Letter, 3rd Job Guide at Lv 120 — delivered via the MyShop inventory).

## Friend list

- Add via right-click → friend functions, or commands `/add`, `/friendadd [player]`.
- `/fellowlist` shows whose friend list you are on; `/fellowdelete [player]` removes you from someone's list (takes effect when they log off).

## Memos

- `/memo [player] [message]` — short direct message (apostrophes break memos).
- Guild notices: `/$memo [message]` — masters/leaders leave a notice the whole guild reads on login.

## Chat & channels

- Chat window with tabs (Alt+1–4 to switch); **Ctrl+0–9** sends registered messages (set with `/register [#]`).
- Custom channels: `/join` or `/chjoin [channel]`, `/chquit`, `/chlist`; speak in a channel with `&[channel] [message]` (channel text appears cyan).
- `/block [player]` mutes/unmutes; `/blocklist` lists muted players.
- Pet name color codes: `^[R` / `^[M` / `^[B` / `^[W` / `^[Y` / `^[O` / `^[C` / `^[G` prefixing name segments colors the name (e.g. `^[RName`).
- Other client commands: `/help` (command list), `/hideme on|off` (hide own character locally), `/freecamera on|off` (far zoom-out), `/invite` (party), `/kick`, `/quit` (leave party).

## Related systems

- [Wedding system](20-wedding-system.md) — memos and gifts build Love Points
- [Economy](31-economy-bank-trade.md) — Trade Mail
- [Party](17-party-system.md) & [Guild](18-guild-system.md) — /invite, /$memo

## Sources

- [Mail — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Mail.html)
- [Chat Commands — Cursed guild forum (Piety, 2010)](https://cursed.forumotion.com/t175-chat-commands)
- [Controls and Secret Controls — MewsiEPTO Wiki](https://mewsie.world/epTOWiki/index.php/Controls_and_Secret_Controls)
- [Functions list — Our Trickster Online Wiki](https://oto.fandom.com/wiki/Episode_Quests)
