# Mentor, Comeback & Character Services (client-data systems)

## Overview

The Korean client's data tables reveal a layer of **player-support systems** that never made it into the English wikis: a mentor system with summonable "angels," a character-freezing Time Capsule, comeback gifts for returning players, beginner death protection, and paid character services. This file documents them from the client's own XML tables (the AngelUIParams / AngelSystemStrings / TimeCapsuleStrings / SleepUserReward_Strings / BeginnerRebirthInfo / Item_RebirthParam / ChangeCharNameUIParams / ChangeHairUIParams families).

## The Angel System (천사 시스템) — mentor summoning

A mentor system pairing beginners with volunteer helpers:

- **Beginners** (marked with a beginner indicator) get an **angel list** UI: call a new angel, request help from a listed one, or dismiss them from memory ("기억에서 지우기").
- **Summoning an angel teleports the mentor to the beginner** ("천사(%s)님이 오시고 계십니다" — "Angel %s is on the way"). Some zones refuse summons; the request is cancelled if the beginner is in a non-summonable area.
- **Matching and conduct (`AngelUIParams`):** calling a *new* angel scans online veterans and **auto-cancels after 30 seconds** of no response; the bad-manner report carries a **24-character reason** and the reporting angel is erased from your memory; **report count restricts the beginner's angel usage**; and after helping, **the angel is returned to their original location**. Veterans toggle eligibility with the **`/천사` (angel) command** — `/천사 on` / `/천사 off`.
- **Cooldowns:** the same angel can be called only once per **5 minutes**; an angel busy with another beginner can't be reached for **30 minutes**; an angel can remove themselves from a beginner's list entirely.
- **Graduation:** when the beginner stops being a beginner, the list and mark disappear ("졸업 축하합니다!") and the angel receives a **wing mark for one week** as thanks ("저 졸업했어요!!").
- **Manner enforcement:** angels can flag a beginner as a **bad-manner user**, restricting their system use for **5–30 minutes** depending on severity.
- Angel-themed **pets** exist in the same data (PetSpeech_Angel, Black Angel, Black Angel Jr., a Hanbok Black Angel).

## Time Capsule (타임캡슐) — character freezing

A character-archival system that **stops a character's time flow**:

- Putting a character into the capsule requires **leaving any guild first** ("길드를 탈퇴하시고 타임캡슐에 넣어주세요").
- The service **consumes 1 Time Capsule ticket** per use, and the character stays preserved **until you choose to open it** (no decay timer on storage).
- On extraction, time resumes — but **friends, guild information, and MyCamp layout are not preserved**, and a **name collision** (someone took the name while frozen) forces a rename.
- A level requirement gates the capsule (level mismatch is rejected).

## Sleep-User Rewards (휴면 유저 보상) — comeback gifts

On returning after a long absence, the **Megalo Company welcome-back screen** appears: "오랜만에 오셨군요!" — a **return gift is deposited into MyShop**. The form also asks for **the name of a friend who missed you**; naming one sends them a gift too ("그 친구께도 좋은 선물을 드리고자 합니다"), with a "receive later" option.

## Beginner protection & rebirth restoration

- **BeginnerRebirthInfo:** below **Lv 20**, death restores **100% of HP, MP, base EXP, and TM EXP** — the documented beginner safety net.
- **Item_RebirthParam:** MyShop restoration items for above that line, each with per-field ratios — e.g. one restores 20% HP/MP but **80% of lost EXP and TM**; another restores 50% across the board.

## Character services (paid)

- **Character rename** and **hair recolor** services (ChangeCharNameUIParams / ChangeHairUIParams) — the MyShop counterpart of the free creation-time choices.

## Related systems

- [Drilling](05-drilling.md) — the drill stress/gauge system runs on similar client tables
- [Recycling](24-recycling.md) — the VIP exchange shop's recycle points
- [Skins & fashion](38-skins-and-fashion-economy.md) — hair dye rules

## Sources

- Trickster Online Korean client data tables (user-provided `xml.zip`, 2026-09): `AngelSystemStrings.xml`, `AngelUIParams.xml`, `TimeCapsuleStrings.xml` / `TimeCapsuleUIParams.xml`, `SleepUserReward_Strings.xml`, `BeginnerRebirthInfo.xml`, `Item_RebirthParam.xml`, `ChangeCharNameUIParams.xml`, `ChangeHairUIParams.xml`, `PetSpeech_Angel*.xml`
