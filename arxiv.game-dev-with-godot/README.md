# arxiv.game-dev-with-godot — Indie Game Development with Godot: Zero to Steam Launch

**1,478 arXiv abstracts** across 15 searches covering the technical foundations of indie game development.
**This README is the primary knowledge document** — it covers the full roadmap from first Godot install to shipping a commercial game on Steam, including engine concepts, business registration, financial management, and tax obligations.

> Target audience: Solo developer or small team (1–5 people). Target platform: Steam (Windows/Mac/Linux). Engine: Godot 4.x.

---

## Search Topics (15 Categories)

| # | Topic | Keywords | Papers | Superseded Theory / Established Fallacy |
|---|---|---|---|---|
| 01 | Godot Engine & ECS | godot / GDScript / entity component system | 11 | "Unity/Unreal are the only serious engines" → Godot 4 ships a production-capable Vulkan renderer, a mature GDScript, and a permissive MIT license; for indie solo dev the total cost of ownership is unmatched. |
| 02 | 2D Game Dev | 2D platformer / tilemap / sprite / pixel art | 32 | "2D games are easier, so start with 3D later" → 2D surface area is narrower but mastery requirements for polish (hitboxes, animation state machines, tile autotiling) are identical; scope decides difficulty, not dimension. |
| 03 | 3D Graphics & Rendering | 3D game rendering / shader / PBR / LOD | 45 | "3D games require expensive art pipelines" → Stylized 3D with generated/purchased assets and Godot's standard PBR material ships publishable games at indie budget. |
| 04 | Procedural Content Generation | procedural generation / dungeon / level generation | 200 | "RNG alone creates interesting procedural content" → Unconstrained randomness produces incoherent content; grammar-based, Wave Function Collapse, and noise-layer PCG are the production standard. |
| 05 | Game AI & NPC Behavior | game AI / behavior tree / NPC | 200 | "Complex behavior trees feel lifelike" → Shallow state machines + a few authored lines of dialogue beat 500-node behavior trees for player perception of NPC intelligence in indie games. |
| 06 | Game Audio | game audio / sound design / adaptive music | 49 | "Music should play continuously" → Dynamic audio states (calm / tension / combat) with silent pauses for emotional contrast increase player presence more than continuous soundtrack. |
| 07 | Game Animation | game animation / character animation / motion matching | 149 | "Keyframe animation is enough for quality motion" → Motion capture + inverse kinematics + procedural blend trees are needed for responsive character feel in action games. |
| 08 | Indie Game Research | indie game / independent game / solo developer | 84 | "Originality is the #1 success factor" → Research on Steam top sellers shows discoverability (wishlist velocity, category fit) predicts revenue more reliably than originality scores. |
| 09 | Game Monetization | game monetization / free to play / game revenue | 116 | "Free-to-play maximizes revenue for indie" → Paid premium games on Steam have better long-term review scores, lower refund rates, and better word-of-mouth for indie devs without large marketing budgets. |
| 10 | Game Testing & QA | game testing / playtesting / game QA | 83 | "Human playtesting covers everything" → Automated gameplay agents find edge-case crashes and softlocks that 100 human sessions miss; both are required. |
| 11 | Player Experience | player experience / player engagement / player satisfaction | 31 | "Difficulty should always be adjustable by the player" → Self-determination theory: players with autonomy over challenge level show higher intrinsic motivation; but DDA achieves the same without decision fatigue. |
| 12 | Game Analytics | game analytics / player telemetry / game metrics | 40 | "Gut instinct guides game balance" → Telemetry data on death locations, item usage, and session length reveals balance issues invisible to the developer. |
| 13 | Game Marketing & Community | game marketing / game launch / game community | 200 | "A good game markets itself" → Research on Steam confirms launch-week wishlist count is the single strongest predictor of first-week revenue; marketing must precede launch. |
| 14 | Reinforcement Learning in Games | reinforcement learning game / deep RL game | 200 | "Alpha-beta pruning is sufficient for all game AI" → Deep RL (PPO, DQN) enables emergent NPC behavior impossible with scripted trees; even small indie games benefit from RL for playtesting bots. |
| 15 | Game Narrative | game narrative / interactive story / narrative game | 38 | "Narrative and gameplay are in fundamental tension" → Environmental storytelling, systemic narrative, and ludonarrative consonance research show story can reinforce moment-to-moment gameplay. |

---

## Full Indie Dev Roadmap

---

### Phase 0 — Before You Write One Line of Code

#### Why Godot 4?

