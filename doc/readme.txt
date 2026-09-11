FurnitureFuel: No fuel consumption for placeable lights, by Damian
Version: next (xlibs 1.5.1, demonized 20250908)
GitHub: https://github.com/damiansirbu-stalker/FurnitureFuel
Changelog: https://github.com/damiansirbu-stalker/FurnitureFuel/blob/main/doc/changelog

Alife Collection:
AlifeAmbience: https://github.com/damiansirbu-stalker/AlifeAmbience
AlifeBalance: https://www.moddb.com/mods/stalker-anomaly/addons/alifebalance
AlifeCompanions: https://github.com/damiansirbu-stalker/AlifeCompanions
AlifeDiegetic: https://www.moddb.com/mods/stalker-anomaly/addons/diegetic-audio-control-100
AlifeGuard: https://www.moddb.com/mods/stalker-anomaly/addons/alifeguard-1001
AlifePlus: https://www.moddb.com/mods/stalker-anomaly/addons/alifeplus-v1-0-01
AlifeSpooks: https://github.com/damiansirbu-stalker/AlifeSpooks
AlifeTactics: https://www.moddb.com/mods/stalker-anomaly/addons/alifetactics
FurnitureFuel: https://github.com/damiansirbu-stalker/FurnitureFuel
JitProfiler: https://github.com/damiansirbu-stalker/JitProfiler
TestZone: https://github.com/damiansirbu-stalker/TestZone
xlibs: https://www.moddb.com/mods/stalker-anomaly/addons/xlibs-1001

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
Modded exes: themrdemonized 2025.9.10 or newer, or AOEngine v0.55 or newer. The full feature set needs the latest demonized build; a feature that needs a newer one stays inactive on older exes.
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

Performance:
Performance comes first, ahead of any feature. When a feature cannot fit the budget it is reworked, replaced, or removed with an X-Ray engine modification rather than allowed to slow the game. Measured on the engine built from the latest source with no multithreading and no optimizations, so the timings are worst-case; the optimized multithreaded build you run is always faster.

Development:
Original mod by Aoldri. This is a one-line patch.

Credits:
Altogolik - support, ideas, source materials

Usage and License:
  Modpacks: allowed and encouraged. Keep the readme and license files.
  Addons, patches, integrations: allowed. Credit "FurnitureFuel by Damian Sirbu" visibly on your mod page.
  Reproducing the implementation in other software: not allowed, even with credit.
  Full license in LICENSE file and on GitHub.

Diagnostics and reporting:
Report at https://github.com/damiansirbu-stalker/FurnitureFuel/issues/new/choose or the EFP, Anomaly, and Zona Discord. Include repro steps, engine build, modlist, load order, and xray.log.
