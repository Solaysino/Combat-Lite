# Combat Lite

Client-side defensive combat routine designed specifically for "bug fixes" by captainwoodlegs (Roblox place ID: 100971017807798). Provides automatic parrying, 360-degree radial threat intercept, and guard-break evasion for Luau execution environments without modifying player controls, camera angles, or movement kinematics.

## Execution

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/Solaysino/Combat-Lite/main/main.lua"))()
```

## Specifications

- Target Game: bug fixes by captainwoodlegs
- Place ID: 100971017807798
- URL: https://www.roblox.com/games/100971017807798/bug-fixes
- Latency Overhead: < 0.2ms per evaluation tick
- Memory Footprint: < 500 KB
- Protection Coverage: Full 360-degree radial sphere (front, sides, back, tip)
- Control Interference: None (camera, orientation, and velocity are untouched)
- GUI Dependency: None (native system notifications only)

## Features

Omnidirectional Threat Perception:
Monitors Animator.AnimationPlayed and server weapon states within striking distance (9.2 studs standard, 10.2 studs for lunges, dynamically scaling up to 11.8 studs based on closing velocity). Protects against attacks from all angles including backstabs, flank swings, diagonal lunges, and spin attacks. Locomotive animations (walk, run, jump, fall) and stance idles are strictly filtered out to prevent false triggers.

Per-Strike Parry Refresh:
Dispatches verified block signals on every incoming attack within multi-hit combos, ensuring continuous protection without guard drops or combo bleed-through.

Displace Neutralization:
Detects incoming unblockable attacks (G-kick / Displace). Instantly terminates active block via the unbloc remote and enforces an immunity window to prevent guard-break stuns and knockdowns.

Emergency Fast-Equip:
Detects incoming attacks while unarmed, automatically equips the katana from the Backpack, and initiates block within the same frame while preserving natural stance idle animations.

Post-Combat Sheathing:
Allows weapons to be sheathed or stored back into the Backpack after combat without unwanted re-equipping.

## Controls

Toggle Key: V (Switches defense between ACTIVE and DISABLED with on-screen confirmation)

## Architecture

Production build runs through an automated packaging pipeline with Base64 byte reconstruction, rolling XOR keystream evaluation, and dead-code elimination. Debug symbols, plaintext remotes, and comments are stripped.

## License

MIT License.