| Criterion | Godot 4 | Unity | Unreal 5 |
|---|---|---|---|
| License | MIT (free forever, no royalties) | Proprietary (Runtime Fee controversy, 2023) | Epic 5% royalty above $1M gross |
| Language | GDScript (Python-like) + C# + C++ | C# | C++ / Blueprints |
| 2D workflow | Native, first-class | Bolt-on | Bolt-on |
| Binary size | ~45 MB export | 30–200 MB | 500 MB+ |
| Asset store | Limited | Large paid/free asset store | Fab marketplace |
| Best for | Indie solo / small team | Mid-size studio | AAA / large team |

**Decision rule**: If you are a solo developer building a 2D or stylized 3D game with a budget under $10,000, Godot 4 is the correct engine. Switch only if you need a specific plugin only available on another engine.

#### Setting Up Godot 4

```
1. Download Godot 4.x from godotengine.org (standard or Mono/.NET version)
2. No installation needed — unzip and run
3. Create a new project: File → New Project → choose renderer
   - Compatibility: best for web/mobile, lowest visual quality
   - Mobile: Vulkan mobile, good balance
   - Forward+: full Vulkan, best quality, desktop only
4. Configure version control: add .godot/ to .gitignore
   Keep: project.godot, *.gd, *.tscn, *.tres, assets/
```

---

### Phase 1 — Godot Engine Core Concepts

#### The Node / Scene / Signal Model

```
Everything in Godot is a Node.
Scenes are saved node trees (.tscn files).
Signals are Godot's event system (like events/delegates in other engines).

Player.tscn
├── CharacterBody2D        ← root node, handles physics
│   ├── Sprite2D           ← visual
│   ├── AnimationPlayer    ← controls animations
│   ├── CollisionShape2D   ← hitbox
│   └── Camera2D           ← follows player
```

| Concept | What It Is | When to Use |
|---|---|---|
| Node | Base building block with a transform and parent/child tree | Always — everything is a node |
| Scene | A saved tree of nodes, instantiable as a prefab | One scene per game object (player, enemy, bullet) |
| Signal | Typed event emitted by a node, connected to a callable | Decouple systems: health changed, level completed |
| Resource | Data file (.tres) that can be shared between scenes | Weapon stats, audio stream, material |
| Autoload | A scene/script that loads globally for the whole game | GameManager, AudioManager, SaveManager |

#### GDScript Essentials

```gdscript
extends CharacterBody2D

const SPEED = 200.0
const JUMP_VELOCITY = -400.0

@export var health: int = 100          # visible in Inspector
@onready var sprite = $Sprite2D        # cached node reference

signal health_changed(new_health: int) # typed signal

func _ready() -> void:
    health_changed.connect(_on_health_changed)

func _physics_process(delta: float) -> void:
    # Add gravity
    if not is_on_floor():
        velocity += get_gravity() * delta

    # Handle jump
    if Input.is_action_just_pressed("ui_accept") and is_on_floor():
        velocity.y = JUMP_VELOCITY

    # Handle movement
    var direction = Input.get_axis("ui_left", "ui_right")
    velocity.x = direction * SPEED if direction else move_toward(velocity.x, 0, SPEED)

    move_and_slide()

func take_damage(amount: int) -> void:
    health -= amount
    health_changed.emit(health)
    if health <= 0:
        queue_free()

func _on_health_changed(new_health: int) -> void:
    print("Health: ", new_health)
```

#### Key Node Types

| Category | Node | Use Case |
|---|---|---|
| 2D Physics | CharacterBody2D | Player, enemy with move_and_slide() |
| 2D Physics | RigidBody2D | Physics objects (crates, balls) |
| 2D Physics | Area2D | Triggers, hitboxes, pickups |
| 2D Visual | Sprite2D | Static image |
| 2D Visual | AnimatedSprite2D | Frame-based animation from sprite sheet |
| 2D Visual | TileMapLayer | Tile-based maps |
| 3D Physics | CharacterBody3D | 3D player movement |
| 3D Visual | MeshInstance3D | 3D object rendering |
| 3D Visual | DirectionalLight3D | Sun / directional lighting |
| UI | Control / Panel / Label | All UI elements |
| UI | CanvasLayer | HUD that doesn't move with camera |
| System | AnimationPlayer | Timeline-based animation |
| System | AudioStreamPlayer | Sound playback |
| System | GPUParticles2D | Particle effects |

---

### Phase 2 — Building a 2D Game

#### 2D Game Architecture Pattern

```
Main.tscn                  ← root scene, loads levels
├── GameManager.tscn        ← Autoload: score, lives, state
├── Level1.tscn             ← current level
│   ├── TileMapLayer        ← ground, platforms
│   ├── Player.tscn         ← instanced player scene
│   ├── Enemies/            ← instanced enemy scenes
│   └── UI.tscn             ← CanvasLayer with HUD
└── AudioManager.tscn       ← Autoload: music, SFX buses
```

