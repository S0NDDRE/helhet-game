# TECHNICAL_DESIGN.md

**Mapper HELHET.lock.md til konkrete systemer.**

---

## SYSTEMS OVERVIEW

| System | Ansvar | Filer |
|--------|--------|-------|
| Core | Game loop, scene management, save/load | Scripts/Core/ |
| Player | Input, bevegelse, kamera | Scripts/Player/ |
| NPC | AI, emotion, memory, dialogue, tasks | Scripts/NPC/ |
| Interaction | Interactable, inventory, items, physics | Scripts/Interaction/ |
| Audio | AudioManager, SFX, music, ambient | Scripts/Audio/ |
| UI | UIManager, dialogue, menu, accessibility | Scripts/UI/ |
| VR | VR controllers, hands, interact, presence | Scripts/VR/ |
| Visuals | Visual, material, post, weather | Scripts/Visuals/ |
| Build | Platform detection, graphics presets, launcher | Scripts/Build/ |

---

## DATA FLOW

```
[PlayerInput] → [PlayerController] → [PlayerCamera]
                      ↓
              [GameManager] → [SceneManager]
                      ↓
    ┌─────────────────┼─────────────────┐
    ↓                 ↓                 ↓
[NPC]          [Interaction]        [Audio]
[Dialogue]     [Inventory]        [Music]
[Emotion]      [Item]             [SFX]
[Memory]                          [Ambient]
    ↓                 ↓                 ↓
    └─────────────────┼─────────────────┘
                      ↓
                  [UIManager]
                      ↓
              [VisualController]
                      ↓
                [PostProcess]
```

---

## TICK RATE

- **FixedUpdate:** 50 Hz (0.02s) — fysikk, input buffer
- **Update:** variabler — bevegelse, AI, animasjon
- **LateUpdate:** kamera, VR

---

## FUSJONSKRAV

Hver interaksjon må endre minst **3 systemer** samme frame.

**Eksempel (dialogvalg):**
1. PlayerInput → velger dialogvalg
2. NPCDialogue → spiller av linje
3. NPCEmotion → endrer emosjon (trust +0.2)
4. NPCMemory → lagrer interaksjon ("spilleren var snill")
5. UI → oppdaterer trust-meter

**5 systemer på én gang. Det er fusjon. Det er kvalitet.**

---

## RUST-MOTOR (bevy_ecs + wgpu)

Hvis du vil ha en Rust-motor i stedet for Unity:

### Crates

- `bevy`: Game engine (ECS, rendering, audio, input)
- `wgpu`: GPU rendering (cross-platform)
- `rodio`: Audio playback
- `gilrs`: Gamepad input
- `rapier`: Fysikk (2D/3D)
- `leafwing-input-manager`: Input mapping
- `bevy_mod_picking`: Interaction (raycast, hover, click)

### Struktur

```
rust-engine/
├── Cargo.toml
├── src/
│   ├── main.rs
│   ├── core/
│   │   ├── mod.rs
│   │   ├── game_state.rs
│   │   └── world_model.rs
│   ├── player/
│   │   ├── mod.rs
│   │   ├── controller.rs
│   │   └── camera.rs
│   ├── npc/
│   │   ├── mod.rs
│   │   ├── emotion.rs
│   │   ├── memory.rs
│   │   └── dialogue.rs
│   ├── interaction/
│   │   ├── mod.rs
│   │   ├── interactable.rs
│   │   └── inventory.rs
│   ├── audio/
│   │   ├── mod.rs
│   │   └── manager.rs
│   └── visuals/
│       ├── mod.rs
│       └── post_process.rs
```

### Kom i gang

```bash
cd rust-engine
cargo run
```

Se `rust-engine/README.md` for full instruksjoner.
