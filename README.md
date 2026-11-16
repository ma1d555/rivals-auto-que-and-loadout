# Rivals auto-queue + auto-loadout

Queues your chosen mode when you're in the lobby and picks your loadout when the weapon picker opens.

## Load it

Put this in your executor (all settings optional):

```lua
getgenv().RivalsQueueLoadoutConfig = {
    AutoQueue = true,
    AutoLoadout = true,
    Queue = "5s",            -- "1s" / "2s" / "3s" / "4s" / "5s"
    Primary = "Shotgun",
    Secondary = "Uzi",
    Melee = "Fists",
    Utility = "Grenade",
}
loadstring(game:HttpGet("https://raw.githubusercontent.com/ma1d555/rivals-auto-que-and-loadout/main/main"))()
```

The script waits until Rivals' lobby, weapon picker or results screen is usable before it starts. Running it again replaces the
running copy.

## Weapon names

Use the base weapon name (not a skin name), and put it in the slot it belongs to in the game:

Assault Rifle, Bow, Burst Rifle, Chainsaw, RPG, Exogun, Fists, Flamethrower, Flare Gun, Freeze Ray, Grenade,
Grenade Launcher, Handgun, Katana, Minigun, Paintball Gun, Revolver, Slingshot, Subspace Tripmine, Uzi, Sniper, Knife,
Shotgun, Crossbow, Daggers, Distortion, Energy Rifle, Energy Pistols, Gunblade, Battle Axe, Riot Shield, Scythe, Trowel,
Medkit, Molotov, Satchel, Smoke Grenade, War Horn, Warpstone, Flashbang, Jump Pad, Warper, Wildcat

The panel only cycles through weapons that are in that slot in the live game, so it's the easiest way to see which slot a
weapon is in. A misspelled or wrong-slot weapon is rejected rather than sending a wrong loadout.

## Notes

- Rivals only takes a loadout in its weapon picker, at the start of a match. A change made mid-match is saved and sent at
  the next pick.
- Other scripts can switch it on and off live: `getgenv().RivalsQueueLoadout.autoQueue = false`. The panel's switches follow.
- Toasts are shared through `getgenv().toast(title, text, { color, image, duration })`.
