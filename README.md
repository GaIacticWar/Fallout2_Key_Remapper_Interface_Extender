<p align="center">
  <img src="https://github.com/user-attachments/assets/85c84eb3-1e22-4741-b452-8dd5765b0b07" width="40%" alt="fallout2_logo" />
</p>

<h1 align="center">Key Remapper & Interface Extender</h1>

<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;A lightweight, high-performance sfall script for <b>Fallout 2</b> (and fan-made games built on its engine) that introduces modern control customization, smart UI menu toggles and efficient key remapping with zero input latency.
</p>

---

## 📋 Key Features

* **⚡ Instant Key Remapping:** Easily rebind keys without input lag or duplicate actions.
* **🧠 Smart UI Toggles:** Re-press any menu key (Inventory, Skilldex, Pip-Boy) to instantly close it.
* **🔑 Global Exit Key:** Set a single master key (e.g., <code>TAB</code> or <code>Q</code>) to close any open UI screen.
* **➕ Additional Binds:** Dedicated keybinds to End Combat, Accept prompts, and "Take All" from containers.
* **🛡️ Context-Aware:** Suspends bindings based on context (e.g., in text fields), preventing unintended inputs.

---

## 📦 Installation

### 📌 Prerequisites
* **[sfall](https://github.com/sfall-team/sfall)** (v3.8.40 or higher) must be installed in your Fallout 2 root directory (`ddraw.dll` present).

### 🗃️ Directory Structure

<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;To install the mod manually or include it in your mod manager, structure your Fallout 2 directory as follows:
</p>

```text
Fallout 2/
└── 📁 mods/
    └── 📁 InterfaceExtender/
        ├── 📝 InterfaceExtender.ini
        ├── ⚖️ LICENSE.txt
        ├── 📖 README.txt
        ├── 📁 presets/
        │   └── 📄 InterfaceExtender_Modern.ini
        └── 📁 scripts/
            └── ⚙️ gl_interface_extender.int
```

*\* Note: The available presets can be used as a foundation for your own custom settings.*

### 📝 Mod Activation

<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Open your sfall mod loading file (<code>mods_order.txt</code> or <code>mods_order.ini</code> inside your <code>mods/</code> folder) and add the mod folder name on a new line:
</p>

```text
InterfaceExtender
```

---

## ⚙️ Configuration (<small>`InterfaceExtender.ini`</small>)

### 🔍 INI Search Hierarchy
  1. `mods\InterfaceExtender\InterfaceExtender.ini`
  2. `mods\InterfaceExtender.ini`
  3. `config\InterfaceExtender\InterfaceExtender.ini`
  4. `config\InterfaceExtender.ini`
  5. `data\scripts\InterfaceExtender.ini`
  6. `InterfaceExtender.ini`

### ⌨️ Available Keys for .INI Configuration

| Category | Supported Syntax (Fallout 2 uses the US Keyboard Layout) |
| :---: | :--- |
| **Numbers** | `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`, `0` |
| **Functions** | `F1`, `F2`, `F3`, `F4`, `F5`, `F6`, `F7`, `F8`, `F9`, `F10`, `F11`, `F12` |
| **Letters** | `A`, `B`, `C`, `D`, `E`, `F`, `G`, `H`, `I`, `J`, `K`, `L`, `M`, `N`, `O`, `P`, `Q`, `R`, `S`, `T`, `U`, `V`, `W`, `X`, `Y`, `Z` |
| **Movement** |  `UP`, `DOWN`, `LEFT`, `RIGHT`, `INSERT`, `DELETE`, `HOME`, `END`, `PAGEUP`, `PAGEDOWN` |
| **Numpad** | `NUMPAD0-9`, `MULTIPLY` (`*`), `NUMLOCK`, `SUBTRACT`, `ADD` (`+`), `DECIMAL`, `NUMPADEQUALS`, `NUMPADENTER`, `NUMPADCOMMA`, `DIVIDE` |
| **Symbols** | `MINUS` (`-`), `EQUALS` (`=`), `LBRACKET` (`[`), `RBRACKET` (`]`), `SEMICOLON` (`;`), `APOSTROPHE` (`'`), `GRAVE` (`` ` ``) `BACKSLASH` (`\`), `COMMA` (`,`), `PERIOD` (`.`), `SLASH` (`/`), `LESS` (`<`), `COLON` (`:`), `UNDERLINE` (`_`) |
| **Special** | `ESCAPE`, `BACKSPACE`, `TAB`, `ENTER`, `LCONTROL`, `LSHIFT`, `RSHIFT`, `LALT`, `SPACEBAR`, `CAPSLOCK`, `SCROLLLOCK`, `RCTRL`, `PRINTSCREEN`, `RALT`, `PAUSE`, `LWIN`, `RWIN`, `APPS` |

> [!WARNING]
> Always place key-disabling entries at the very bottom of your section, after all custom key rebinds.
> Syntax: `KEY_NAME = DISABLED`.

### 🗒️ InterfaceExtender.ini (Example)
```ini
[Modules]
; Enables the built-in key rebinder (configures keys defined in the [KeyMap] section below).
; Options: 1 = Enabled, 0 = Disabled
KeysRemapper=1


[General]
; Note: To disable any shortcut in this section, leave its value empty (e.g., AdditionalCloseKey=).
; These shortcuts function independently of any custom bindings set in [KeyMap].

; Adds a secondary shortcut to close all open menus (Inventory, Character Screen, Loot, etc.).
; Recommended: 'TAB' (same as in the modern fallout games).
AdditionalCloseKey=TAB

; Adds a secondary shortcut to confirm or accept prompts and dialogs.
; Recommended: 'E' (same as in the modern fallout games).
AdditionalAcceptKey=

; Adds a secondary shortcut to end combat.
; Recommended: Set to the same key used to start combat or any preferred shortcut.
AdditionalEndCombatKey=G

; Customizes the "Take All" key in the loot interface.
; Recommended: 'R' (same as in the modern fallout games).
; Note: By engine default, "Take All" inherits whatever key is bound to 'Start Combat' (default 'A').
TakeAllKey=


[KeyMap]
; Format: PHYSICAL_KEY = TARGET_KEY
; Example: Rebinding WASD movement
W = Up    ; Move screen Up
S = Down  ; Move screen Down
A = Left  ; Move screen Left
D = Right ; Move screen Right

; Format: PHYSICAL_KEY = DISABLED
; Example: Disabling Save & Load Game keys
F4 = Disabled ; Save Game
F5 = Disabled ; Load Game

```

---

## 🛠️ Compiling from Source

1. Ensure the `headers` folder (containing `sfall.h` and `dik.h`) is placed in the same directory as your `src` folder.
2. Open `gl_interface_extender.ssl` in Fallout Script Editor and compile it (**F8** / **Compile**).
3. Move the compiled `gl_interface_extender.int` file to `mods/InterfaceExtender/scripts/`.
4. Move, also, `InterfaceExtender.ini` to a valid path (e.g., `mods/InterfaceExtender/`).

---

## 📜 License & Permissions

&nbsp;&nbsp;&nbsp;&nbsp;This project is released under custom terms. Please see the [LICENSE.txt](LICENSE.txt) file for full details regarding personal use, redistribution, and attribution.
