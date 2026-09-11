# Combat Lite

Client-side defensive combat routine for Luau execution environments. Designed for threat perception, dynamic parry windowing, and unblockable neutralization without character kinematics or camera manipulation.

## Execution

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/Solaysino/Combat-Lite/main/main.lua"))()
```

## Specifications

- Latency overhead: < 0.2ms per evaluation tick
- Memory footprint: < 450 KB
- Network footprint: Event-driven, zero remote polling
- Control interference: None (camera, orientation, velocity untouched)
- GUI dependency: None (system notifications only)

## Features

Threat Perception:
Monitors Animator.AnimationPlayed and active playback tracks within 10.5 studs. Resolves asset IDs against internal tables of validated attack signatures. Looped tracks, locomotive states, and idle/clean actions are filtered to eliminate false positives.

Displace Neutralization:
Intercepts unblockable strike signatures. Enforces immediate guard termination via unbloc remote and applies a 0.70s immunity window to prevent guard-break stuns.

Anti-Combo Sustain:
Heartbeat evaluation loop dynamically extends parry duration across rapid strike chains without redundant remote invocations.

Emergency Equipment Retrieval:
Scans Backpack and proximate workspace drops when threats are detected while unequipped. Equips weapon and initializes guard while preserving local stance idle priority tracks.

## Controls

Keybind: V (Toggles routine between ENABLED and DISABLED)

## Architecture

Production build utilizes monolithic array encapsulation, Base64 byte reconstruction, and rolling XOR keystream evaluation. Debug symbols, comments, and plaintext remote identifiers are stripped.

## License

MIT License.
