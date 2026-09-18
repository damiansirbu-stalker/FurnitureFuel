FurnitureFuel: No fuel consumption for placeable lights, by Damian
Version: 1.0.4-snapshot (xlibs 1.5.1, demonized 20250908)
Changelog: https://github.com/damiansirbu-stalker/FurnitureFuel/blob/main/doc/changelog

My work:
GitHub: https://github.com/orgs/damiansirbu-stalker/repositories
ModDB: https://www.moddb.com/members/damian-sirbu/addons
Nexus: https://www.nexusmods.com/profile/damiansirbu/mods

My contributions:
X-Ray Monolith: https://github.com/themrdemonized/xray-monolith

Removes fuel and battery consumption from all placeable light furniture.
Lights no longer require batteries, kerosene, or gauss ammo to operate.

One script change: bind_light_furniture.script line 88, self.infinite_fuel = true instead of checking world object status.
All visual effects, sounds, flickering, and toggle behavior are preserved.

Features:

Affected items:
  Metal Torch (was: batteries_dead, 800h)
  Gas Lamp (was: kerosene, 1200h)
  Gas Lamp GAMMA variant (was: kerosene, 99999h)
  Light Altar (was: ammo_gauss, 2400h)

All other furniture (workshop, radio, displays, stashes) does not consume fuel and is unaffected.

Requirements:
Anomaly 1.5.3
Modded exes: themrdemonized 20250908 or newer, or AOEngine v0.55 or newer. The full feature set needs the latest demonized build. A feature that needs a newer one stays inactive on older exes.
xlibs (https://www.moddb.com/mods/stalker-anomaly/addons/xlibs-1001)
Hideout Furniture by Aoldri (provides bind_hf_base.script)

Install (MO2):
1. Install Hideout Furniture by Aoldri
2. Install this mod
3. Must load AFTER Hideout Furniture and any Hideout Furniture patches

Uninstall (MO2):
Disable or remove in MO2.

Compatibility:
Coexists with Hideout Furniture (Aoldri), SixSloth's & Veerserif's Hideout Furnitures, Even More Hideout Furnitures, Hideout Furniture Expansion, and G.A.M.M.A. Light Sources Spawner.
- Conflicts: any mod that also overrides bind_light_furniture.script (this is a full-file replacement, not DLTX).

How It's Built:

Although it started from work by Demonized, Alundaio, and Tronex, the current code and patterns are original, learned through reverse-engineering X-Ray, load testing, and custom X-Ray changes.
The design favors the engine's own mechanisms and minimal intervention, with event-native pub/sub over polling.
Work spreads across frames through deferred queues and rate limiters, while per-level caches replace world scans.
The raycasting and range math are hand-written and tested live, and the code follows the engine's own standards and flags.
Performance is the first invariant. Every flow stays under 2ms, and the build rewrites or drops anything that misses.
Profiled continuously with JitProfiler, an engine-native scientific tool. Manual tests run on unoptimized, single-threaded exes.
The code carries tracing and monitoring from the ground up, with every flow timed off the log level.
Every commit runs the full pipeline locally and in CI: luacheck, a Selene build compiled for STALKER with flags the public build lacks, and a load test that runs every script against engine stubs.
Rule layers then check crash safety, hotpath cost, engine correctness, complexity, architecture contracts, security, and the docs.
Every mod is configurable through MCM or LTX, down to each rate, threshold, and toggle, with nothing tunable left hard-coded.
The mod avoids writing engine values, holding its own state in parallel. Any value it must change stays inside the engine's own bounds, so save corruption is impossible.
It depends on no other mod, not even my own. The only shared layers are X-Ray and xlibs.

[Screenshot: FurnitureFuel under JitProfiler, a live CPU and allocation capture]
Project Health: https://damiansirbu-stalker.github.io/FurnitureFuel/

Credits:
Original Hideout Furniture mod by Aoldri.
Altogolik - support, ideas, source materials

Usage and License:
  Modpacks: allowed and encouraged. Keep the readme and license files.
  Addons, patches, integrations: allowed. Credit "FurnitureFuel by Damian Sirbu" visibly on your mod page.
  Reproducing the implementation in other software: not allowed, even with credit.
  Full license in LICENSE file and on GitHub.

Diagnostics and reporting:
Report at https://github.com/damiansirbu-stalker/FurnitureFuel/issues/new/choose or the EFP, Anomaly, and Zona Discord. Include repro steps, engine build, modlist, load order, xray.log, and the debug log.
