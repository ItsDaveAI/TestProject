# Fiesta Zones

## Overview

Fiesta Zones are **timed party-grinding maps** with big EXP/TM bonuses — the "Fiesta Renewal" system. Ten zones bracket the level range up to 400; each opens on a fixed schedule and admits a player **twice per day** using a **Fiesta Ticket**.

## How it works

1. The zone opens **every 2 hours** at fixed times (announced in-game: "The Fiesta Ticket is needed to enter the Waiting Room.").
2. Click your **Fiesta Ticket** (consumed) → teleports you to your level bracket's **Waiting Room** (has an Item Girl general shop) for ~5 minutes of preparation.
3. Announcement: "The Fiesta has started!" — the **Ball Room** portal unlocks. The Ball Room contains non-active monsters (**Merrymakers**).
4. After 5 more minutes the **Grand Ball Room** portal appears — filled with active monsters (**Revellers**). You have exactly **20 minutes** to kill as much as possible under the zone's EXP/TM bonuses.
5. When time is up you are teleported back to wherever you were before using the ticket.

## The zones (1–6 documented; 10 total)

| Zone | Level bracket | Bonus | Merrymaker / Reveller |
| --- | --- | --- | --- |
| 1 — Cora Alert | 21–59 | EXP +50% / TM +300% | Cora (Lv 30) / Cora (Lv 60) |
| 2 — Sand Alert | 60–89 | EXP +100% / TM +400% | Sand Demon (Lv 70) / Sand Demon (Lv 90) |
| 3 — Cucool Alert | 90–119 | EXP +250% / TM +500% | Cucool (Lv 100) / Cucool (Lv 120) |
| 4 — Skull Alert | 120–149 | EXP +300% / TM +600% | Raver Skeleton (Lv 130) / Raver Skeleton (Lv 150) |
| 5 — Jelly Fish Alert | 150–179 | EXP +450% / TM +700% | Jellyfish (Lv 160) / Jellyfish (Lv 180) |
| 6 — Mask Alert | 180–219 | EXP +500% / TM +800% | Mask monsters (Lv 190/210+) |

(Zones 7–10 continue the pattern toward Lv 400 per the Fiesta overview — "10 Fiesta Zones divided in brackets over 400 levels.")

## Notes

**The scheduling engine (client data):** `FiestaInfo` holds **240 fiesta instances** — each row binding a zone ID, **portal index and portal-open minute**, and activation windows (year/month/day/hour) with working-day masks — the daily fiesta calendar is a timed-portal script, the same scheduling machinery as the event-drop timers ([Events](30-events.md)).

- The TM multipliers are the draw: Fiesta is one of the fastest TM-leveling methods, pairing with the [party system](17-party-system.md)'s multipliers.
- A **Fiesta Party** variant coordinates group entry (party-wide ticket use).

## Fiesta Party events

The **Fiesta Party / Winter Fiesta Party** events (Dec 21, 2011 – Jan 18, 2012, and May 8–23, 2012) dressed the zones for the holidays: a **Fiesta Ticket arrived in your MyShop inventory at first login each day**, the zone opened twice daily for 20 minutes each, and monsters dropped **Fiesta Marbles** at a low rate — exchanged at **Heidi** in the waiting room for a TTX Pet 60 (15 marbles), Fiesta Gift Box A (5 marbles), and the Jasmine bouquet / hair pin / shield (3 marbles each).

## Related systems

- [Party system](17-party-system.md)
- [TM leveling](03-tm-leveling-and-skills.md)
- [Events](30-events.md) (EXP/TM boost weeks stack conceptually)

## Sources

- [Fiesta — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Fiesta.html)
- [Fiesta Party — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Fiesta_Party.html) (marble exchange, daily tickets)
- [Fiesta Party — ggFTW Trickster Wiki](https://wikimirror.lifeto.co/wiki.ggftw.com/trickster/Fiesta_Party.html)
- [Fiesta Zone — Our Trickster Online Wiki](https://oto.fandom.com/wiki/Fiesta_Zone)
