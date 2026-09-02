# Nuzlocke

An enforced, deeply configurable Nuzlocke for Gen1Recomp. The rules are not a
promise you make to yourself — the mod holds you to them, and it tracks the
whole run while it does.

Red, Blue and Yellow are the mature baseline. Gold and Silver are beta targets,
Crystal is alpha. Support in one edition is never treated as proof for another.

## What it enforces

- **Permanent death.** A fainted party member dies and is removed.
- **One catch per area**, with Failed Encounters and configurable Dupes modes.
- **Mandatory nicknames**, Shiny Clause, and escape restrictions.
- **Level caps** and difficulty profiles.
- **Species restrictions** — Type Locke, Colorlocke, Alphabetlocke, PKMN BAN,
  maximum BST, legendary/glitch classification. Each can be off, deterministically
  random for the run, or chosen.
- **Item, healing, service and economy restrictions**, plus party/team limits.
- **Special acquisition policy.** Gifts, fossils, prizes and NPC trades each
  independently consume the area's slot (AREA) or keep provenance without it
  (BONUS).

## What it tracks

Encounter tracking, durable Run History v2, and translated **Graveyard** and
**Almanac / Run Recap** viewers under the NUZ MENU. There's an explicit
END RUN / ABANDON RUN lifecycle, and Forgiveness / F. TOKEN support if you want
a run to survive one mistake.

## Randomizer

Ten independently resolved subsystems: Starter, Encounters, Field Items,
Learnsets, Trainers, Evolutions, Shops, TM Contents, TM Locations and Gift
Items. Mappings are deterministic (algorithm v1) against persisted source
identities. Gen-II Random Trainers and Gen-II Random Field Items currently have
tester-reported runtime failures and are not claimed as working.

## Install

1. Download the newest `nuzlocke` zip from the
   [releases page](https://github.com/Stone696/nuzlocke/releases).
2. In the launcher: MODS → **Import mod .zip**.
3. Enable it and start a new game — the ruleset keys off Slow Start.

The manifest sets `"github": "Stone696/nuzlocke"`, so the launcher's **Update**
and **Versions** buttons handle it from there.

## Compatibility

- Mod API 2, engine `>=0.2.24 <2.0.0`.
- `content` profile, loads late (`priority: 100`) so it sees other mods'
  party changes. Declares `engine_internals`: it patches battle and party
  handling to make death stick.
- Compatibility is ownership-based — it prefers public hooks and provider
  contracts, and stands down where another mod legitimately owns a mechanic
  (external shiny providers, replacement bag/party UIs, and so on).
- **Kanto Ascendant** is an explicit conflict; don't run it with standalone
  Nuzlocke.
- Reviewed targets and evidence levels are documented in the repo's
  `docs/COMPATIBILITY.md` and `docs/FEATURE_CONFIDENCE.md`.

## Credits

Originally created by **bryanthaboi**. **Stone696** is the current maintainer
and has taken it far past the original — continued development, the challenge
rule catalog, the randomizer, compatibility work and all current releases.
Shiny support traces back to **masterwebx**'s original Shiny Pokémon mod.