#### Tilemaps (Godot 4.3+)

```
1. Create TileSet resource with your tile sheet texture
2. Add TileMapLayer node, assign TileSet
3. Paint tiles in editor
4. For collision: select tile in TileSet editor → add CollisionPolygon2D
5. For autotiling: create TerrainSet → assign terrain bits per tile
```

#### Character Controller (Godot 4 CharacterBody2D)

```gdscript
# Minimal character controller with coyote time + jump buffer
extends CharacterBody2D

@export var speed := 200.0
@export var jump_force := 500.0
@export var gravity_scale := 2.5

var coyote_timer := 0.0
var jump_buffer := 0.0
const COYOTE_TIME := 0.12
const JUMP_BUFFER_TIME := 0.12

func _physics_process(delta: float) -> void:
    var gravity = ProjectSettings.get_setting("physics/2d/default_gravity")

    if is_on_floor():
        coyote_timer = COYOTE_TIME
    else:
        coyote_timer -= delta
        velocity.y += gravity * gravity_scale * delta

    if Input.is_action_just_pressed("jump"):
        jump_buffer = JUMP_BUFFER_TIME

    jump_buffer -= delta

    if jump_buffer > 0 and coyote_timer > 0:
        velocity.y = -jump_force
        coyote_timer = 0.0
        jump_buffer = 0.0

    var dir := Input.get_axis("move_left", "move_right")
    velocity.x = move_toward(velocity.x, dir * speed, speed * 8 * delta)
    move_and_slide()
```

#### Camera & Screen Shake

```gdscript
# Camera2D shake pattern
@export var shake_strength := 10.0
var shake_timer := 0.0

func shake(duration := 0.3) -> void:
    shake_timer = duration

func _process(delta: float) -> void:
    if shake_timer > 0:
        shake_timer -= delta
        offset = Vector2(
            randf_range(-shake_strength, shake_strength),
            randf_range(-shake_strength, shake_strength)
        )
    else:
        offset = Vector2.ZERO
```

---

### Phase 3 — Building a 3D Game

#### 3D Scene Setup

```
World.tscn
├── WorldEnvironment          ← sky, ambient light, post-processing
├── DirectionalLight3D        ← sun
├── Player.tscn
│   ├── CharacterBody3D
│   │   ├── CollisionShape3D  ← CapsuleShape3D
│   │   ├── MeshInstance3D    ← character model
│   │   ├── Camera3D          ← first-person: child of head bone
│   │   └── AnimationPlayer
└── Level.tscn
    ├── StaticBody3D meshes
    └── NavigationRegion3D    ← AI navigation baked mesh
```

#### First-Person Controller

```gdscript
extends CharacterBody3D

@export var speed := 5.0
@export var jump_velocity := 5.0
@export var mouse_sensitivity := 0.002

@onready var camera := $Camera3D
var pitch := 0.0

func _ready() -> void:
    Input.mouse_mode = Input.MOUSE_MODE_CAPTURED

func _unhandled_input(event: InputEvent) -> void:
    if event is InputEventMouseMotion:
        rotate_y(-event.relative.x * mouse_sensitivity)
        pitch = clamp(pitch - event.relative.y * mouse_sensitivity, -PI/2, PI/2)
        camera.rotation.x = pitch

func _physics_process(delta: float) -> void:
    if not is_on_floor():
        velocity += get_gravity() * delta
    if Input.is_action_just_pressed("jump") and is_on_floor():
        velocity.y = jump_velocity
    var input_dir := Input.get_vector("move_left","move_right","move_forward","move_back")
    var direction := (transform.basis * Vector3(input_dir.x, 0, input_dir.y)).normalized()
    velocity.x = direction.x * speed if direction else move_toward(velocity.x, 0, speed)
    velocity.z = direction.z * speed if direction else move_toward(velocity.z, 0, speed)
    move_and_slide()
```

---

### Phase 4 — Core Game Systems

#### Save / Load System

```gdscript
# SaveManager.gd (Autoload)
const SAVE_PATH := "user://savegame.json"

func save(data: Dictionary) -> void:
    var file := FileAccess.open(SAVE_PATH, FileAccess.WRITE)
    file.store_string(JSON.stringify(data))

func load_data() -> Dictionary:
    if not FileAccess.file_exists(SAVE_PATH):
        return {}
    var file := FileAccess.open(SAVE_PATH, FileAccess.READ)
    return JSON.parse_string(file.get_as_text())
```

