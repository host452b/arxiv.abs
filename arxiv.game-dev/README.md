# arxiv.game-dev — Game Development Research: Full Academic Landscape

**5,197 arXiv abstracts** from 29 targeted searches in the CS category, covering every core technical domain of the Game Developer Roadmap.

**Knowledge Document:** [readme_game_roadmap.md](readme_game_roadmap.md) — Complete Game Development Roadmap

## Search Topics (29 Categories)

| # | Topic | Keywords | Papers | Superseded Theory / Established Fallacy |
|---|---|---|---|---|
| 01 | Game Engine Architecture | game engine / real-time engine / game loop / engine architecture | 185 | "Custom engines are always more efficient than commercial engines" → UE5/Unity optimization has closed the gap; custom engines carry massive maintenance costs that rarely justify the tradeoff. |
| 02 | Real-Time Rendering | real-time rendering / shader programming / rendering pipeline / rasterization | 200 | "More polygons = better visual quality" → Ray tracing + global illumination, screen-space effects, and LOD management contribute more to perceived quality than raw polygon count. |
| 03 | Ray Tracing & Global Illumination | ray tracing / global illumination / physically based rendering / path tracing | 200 | "Ray tracing requires full-path tracing to look good" → Hybrid rasterization+ray tracing (DXR) delivers visually comparable results at a fraction of the computational cost. |
| 04 | Procedural Content Generation | terrain generation / noise terrain / map generation / world generation | 200 | "RNG alone creates interesting procedural content" → Unconstrained randomness produces incoherent content; grammar-based, constraint-satisfaction, and ML PCG produce playable variety. |
| 05 | Game AI | game AI / behavior tree / game pathfinding / NPC decision making | 200 | "NPCs with large behavior trees feel lifelike" → Tree-based AI becomes brittle and obviously scripted at scale; LLM-powered and RL-trained NPCs adapt dynamically. |
| 06 | Game Physics | collision detection / rigid body dynamics / physics simulation / physics engine | 200 | "Realistic physics always improves game feel" → Game feel research (Swink) shows intentionally unrealistic physics (exaggerated momentum, forgiving hitboxes) improves perceived quality. |
| 07 | ECS & Architecture Patterns | component based architecture / game object / game framework / engine design | 200 | "Object-oriented inheritance hierarchies are the right architecture for games" → ECS (Entity Component System) significantly outperforms deep OOP hierarchies for cache performance and composition. |
| 08 | Multiplayer & Netcode | multiplayer game / game networking / lag compensation / netcode | 200 | "Deterministic lockstep is the only reliable multiplayer architecture" → Rollback netcode (GGPO) provides significantly better experience for fighting and action games than lockstep. |
| 09 | Game Design & Level Design | game design / level design / MDA framework / game mechanics | 200 | "Difficulty should be determined by player-defined settings" → Dynamic Difficulty Adjustment (DDA) driven by player behavior metrics produces better retention than static settings. |
| 10 | Roguelike & Procedural Generation | procedural generation / noise function / perlin noise / random map | 200 | "Procedural generation makes games infinitely replayable" → Player fatigue with PCG content shows engagement requires authored 'anchor' moments; pure PCG rarely sustains long-term play. |
| 11 | Game UI/UX | user interface design / interaction design / usability / HUD | 200 | "Game UI should follow web/app design conventions" → Diegetic and meta UI designs (health bars integrated into environment) consistently outperform HUD-heavy conventional UI in immersion. |
| 12 | Game Animation & IK | game animation / motion matching / inverse kinematics / character animation | 200 | "Keyframe animation is sufficient for high-quality character motion" → Motion capture + inverse kinematics + procedural blend trees are required for responsive, natural-feeling character motion. |
| 13 | Game Performance Optimization | game optimization / level of detail / occlusion culling / GPU performance | 200 | "GPU is always the rendering bottleneck" → Draw call overhead, CPU-GPU synchronization, and memory bandwidth are frequently the actual bottlenecks, not raw GPU FLOPS. |
| 14 | LLM & Conversational NPC | language model game / LLM NPC / generative AI game / conversational NPC | 185 | "LLM-powered NPCs will always say something coherent and on-topic" → Without constrained output schemas and memory management, LLM NPCs produce off-topic or lore-breaking responses. |
| 15 | Game Testing & QA | software testing automation / test generation / fuzzing / regression testing | 200 | "Human playtesting is required to find most gameplay bugs" → AI playtesting agents systematically explore state spaces that human testers never cover, especially edge cases. |
| 16 | Game Audio | audio synthesis / music generation / sound generation / speech synthesis | 200 | "Silence is always a mistake in games" → Dynamic audio design and strategic silence create emotional contrast; over-saturated soundscapes cause audio fatigue. |
| 17 | Reinforcement Learning in Games | reinforcement learning game / deep RL game / game playing agent | 200 | "Minimax with alpha-beta pruning is optimal for game AI" → MCTS + deep RL (AlphaGo/AlphaZero) made alpha-beta pruning obsolete for complex games by learning evaluation functions. |
| 18 | Art Styles & Rendering | neural style transfer / image stylization / artistic rendering / style generation | 200 | "Photorealism is the goal of all game graphics" → Stylized art directions (cel-shading, pixel art, painterly) show equal or higher player engagement and age significantly better. |
| 19 | Game Economy & Difficulty | dynamic difficulty adjustment / player skill / adaptive game / reward shaping | 152 | "Monetization via random loot boxes is ethically neutral" → Behavioral economics and gambling addiction research have led to regulatory action in multiple countries. |
| 20 | Game Development Process | agile development / software engineering process / CI/CD / devops | 200 | "Crunch time is necessary to ship good games" → Post-mortems consistently show crunch reduces code quality, increases bug rates, and destroys team retention. |
| 21 | Player Experience & Game Feel | user experience / usability study / player satisfaction / game engagement | 200 | "Player retention requires frequent rewards" → Self-determination theory: intrinsic motivation (autonomy, mastery, purpose) sustains engagement better than extrinsic reward schedules. |
| 22 | MMO & Online Games | MMORPG / online game server / virtual world / massively multiplayer | 124 | "MMOs require monthly subscriptions to be sustainable" → Free-to-play with ethical monetization consistently generates higher total revenue than subscription models. |
| 23 | AI Content Generation | generative model game / AI game design / game content generation | 91 | "AI-generated game assets will always look low quality" → Stable Diffusion fine-tuned on game art styles now produces pipeline-quality assets for concept and texture work. |
| 24 | Video Game Research | video game / computer game / game player / game experience | 200 | "Video games are a cultural harm" → 40+ years of media effects research shows no consistent link between game violence and real-world violence; benefits in cognition and social play are documented. |
| 25 | VR / AR Games | virtual reality game / augmented reality / mixed reality / XR | 200 | "VR is niche because of motion sickness" → Locomotion research shows teleportation and comfort modes reduce sickness to non-problem levels for 90%+ of users. |
| 26 | Pathfinding & A* | pathfinding algorithm / A* search / navigation mesh / motion planning | 200 | "A* is the optimal pathfinding algorithm for all games" → Hierarchical pathfinding, flow fields, and navigation meshes outperform A* for large crowds and open-world navigation. |
| 27 | Mobile Games | mobile game / mobile application / touch interface / smartphone game | 200 | "Mobile games must have simple mechanics to succeed" → Deep strategy and RPG mechanics dominate mobile top-grossing charts; complexity + accessibility is the winning formula. |
| 28 | Asset Pipeline & Textures | texture compression / texture synthesis / material generation / PBR material | 200 | "Uncompressed textures provide the best visual quality" → Texture compression (ASTC, BC7) is perceptually lossless with massive memory and bandwidth savings. |
| 29 | Game Narrative | game narrative / interactive story / narrative generation / story game | 143 | "Narrative and gameplay are in fundamental tension" → Environmental storytelling, procedural narrative, and ludonarrative consonance research show narrative can reinforce gameplay. |

