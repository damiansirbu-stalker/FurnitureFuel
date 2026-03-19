Hideout Furniture Infinite Fuel: No fuel consumption for placeable lights, by Damian
Latest: 1.0.1 (xlibs 1.0.5)

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
Modded exes
xlibs (https://www.moddb.com/mods/stalker-anomaly/addons/xlibs-1001)
Hideout Furniture by Aoldri (provides bind_hf_base.script)

Install (MO2):
1. Install Hideout Furniture by Aoldri
2. Install this mod
3. Must load AFTER Hideout Furniture and any Hideout Furniture patches

Uninstall (MO2):
Disable or remove in MO2.

Compatibility:
Simple file replacement (not DLTX). Overrides bind_light_furniture.script.
Works with Hideout Furniture by Aoldri, SixSloth's & Veerserif's Hideout Furnitures, Even More Hideout Furnitures, Hideout Furniture Expansion, G.A.M.M.A. Light Sources Spawner.

Development:
Source: https://github.com/damiansirbu-stalker/Hideout-Furniture-Infinite-Fuel
Releases: https://github.com/damiansirbu-stalker/Hideout-Furniture-Infinite-Fuel/releases
Original mod by Aoldri. This is a one-line patch.

Versions:

1.0.1
  Added: dependency gate for xlibs version check
  Added: xlibs as explicit requirement (uses xlog)

1.0.0
  First release. Infinite fuel for all placeable lights.