#### State Machine Pattern

```gdscript
# Lightweight enum-based state machine
enum State { IDLE, WALK, JUMP, ATTACK, DEAD }
var state := State.IDLE

func _physics_process(delta: float) -> void:
    match state:
        State.IDLE:   _state_idle(delta)
        State.WALK:   _state_walk(delta)
        State.JUMP:   _state_jump(delta)
        State.ATTACK: _state_attack(delta)
        State.DEAD:   pass

func transition(new_state: State) -> void:
    state = new_state
    # trigger animation, sound, etc.
```

#### Scene Management (level loading)

```gdscript
# SceneManager.gd (Autoload)
func change_scene(path: String, transition := true) -> void:
    if transition:
        $TransitionAnim.play("fade_out")
        await $TransitionAnim.animation_finished
    get_tree().change_scene_to_file(path)
    if transition:
        $TransitionAnim.play("fade_in")
```

---

### Phase 5 — Audio, Shaders & Polish

#### Audio Architecture

```
Bus layout (Project → Audio):
  Master
  ├── Music     (volume slider in Options menu)
  ├── SFX       (volume slider)
  └── UI        (separate from SFX for muting in pause)

AudioStreamPlayer for music (non-positional)
AudioStreamPlayer2D / 3D for spatial SFX
```

```gdscript
# AudioManager.gd (Autoload) — simple sound pool
var sfx_pool := {}

func play_sfx(key: String) -> void:
    if key not in sfx_pool:
        sfx_pool[key] = AudioStreamPlayer.new()
        add_child(sfx_pool[key])
        sfx_pool[key].stream = load("res://audio/sfx/" + key + ".ogg")
        sfx_pool[key].bus = "SFX"
    sfx_pool[key].play()
```

#### Custom Shaders (Sprite Outline)

```glsl
// outline.gdshader — attach to Sprite2D material
shader_type canvas_item;

uniform vec4 outline_color : source_color = vec4(1.0);
uniform float outline_width : hint_range(0, 10) = 1.0;

void fragment() {
    vec4 col = texture(TEXTURE, UV);
    if (col.a < 0.1) {
        vec2 size = outline_width / vec2(textureSize(TEXTURE, 0));
        float alpha = texture(TEXTURE, UV + vec2(size.x, 0)).a
                    + texture(TEXTURE, UV - vec2(size.x, 0)).a
                    + texture(TEXTURE, UV + vec2(0, size.y)).a
                    + texture(TEXTURE, UV - vec2(0, size.y)).a;
        COLOR = vec4(outline_color.rgb, min(alpha, 1.0) * outline_color.a);
    } else {
        COLOR = col;
    }
}
```

---

### Phase 6 — Game AI & Navigation

#### NavigationAgent2D (Pathfinding)

```gdscript
# Enemy with pathfinding to player
extends CharacterBody2D

@onready var nav := $NavigationAgent2D
@export var speed := 80.0

func _physics_process(delta: float) -> void:
    if nav.is_navigation_finished():
        return
    var next := nav.get_next_path_position()
    var direction := (next - global_position).normalized()
    velocity = direction * speed
    move_and_slide()

func set_target(pos: Vector2) -> void:
    nav.target_position = pos
```

#### Simple Behavior State Machine for Enemy

```gdscript
enum EnemyState { PATROL, CHASE, ATTACK, DEAD }

func _physics_process(delta: float) -> void:
    match state:
        EnemyState.PATROL:
            _patrol(delta)
            if player_in_sight_range():
                transition(EnemyState.CHASE)
        EnemyState.CHASE:
            nav.target_position = player.global_position
            _move_to_nav(delta)
            if player_in_attack_range():
                transition(EnemyState.ATTACK)
            elif not player_in_sight_range():
                transition(EnemyState.PATROL)
        EnemyState.ATTACK:
            _attack()
            if not player_in_attack_range():
                transition(EnemyState.CHASE)
```

---

### Phase 7 — Testing, Profiling & QA

#### In-Engine Profiler

```
Debug → Profiler while running:
  - FPS + frame time (target: 60 fps / 16.67ms)
  - GPU time: watch for draw call spikes
  - GDScript: find expensive _process() functions

Debug → Monitor:
  - Object count (watch for leaks with queue_free())
  - Draw calls: target < 200 per frame for 60fps
  - Physics bodies: too many causes frame drops
```

#### Automated Testing with GDUnit4