**5,480 raw results → 5,197 deduplicated abstracts**

## Abstracts by Year

| Year | Papers | Year | Papers | Year | Papers |
|------|--------|------|--------|------|--------|
| 1996–1999 | 6 | 2010 | 37 | 2020 | 404 |
| 2000–2009 | 115 | 2011–2015 | 308 | [2021](2021/abstracts/) | 426 |
| [2016](2016/abstracts/) | 135 | [2018](2018/abstracts/) | 260 | [2022](2022/abstracts/) | 474 |
| [2017](2017/abstracts/) | 167 | [2019](2019/abstracts/) | 298 | [2023](2023/abstracts/) | 619 |
| [2024](2024/abstracts/) | 790 | [2025](2025/abstracts/) | 992 | [2026](2026/abstracts/) | 222 |

> 2023–2025 totals **2,401 papers** (46% of all), reflecting the exponential growth of game AI and generative game research in recent years.

## Search Parameters

- Category: `cs` (Computer Science)
- Sort: `relevance`
- Tool: [arxs](https://github.com/host452b/arxs) v1.0.3
- Searched: 2026-03-25

---

## Best Practices by Category (80/20 Pareto)

> **Pareto Principle:** In each domain, 20% of key practices drive 80% of results and recognition. Each "critical lever" below represents the high-frequency consensus from papers in that category.

### 01 Game Engine Architecture

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Fixed-timestep game loop** (`fixedUpdate` + variable render frame) | Eliminates physics jitter and network desync; the foundational prerequisite for all engine architecture discussions |
| **Data-Oriented Design (DOD)**: arrange memory by component type, not by entity | 5–10× reduction in cache misses; the single largest performance gain for large-entity scenes |

> Master these two and 80% of engine architecture questions have answers. Everything else (multithreaded rendering, Job System) builds on this foundation.

---

### 02 Real-Time Rendering

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Deferred Shading** | Decouples lighting from geometry count; supports hundreds of dynamic lights; the default choice for modern AAA pipelines |
| **Physically Based Rendering (PBR)**: metallic + roughness workflow | Standardizes materials; assets remain consistent across all lighting conditions, eliminating rework costs |

> Choosing the right rendering path + standardizing materials covers 80% of visual quality demands. Everything else (TAA, SSR) is incremental improvement.

---

### 03 Ray Tracing & Global Illumination

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Hybrid rendering**: ray tracing for reflections/shadows, rasterization for primary rays | 10–20% ray tracing overhead delivers 80% of global illumination visual benefit; avoids full path tracing frame rate collapse |
| **Denoiser** (SVGF / DLSS-RR) | Makes 1 spp path tracing usable quality; without a denoiser, real-time ray tracing is non-viable |

> Hybrid rendering strategy + denoising is the core formula for shipping real-time ray tracing in production today.

---

### 04 Procedural Content Generation (PCG)

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Fractal noise stacking** (Perlin / Simplex + multiple octaves) | Generates natural-looking terrain, clouds, and textures; a single function covers 80% of procedural visual content needs |
| **Seeded randomness + constraint satisfaction** (room placement / level connectivity) | Reproducible (debugging / speedruns) + guaranteed playability; the standard paradigm for Roguelike level generation |

> Master fractal noise and constraint-based seed generation and you can drive the vast majority of PCG scenarios.

---

### 05 Game AI

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Behavior Trees** | Composable NPC decision-making; readable, extensible; native support in UE5 / Unity; covers 80% of NPC behavior requirements in shipped titles |
| **Navigation Mesh (NavMesh) + A\*** | Runtime path queries; precomputed NavMesh reduces real-time pathfinding cost by 10–100× |

> Behavior Trees handle "decisions," NavMesh+A* handles "movement" — the two together solve the core game AI problem.

---

### 06 Game Physics

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Broad-phase collision detection** (spatial hashing / BVH) | Reduces O(n²) collision pair screening to O(n log n); the single largest determinant of physics frame time in large object scenes |
| **Position-Based Dynamics (PBD)** | Unconditionally stable, simple to implement; dominates cloth / soft-body / constraint simulation; the default in Nvidia FleX / PhysX |

> Broad-phase eliminates wasted computation, PBD ensures stability — together they cover 80% of game physics implementation needs.

---

### 07 ECS & Architecture Patterns

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Entity-Component-System (ECS)**: components are pure data, systems are pure logic | Complete decoupling; hot reload, parallel processing, and serialization all benefit; the core architecture of Unity DOTS / Bevy |
| **Object Pooling** | Eliminates per-frame `new/delete` spikes; essential for high-frequency objects: bullets, particles, audio sources |

> ECS solves "how to organize code," Object Pooling solves "how to manage memory" — the two most common answers in game architecture.

---

### 08 Multiplayer & Netcode

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Client-side prediction + server reconciliation** (Rollback Netcode) | Eliminates perceived latency; the decisive technique for network feel in fighting games and shooters |
| **Interpolation + extrapolation** (Dead Reckoning) | Smooths non-critical object movement; masks 80% of network jitter at very low bandwidth cost |

> Client prediction handles inputs, Dead Reckoning handles state — the combination covers 80% of multiplayer latency perception problems.

---

### 09 Game Design & Level Design

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **MDA Framework** (Mechanics → Dynamics → Aesthetics) | Layers design intent for analysis; the most-cited design analysis tool in game research |
| **Grey-boxing iteration** | Validate flow and combat pacing with primitive geometry before art; reduces 80% of late-stage redesign rework |

> MDA clarifies "why," grey-boxing validates "whether it works" — the two most efficient workflows in level design.

---

### 10 Roguelike & Procedural Generation

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **BSP / Room-and-Corridor constrained generation** | Guarantees level connectivity and reachability; the industry-standard foundation algorithm for Roguelike level generation |
| **Meta-progression design** (permanent unlocks + per-run randomness) | *Slay the Spire* / *Hades* validate: meta-progression is the core driver of replayability |

> Constrained generation ensures "each run is playable," meta-progression ensures "motivation to replay" — covers 80% of Roguelike design's critical questions.

---

### 11 Game UI/UX

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Instant visual feedback (< 100ms)** | Every interactive element responds within 100ms; beyond this threshold players perceive "no response" — the largest negative factor in UX ratings |
| **Diegetic UI first** | Integrate UI into the game world (e.g., Dead Space's spine health bar); reduces HUD clutter, increases immersion |

> Response speed + information layering covers 80% of game UI usability problems; everything else (animation, style) is incremental experience.

---

### 12 Game Animation & IK

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Motion Matching** | Real-time query of the best clip from a motion capture database; replaces complex animation state machines; validated by *God of War* and *For Honor* |
| **Two-Bone IK** | The minimum viable solution for hand/foot contact with the environment; negligible computation cost, significant visual improvement |

> Motion Matching covers 80% of body animation quality; Two-Bone IK resolves contact point clipping — the two core levers in modern character animation.

---

### 13 Game Performance Optimization

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **LOD (Level of Detail) + Occlusion Culling** | Reduces GPU vertex count and draw calls; the single largest gain in scene complexity optimization |
| **GPU Instancing + Draw Call Batching** | Reduces CPU→GPU submission for repeated geometry from N to 1; resolves CPU-side rendering bottlenecks |

> LOD+culling reduces rendering volume, batching reduces submission count — together they typically cover 80% of frame time optimization headroom.

---

### 14 LLM & Conversational NPC

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Retrieval-Augmented Generation (RAG)**: NPC knowledge base + vector search | Prevents hallucination and maintains character consistency; the engineering core for shipping LLM NPCs |
| **Structured output constraints** (JSON Schema / function calling) | Parses LLM output into game events; eliminates the instability of free-text parsing |

> RAG ensures character consistency, structured output ensures engine-consumable results — covers 80% of LLM NPC engineering risk.

---

### 15 Game Testing & QA

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Critical path automated regression tests** | Every commit automatically validates core game loops (login / combat / save); blocks 80% of production incidents |
| **Fuzzing input handling** | Random input combinations expose crashes and state machine deadlocks; covers edge cases with minimal human effort |

> Automated regression protects the main branch, fuzzing covers boundaries — together they form the minimum viable safety net for game QA.

---

### 16 Game Audio

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Adaptive music systems** (vertical remixing / horizontal transitions) | Dynamically switch music layers by game state; core capability of FMOD / Wwise; infinite states from minimal assets |
| **Spatial audio (HRTF / binaural rendering)** | 3D sound localization; in VR / FPS contexts delivers directional information faster than visual cues |

> Adaptive music solves "monotonous background music," spatial audio solves "sound perception" — covers 80% of game audio experience problems.

---

### 17 Reinforcement Learning in Games

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **PPO (Proximal Policy Optimization)** | The most stable policy gradient algorithm; foundation of OpenAI Five / AlphaStar; suitable for 80% of game RL tasks |
| **Reward shaping** | Decompose sparse rewards into dense intermediate rewards; resolves the exploration bottleneck in long-horizon game RL |

> PPO as the algorithmic baseline, reward shaping as the convergence solution — covers 80% of game RL implementation paths.

---

### 18 Art Styles & Rendering

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Neural style transfer / diffusion model texture generation** | Unifies art style; automates concept-to-texture workflow; covers 80% of stylized texture needs |
| **Post-process LUT (color grading lookup table)** | One LUT handles full-scene tone mapping; art team defines once, all scenes apply automatically |

> Generative models produce stylized assets, LUTs unify color tone — covers 80% of art style consistency requirements.

---

### 19 Game Economy & Difficulty

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Dynamic Difficulty Adjustment (DDA)**: real-time parameter tuning based on player performance | Maintains the "flow" zone; reduces churn from games feeling too hard or too easy; the core mechanic for retention optimization |
| **Rubber-banding mechanics** | Applies pressure to leaders, compensates laggards; the single most efficient balancing tool in multiplayer games |

> DDA maintains single-player flow, rubber-banding maintains multiplayer balance — covers 80% of core observations in difficulty design research.

---

### 20 Game Development Process

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Vertical Slice prototype** | Validates the core gameplay loop before full production; the critical filter deciding whether to enter full-scale production |
| **CI/CD pipeline** (automated build + smoke tests) | Prevents integration debt accumulation; every commit is deliverable; the engineering infrastructure standard at modern game studios |

> Vertical slice validates direction, CI/CD ensures deliverability — covers 80% of game development process problems.

---

### 21 Player Experience & Game Feel

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Game Juice**: screen shake + particles + sound effects stacked | Every player action has multi-sensory feedback; 80% of "feels good" perception originates here |
| **Clear state visualization** (health / ammo / cooldowns at a glance) | Reduces cognitive load; players focus on decisions, not reading the UI; the most direct positive factor in UX ratings |

> Rich feedback + clear information covers 80% of the core dimensions of player experience evaluation.

---

### 22 MMO & Online Games

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Zone sharding + dynamic load balancing** | Horizontal server capacity scaling; the engineering foundation for thousands of players in the same region |
| **Eventual consistency** (async sync for non-combat state) | Reduces lock contention from strong consistency; inventory / social / map state 80% don't require real-time strong consistency |

> Sharding solves capacity, eventual consistency reduces sync pressure — covers 80% of core MMO backend architecture challenges.

---

### 23 AI Content Generation

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Diffusion models** for 2D asset generation | Covers concept art / textures / sprites for rapid iteration; the dominant approach for AI-generated game art today |
| **Constraint post-processing** (playability validation + collision body generation) | Ensures generated content conforms to game rules; without constraints, ~70% of AI-generated content is not directly usable |

> Generative models provide variety, constraint post-processing ensures usability — covers 80% of AI content generation engineering challenges.

---

### 24 Video Game Research

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Player behavior clustering** (behavioral models / Bartle taxonomy) | Segments players into groups; the foundational analysis tool for all player-data-driven design decisions |
| **Large-scale A/B testing** | Statistically validates design hypotheses; 80% of live-game operational decisions should be data-driven |

> Player modeling understands "who is playing," A/B testing validates "what works" — covers the two highest-frequency methodologies in game research.

---

### 25 VR / AR Games

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Comfort-first locomotion design** (teleportation / snap turn toggle) | Eliminates 80% of motion sickness complaints; the single largest factor affecting VR retention |
| **Foveated rendering** | Reduces resolution in peripheral areas; key GPU budget technique for maintaining 90+ fps (saves 30–50% render budget) |

> Comfort design solves retention, foveated rendering solves frame rate — covers 80% of core VR engineering challenges.

---

### 26 Pathfinding & A*

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Navigation Mesh (NavMesh) precomputation** | Discretizes continuous space into a polygon graph; 10–100× faster than grid A*; the standard in Unity / UE5 |
| **Hierarchical pathfinding (HPA\* / HANA)** | Macro path (region level) + micro path (local level) separation; solves performance problems for pathfinding on very large maps |

> NavMesh solves "spatial representation," hierarchical planning solves "large-map scalability" — covers 80% of pathfinding engineering problems.

---

### 27 Mobile Games

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Adaptive quality presets** (dynamic adjustment by device tier / thermal state) | Covers device fragmentation; prevents thermal throttling on low-end devices; a foundational engineering requirement for mobile game retention |
| **Touch abstraction layer** (virtual joystick / gesture recognition unified interface) | Shields hardware differences; reduces porting cost; best practice for cross-platform mobile game input |

> Adaptive quality solves device fragmentation, touch abstraction solves input fragmentation — covers 80% of mobile game platform adaptation problems.

---

### 28 Asset Pipeline & Textures

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **GPU texture compression** (BC7 for desktop / ASTC for mobile) | 4–6× VRAM reduction with acceptable quality loss; the highest-ROI single optimization in any asset pipeline |
| **Automated LOD generation** (artists submit high-poly; pipeline auto-generates lower LODs) | Eliminates the repetitive labor of manual LOD creation; ensures consistency across LOD transitions |

> Compression solves bandwidth and VRAM, automated LOD solves production efficiency — covers 80% of asset pipeline engineering gains.

---

### 29 Game Narrative

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Branching dialogue + narrative flag system** | Tracks player choices to affect subsequent story; *Disco Elysium* / *Mass Effect* validate: state tracking is the engineering core of non-linear narrative |
| **Environmental storytelling** | Conveys story through scene objects without interrupting flow; the source of 80% of immersive narrative |

> Flag-based branching makes "choices matter," environmental storytelling makes "the world feel deep" — covers 80% of key game narrative design practices.

---

[中文说明](README.zh-CN.md) | [Game Dev Roadmap](readme_game_roadmap.md) | [Back to main](../README.md)

---

## Paradigm Shifts / 范式转移 (Kuhn)

| Old Paradigm | Trigger Event | New Paradigm |
|---|---|---|
| **Custom engines for performance** — proprietary tech = competitive edge | Unreal / Unity optimization: UE5 Nanite, DLSS | **Commercial engines dominate** — ROI favors off-the-shelf solutions |
| **Deterministic lockstep netcode** — all clients must stay in sync | GGPO / rollback research: fighting-game community validation | **Rollback netcode standard** — predict + rollback feels better than lockstep |
| **OOP inheritance for game logic** — deep class hierarchies | Data-oriented design (2018+): cache-miss profiling results | **Entity Component System (ECS)** — composition over inheritance |
| **Alpha-beta pruning game AI** — minimax search | AlphaGo / deep RL (2016+): self-play learning | **MCTS + neural evaluation** — learned value functions replace hand-coded heuristics |

**已被推翻的认知误区 / Overturned Beliefs:**
- ✗ "更多多边形 = 更好的视觉质量" → 光线追踪+全局照明和LOD管理对感知质量的贡献远超多边形数量
- ✗ "真实物理总是改善游戏感受" → 游戏感研究表明，故意不真实的物理（夸张的动量）提升感知质量
- ✗ "加班是发布优秀游戏的必要条件" → 事后分析一致表明加班降低代码质量、增加缺陷率、摧毁团队留存
- ✗ "玩家保留需要频繁奖励" → 自我决定理论：内在动机（自主性、掌握感）比外在奖励更持久


---

## Established Fallacies / 公认谬误

| Misconception | Why It Persisted | What Evidence Shows |
|---|---|---|
| More polygons = better visual quality | Visual fidelity scales with geometry count | Ray tracing, global illumination, and LOD management contribute more to perceived quality than raw polygon count |
| Crunch is necessary to ship quality games | Deadline pressure improves team output | Post-mortems consistently show crunch reduces code quality, increases defect density, and destroys team retention |
| Players prefer realistic physics over gamefeel | Realism = immersion | Game-feel research: deliberately unrealistic physics (exaggerated momentum, coyote time) measurably increase perceived responsiveness and satisfaction |

## Obsolete Scientific Theories / 过时科学理论

| Theory | Era | Why Superseded |
|---|---|---|
| Deep OOP inheritance hierarchies for game entities | Pre-2010s: OOP as universal game architecture | Data-oriented design and ECS proved OOP cache-inefficient at game scale; Bungie, Unity, and Epic adopted component systems |
| Fixed-function GPU pipeline optimization | Pre-2006: optimize within fixed rendering stages | Programmable shaders made fixed-function pipelines obsolete; modern GPU programming is fully shader-driven |
| Deterministic simulation as a networking requirement | Pre-rollback era: all clients must run identical logic | Rollback netcode decoupled gameplay from networking determinism; determinism is now optional per game design choice |

## Falsified Theories / 被证伪的理论

| Theory | Prediction | Falsifying Evidence |
|---|---|---|
| Alpha-beta pruning can beat expert Go players with sufficient depth | Predicted: deeper tree search → superhuman Go performance | 30 years of attempts failed; AlphaGo's MCTS + deep RL, not deeper alpha-beta, achieved superhuman performance (Silver et al., 2016) |
| Violent video games cause real-world aggression | Predicted: exposure to in-game violence → increased aggressive behavior | Markey et al. (2015), Ferguson (2015) meta-analyses: no causal link; longitudinal data shows inverse correlation in several countries |
