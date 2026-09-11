# Combat Lite

Client-side defensive combat routine designed specifically for "bug fixes" by captainwoodlegs (Roblox place ID: 100971017807798). Provides frame-perfect automatic parrying, 360-degree radial threat interception, early-warning emergency fast-equip from backpack, and guard-break evasion for Luau execution environments without modifying player controls, camera angles, or movement kinematics.

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
- Protection Coverage: Full 360-degree radial sphere (front, flank sides, backstabs, blade-tip sweeps)
- Control Interference: None (camera, player orientation, and velocity are untouched)
- GUI Dependency: None (native system notifications only)

## Features

Omnidirectional Threat Perception:
Monitors Animator.AnimationPlayed and server weapon states in a full 360-degree radial danger zone (9.2 studs standard, 10.5 studs for lunges, scaling up to 12.0 studs based on mutual closing velocity). Protects against attacks from all angles including backstabs, flank swings, diagonal lunges, spin cuts, and tip hits. Locomotive animations (walk, run, jump, fall) and stance idles are strictly filtered out to prevent false triggers.

Frame-by-Frame Continuous Threat Scanning:
Evaluates active attack animations and swordatac flags every RenderStepped tick. Intercepts ongoing attacks, sprint lunges, and charges even if the enemy initiated the swing from outside the sensor sphere.

Early-Warning Emergency Fast-Equip:
Monitors incoming threats while unarmed with an expanded 14.8-stud predictive sphere. Automatically equips the katana from the Backpack and synchronizes parry packets within the same frame before the enemy closes into lethal range, while preserving natural posture idle animations.

Combat Authority & Attack Freedom:
Provides unrestricted player attack freedom. Pressing attack keys (Q, E, F, G, R, T, X, B) or Left Mouse Button immediately releases active block to allow fluent chaining and combos. If an incoming enemy strike threatens the player during an attack, Clash Guard instantly cancels the swing and deflects the incoming blow with zero damage taken.

Displace Neutralization:
Detects incoming unblockable attacks (G-kick / Displace). Instantly drops active block via the unbloc remote and enforces an immunity window to prevent guard-break stuns and knockdowns.

Per-Strike Parry Refresh:
Dispatches verified block signals on every incoming strike within multi-hit combos, ensuring continuous protection without guard drops or combo bleed-through.

Post-Combat Sheathing:
Allows weapons to be sheathed or stored back into the Backpack after combat without unwanted re-equipping.

## Controls

Toggle Key: V (Switches defense between ACTIVE and DISABLED with on-screen confirmation)

## Architecture

Production build runs through an automated packaging pipeline with Base64 byte reconstruction, rolling LCG XOR keystream evaluation, and dead-code elimination. Debug symbols, plaintext remotes, and comments are stripped.

## License

MIT License.