```gdscript
# test_player.gd
extends GdUnitTestSuite

var player: Player

func before_test() -> void:
    player = Player.new()
    add_child(player)

func after_test() -> void:
    player.queue_free()

func test_take_damage_reduces_health() -> void:
    player.health = 100
    player.take_damage(30)
    assert_int(player.health).is_equal(70)

func test_death_on_zero_health() -> void:
    player.health = 10
    player.take_damage(10)
    await get_tree().process_frame
    assert_bool(is_instance_valid(player)).is_false()
```

#### Playtesting Checklist

| Phase | What to Test | Method |
|---|---|---|
| Internal alpha | Core loop fun, controls feel, crash bugs | Dev self-play, 5 friends |
| Closed beta | Tutorial clarity, difficulty curve, first 10 minutes | 20–50 targeted players |
| Open beta | Performance on different hardware, edge cases | Steam beta branch, 200+ players |
| Pre-launch | Day-1 patch readiness, achievements, cloud saves | Full regression pass |

---

### Phase 8 — Building & Export

#### Export Targets

| Platform | Export Template | Notes |
|---|---|---|
| Windows | Windows Desktop | .exe + PCK; codesign optional but reduces SmartScreen warnings |
| macOS | macOS | Must codesign + notarize for Gatekeeper; requires Apple Developer account ($99/yr) |
| Linux | Linux/X11 | .x86_64 binary; Steam Runtime handles dependencies |
| Web | Web (HTML5) | Godot 4 web export is functional; SharedArrayBuffer requires COOP/COEP headers |
| Android | Android | Requires Android SDK, JDK; Google Play fee: $25 one-time |
| iOS | iOS | Requires Xcode on Mac; App Store fee: $99/yr |

```
Project → Export → Add Preset (Windows Desktop)
  Resources tab:
    - Include filters: *.png,*.ogg,*.tres,*.gdshader
    - Exclude: tests/, .git/
  Features tab:
    - Release (not debug)
  Binary:
    - Embed PCK into executable for single-file distribution
```

---

### Phase 9 — Steam Integration with GodotSteam

#### Setup

```
1. Download GodotSteam from godotsteam.com (pre-built editor + templates)
   OR use the GDExtension version in a standard Godot install
2. Add steam_appid.txt to project root with your App ID (480 for testing)
3. Place steam_api.dll (Windows) / libsteam_api.so (Linux) next to binary
```

#### Basic Steam Initialization

```gdscript
# SteamManager.gd (Autoload)
extends Node

func _ready() -> void:
    if OS.has_feature("editor"):
        return  # don't init Steam in editor
    var result = Steam.steamInit()
    if result["status"] != 1:
        push_error("Steam init failed: " + str(result))
        return
    print("Steam initialized. AppID: ", Steam.getAppID())

func _process(_delta: float) -> void:
    Steam.run_callbacks()
```

#### Achievements

```gdscript
# Unlock an achievement
Steam.setAchievement("FIRST_KILL")
Steam.storeStats()

# Check on game start (for unlock indicators)
func check_achievement(name: String) -> bool:
    return Steam.getAchievement(name)["achieved"]
```

#### Steam Cloud Saves

```gdscript
# Write save to Steam Cloud
func cloud_save(filename: String, data: Dictionary) -> void:
    var json_str = JSON.stringify(data)
    Steam.fileWrite(filename, json_str.to_utf8_buffer())

# Read from Steam Cloud
func cloud_load(filename: String) -> Dictionary:
    if not Steam.fileExists(filename):
        return {}
    var bytes = Steam.fileRead(filename)
    return JSON.parse_string(bytes.get_string_from_utf8())
```

---

### Phase 10 — Steam Publishing Checklist

#### Steamworks Account Setup

| Step | Action | Cost |
|---|---|---|
| 1 | Register at partner.steamgames.com | $100 USD one-time (refunded at $1,000 revenue) |
| 2 | Complete banking info (Stripe-based) | Free |
| 3 | Complete tax interview (W-9/W-8BEN) | Free |
| 4 | Create App in Steamworks Dashboard | Free after $100 fee |
| 5 | Submit to Steam Review | Free (review takes ~5 business days) |

#### Store Page Requirements

| Asset | Specification |
|---|---|
| Capsule (main) | 616 × 353 px |
| Capsule (large) | 460 × 215 px |
| Header capsule | 460 × 215 px |
| Vertical capsule | 374 × 448 px |
| Screenshots | Min 5, 1280 × 720 or 1920 × 1080 |
| Trailer | Optional but strongly recommended; 1080p60 |
| Short description | Max 300 characters |
| Long description | HTML supported; include features, genre, system requirements |

#### Age Rating

```
IARC (International Age Rating Coalition):
  Complete free questionnaire at Steamworks → IARC Questionnaire
  Takes ~10 minutes, gives ratings for all major regions (ESRB, PEGI, USK, etc.)
  Required before release
```

#### Pre-Launch Timeline

| Time Before Launch | Action |
|---|---|
| 8+ weeks | Store page live (coming soon), start wishlist campaign |
| 4 weeks | Send keys to content creators / press |
| 2 weeks | Enable Steam beta branch for testing |
| 1 week | Upload release build, submit for final review |
| Launch day | Announce on social, post in communities, email wishlist |
| Day 1 patch | Fix top reported bugs within 24h |

---

### Phase 11 — Company Registration & Legal Compliance

#### Entity Type Comparison

| Structure | Best For | Liability | Tax Treatment | Setup Cost |
|---|---|---|---|---|
| Sole Proprietor / Freelancer | Side project, <$50k/yr | Personal liability | Pass-through to personal tax | Free–$50 (DBA filing) |
| Single-Member LLC (US) | Primary income source | Limited (separates personal assets) | Pass-through (Schedule C) or S-Corp election | $50–$500 (by state) |
| Ltd / Limited Company (UK) | UK-based developers | Limited | Corporation Tax (19–25%) | ~£12 via Companies House |
| 个体工商户 (China) | Small indie studio China | Personal liability | 经营所得 progressive rate | RMB 200–500 |
| 有限责任公司 (China) | Growing studio China | Limited | Enterprise Income Tax 25% (15% high-tech) | RMB 5,000+ registered capital |

#### US LLC Formation (Recommended for US Devs)

```
1. Choose state: Wyoming or Delaware for low fees; home state to avoid registered agent fees
2. File Articles of Organization with Secretary of State (~$50–$150)
3. Get EIN (Employer Identification Number) from IRS.gov — free, instant online
4. Open business bank account (Mercury, Relay, or local credit union)
5. File BOI (Beneficial Ownership Information) report with FinCEN — free, required 2024+
6. Annual report: $0–$300 depending on state
```

#### Steamworks Tax Interview

```
US persons: Complete W-9 (SSN or EIN)
Non-US persons: Complete W-8BEN (individual) or W-8BEN-E (entity)
  - W-8BEN reduces US withholding tax on US-sourced income
  - Many countries have tax treaties reducing withholding to 0%
  - China: 10% withholding without treaty; treaty may reduce to 0% for services
  - Update W-8BEN every 3 years
```

#### Legal Documents for Your Game

| Document | Required? | Notes |
|---|---|---|
| Privacy Policy | Yes (Steam requires) | Required if you collect any data; GDPR applies to EU players |
| EULA / Terms of Service | Recommended | Limits liability; define refund policy |
| Copyright notice | Automatic (no registration needed) | Register with Copyright Office for statutory damages in US |
| Trademark | Optional | Consider for game title if building a series |
| COPPA compliance | If targeting under-13 | Do not collect data from children without parental consent |
| Accessibility statement | Recommended | WCAG guidelines for menus; subtitle support |

#### Content Ratings

| Rating System | Region | How to Get | Cost |
|---|---|---|---|
| IARC | Global (via Steam) | Steamworks questionnaire | Free |
| ESRB | North America | IARC or direct submission | Free via IARC |
| PEGI | Europe | IARC or direct | Free via IARC |
| CERO | Japan | Direct submission to CERO | ~¥55,000 |
| ACB | Australia | IARC or direct | Free via IARC |

---

### Phase 12 — Financial Management

#### Revenue Streams

| Source | Revenue Share | Payment Schedule | Notes |
|---|---|---|---|
| Steam | 70% to developer | Net 30 after month end | 75% after $10M, 80% after $50M lifetime |
| itch.io | 85–100% (configurable) | Instant via Stripe/PayPal | Great for early access, pay-what-you-want |
| Epic Games Store | 88% to developer | Net 45 | Harder to get listed as indie |
| Humble Bundle | Negotiated | Per bundle | High-profile exposure |
| GOG | 70% | Monthly | DRM-free audience |

#### Steam Revenue Calculator

```
Gross revenue:         $10,000
- Refunds (~5-8%):      -$700
- Chargebacks (~1%):    -$100
Net before Steam:       $9,200
- Steam 30% cut:       -$2,760
Developer net:          $6,440
- Payment processing:  ~$130
- VAT/tax Steam handles: $0 (Steam is the "merchant of record" in most regions)
Final to bank:          ~$6,310 (63% of gross)
```

#### Budget Planning for Indie Games

| Category | Typical Range | Notes |
|---|---|---|
| Music & SFX | $500–$5,000 | Hire composer; AudioJungle; free CC0 assets |
| Art assets | $0–$10,000 | Self-made, Kenney.nl, itch.io asset packs |
| Marketing | $500–$5,000 | Press kits, trailer editing, influencer keys |
| Steam fee | $100 | One-time, recouped |
| Business setup | $0–$500 | LLC, bank account |
| Tools & subscriptions | $200–$1,000/yr | Godot (free), Adobe CC, Aseprite, etc. |
| Contractor work | $0–$20,000 | QA testers, localizers, art commissions |

#### Expense Tracking

```
Track every business expense from day 1:
  - Hardware (computer, drawing tablet, controllers): depreciable asset
  - Software licenses (Aseprite, Affinity Photo, etc.): deductible
  - Music/SFX licenses: deductible
  - Contractor payments: issue 1099-NEC if >$600 (US)
  - Home office: partial deduction if dedicated space
  - Internet: partial deduction
  - Conference/event tickets (GDC, etc.): deductible

Tools: Wave (free), QuickBooks Self-Employed, or a spreadsheet
```

---

### Phase 13 — Tax Management

#### US Tax Obligations for Indie Devs

| Tax | Rate | Due Date | Form |
|---|---|---|---|
| Federal income tax | 10–37% on net income | April 15 annual + quarterly estimates | 1040 / Schedule C |
| Self-employment tax | 15.3% on net income up to $160,200 | With quarterly estimates | Schedule SE |
| Quarterly estimates | 90% of current year or 100% of prior year | Apr 15, Jun 15, Sep 15, Jan 15 | 1040-ES |
| State income tax | 0–13% (varies) | Varies by state | State form |

```
Quarterly tax payment estimate (US):
  Net income this quarter: $5,000
  Self-employment tax (15.3%):  $765
  Federal income (22% bracket): $1,100
  State (5%):                    $250
  Quarterly payment:            ~$2,115 (42% of net)
  Rule of thumb: set aside 30–40% of every payment for taxes
```

#### UK Tax (if UK-based)

```
Sole Trader:
  - Register for Self Assessment at HMRC
  - Income Tax: 20% (£12,570–£50,270), 40% above
  - National Insurance: Class 4 NI on profits > £12,570
  - VAT: register when turnover > £90,000 (Steam handles VAT on your behalf)

Limited Company:
  - Corporation Tax: 19–25% on profits
  - Pay yourself via salary + dividends to optimize tax
  - Director's loan account
```

#### China Tax (if China-based)

```
个体工商户 (Individual Business):
  - 经营所得 progressive: 5%, 10%, 20%, 30%, 35%
  - VAT: 3% (小规模纳税人) or 6% (一般纳税人)
  - Steam handles VAT for end consumers; you handle domestic sales

Steam W-8BEN-E (中国公司):
  - Fill as Chinese entity
  - China-US tax treaty: income from services may be exempt from 30% US withholding
  - Consult Chinese accountant for IIT deductibility of dev expenses
```

#### Key Tax Deductions for Game Developers

| Deduction | Notes |
|---|---|
| Computer / GPU | Section 179 (US): deduct full cost year 1 |
| Software licenses | 100% deductible in year purchased |
| Home office | $5/sq ft simplified method (US); pro-rata rent |
| Contractors | Deductible; 1099-NEC required > $600/yr per contractor |
| Health insurance | 100% deductible if self-employed with no employer plan (US) |
| Steam fee ($100) | Business expense |
| Game development courses | Deductible as continuing education |
| GDC attendance | Travel + conference = deductible business expense |

---

## Best Practices by Category (80/20 Pareto)

### Engine & Architecture

| Critical Lever (20%) | Impact Covered (80%) |
|---|---|
| **One scene per game object** — never put multiple logical game objects in one .tscn | Eliminates merge conflicts, enables parallel dev, makes instancing trivial |
| **Signals over direct calls** for cross-scene communication | Eliminates cyclic dependencies; the #1 source of spaghetti in Godot projects |

### 2D / 3D Gameplay

| Critical Lever (20%) | Impact Covered (80%) |
|---|---|
| **Coyote time + jump buffer** in platformers | Eliminates the #1 platformer complaint: "controls feel unresponsive" |
| **NavigationRegion bake** + NavigationAgent for all NPC movement | Replaces manual pathfinding; handles dynamic obstacles automatically |

### Audio

| Critical Lever (20%) | Impact Covered (80%) |
|---|---|
| **Three audio buses** (Music / SFX / UI) with independent volume sliders | Players with hearing sensitivity can tune each; Options menu staple |
| **Positional audio** (AudioStreamPlayer2D/3D) for all in-world SFX | Spatial audio increases immersion disproportionately to implementation cost |

### Performance

| Critical Lever (20%) | Impact Covered (80%) |
|---|---|
| **Object pooling** for frequently spawned objects (bullets, particles) | Eliminates GC pauses from rapid queue_free() + instantiate() cycles |
| **Profiler first, optimize second** — never optimize without profiler data | Prevents optimizing the wrong thing; devs are wrong about bottlenecks >70% of the time |

### Steam Marketing

| Critical Lever (20%) | Impact Covered (80%) |
|---|---|
| **Wishlist page live 6+ months before launch** | Research confirms wishlist count is the strongest predictor of launch-week revenue |
| **Trailer within first 10 seconds shows actual gameplay** | Conversion rate on trailers that open with gameplay is 2–3× higher than cinematic openers |

### Business & Legal

| Critical Lever (20%) | Impact Covered (80%) |
|---|---|
| **Separate business bank account** from day 1 | Makes accounting trivial; required for LLC legitimacy; prevents audit risk |
| **Set aside 35% of every Steam payment for taxes** | Self-employment tax surprise is the #1 financial mistake of new indie devs |

---

## Paradigm Shifts / 范式转移 (Kuhn)

| Old Paradigm | Trigger Event | New Paradigm |
|---|---|---|
| **AAA engines required for commercial quality** — Unity/Unreal or nothing | Godot 4 Vulkan renderer + MIT license (2023) | **MIT-licensed open engines produce commercial titles** — Godot games on Steam since 2024 |
| **Hand-authored levels are always higher quality** — procedural = cheap | Wave Function Collapse + ML-PCG research (2019+) | **Constraint-guided PCG matches authored quality** at a fraction of the content cost |
| **Indie devs can't afford music** — hire a composer or use stock loops | Adaptive music tools + CC0 asset communities (itch.io, OpenGameArt) | **Procedural / adaptive audio + free assets** produces professional results at near-zero cost |
| **Solo dev can't handle legal/financial complexity** — need a publisher | Stripe, Mercury Bank, Steamworks online tax wizard | **One-person LLC + self-service tax tools** replace the need for a publisher deal |

**已被推翻的认知误区 / Overturned Beliefs:**
- ✗ "需要一个发行商才能登陆 Steam" → Steamworks Direct ($100) 允许任何人直接发布；发行商只在营销预算和平台关系上有价值
- ✗ "Godot 不够专业，无法商业发布" → 2023–2024 年数百款 Godot 游戏登陆 Steam；引擎成熟度已达商业标准
- ✗ "独立开发者不需要建立公司" → 无公司结构意味着个人资产与业务负债无法隔离；LLC 成本极低且保护巨大
- ✗ "Steam 会处理所有税务" → Steam 是消费者端 VAT 的商户账户，但对开发者收入的所得税没有任何帮助；你仍需自己处理

---

## Established Fallacies / 公认谬误

| Misconception | Why It Persisted | What Evidence Shows |
|---|---|---|
| "More features = better game" — add content to solve every problem | Feature-completeness feels like polish | Indie post-mortems: scope creep is the #1 reason indie games fail to ship; cut ruthlessly |
| "Launch on all platforms simultaneously" — maximize addressable market | Platform diversity intuition | Multi-platform launch splits QA effort and community; Steam-first then port is the evidence-backed indie sequence |
| "A better game sells itself" — quality guarantees discoverability | Romantic notion of meritocracy | Steam has 10,000+ new games/year; without a wishlist campaign, even excellent games are invisible at launch |

---

## Obsolete Scientific Theories / 过时科学理论

| Theory | Era | Why Superseded |
|---|---|---|
| Sprite-based 3D (Mode7, billboarding as primary 3D) | Pre-GPU era (1990s) | Hardware-accelerated polygon rendering made true 3D accessible on consumer hardware |
| Fixed-function rendering pipeline | Pre-shader era (pre-2002) | Programmable vertex/fragment shaders replaced all fixed-function stages; Godot's renderer is fully shader-driven |
| Tile-based collision (pixel-perfect per-tile) | 8-/16-bit era | Physics engine collision shapes with broad-phase detection replaced manual per-tile collision; modern engines never use this |

---

## Falsified Theories / 被证伪的理论

| Theory | Prediction | Falsifying Evidence |
|---|---|---|
| "Steam Greenlight/votes predict commercial success" | Community upvotes → revenue | Greenlight shuttered 2017; top Greenlit games underperformed; wishlist velocity (not community votes) predicts launch revenue |
| "Violent games cause aggressive behavior" | Exposure to in-game violence → real-world aggression | Markey et al. (2015), Ferguson (2015): no causal link found; longitudinal data in multiple countries shows inverse correlation |
