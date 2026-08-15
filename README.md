<p align="center">
  <img src="https://github.com/user-attachments/assets/85c84eb3-1e22-4741-b452-8dd5765b0b07" width="40%" alt="fallout2_logo" />
</p>

<h1 align="center">Key Remapper & Interface Extender</h1>

<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;A lightweight, high-performance sfall script for <b>Fallout 2</b> that introduces modern control customization, smart UI menu toggles, context-aware shortcut protection, and low-level key remapping with zero input latency.
</p>

---

## Key Features

* **⚡ Ultra-Fast `O(1)` Key Remapper**  
  Translates physical keys to target keys using fixed array lookup tables. Native action suppression prevents remapped targets from triggering duplicate inputs.
  
* **🧠 Smart UI Menu Toggles**  
  Re-press the shortcut that opened a menu (Inventory <code>I</code>, Skilldex <code>S</code>, Pip-Boy Clock <code>Z</code>) to instantly close it.

* **🔑 Global Menu Exit Key**  
  Configure a single master key (e.g., <code>TAB</code> or <code>Q</code>) to exit almost any open UI screen (Inventory, Containers, Barter, Save/Load, Character Screen, Automap, Pip-Boy, Options).

* **➕ Additional Action Shortcuts**  
  Dedicated configurable keys for accepting prompts, ending combat turns, and triggering "Take All" in container interfaces.

* **🛡️ Context-Aware Input Protection**  
  Automatically suspends custom shortcuts inside text fields (save game names, numeric quantity inputs) when bound to printable letter/digit keys, preventing accidental UI closing while typing.

* **⚖️ Illegalities Validation**  
  Detects conflicting bindings (e.g., identical Accept and Close bindings) and safely disables the conflict before input loops occur.

---

## 🗃️ Directory Structure

<p align="justify">
To install the mod manually or include it in your mod manager, structure your Fallout 2 directory as follows:
</p>

```text
Fallout 2/
└── 📁 mods/
    └── 📁 InterfaceExtender/
        ├── 📄 InterfaceExtender.ini
        ├── 📁 presets/
        │   └── 📄 InterfaceExtender_MODERN.ini
        └── 📁 scripts/
            └── 📄 gl_interface_extender.int
```
*\* Note: `InterfaceExtender_MODERN.ini` can be used as a foundation for your custom settings.*

## 🔍 INI Search Hierarchy
  1. `mods\InterfaceExtender\InterfaceExtender.ini`
  2. `mods\InterfaceExtender.ini`
  3. `config\InterfaceExtender\InterfaceExtender.ini`
  4. `config\InterfaceExtender.ini`
  5. `data\scripts\InterfaceExtender.ini`
  6. `..\InterfaceExtender.ini`

---

## ⚙️ Configuration (<small>`InterfaceExtender.ini`</small>)

### ⌨️ Available Keys for .INI Configuration

| Category | Supported Syntax |
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

### 📝 InterfaceExtender.ini
```ini
[Modules]
; Enable (1) or Disable (0) the key remapping engine
KeysRemapper=1

[General]
; Master hotkey to exit open UI menus and screens (e.g., TAB, ESC)
; Note: Leave empty to disable
AdditionalCloseKey=TAB

; Secondary key to accept prompts and dialogs (e.g., E, SPACE)
; Note: Leave empty to disable
AdditionalAcceptKey=E

; Secondary key to end combat turn (e.g., G, F)
; Note: Leave empty to disable
AdditionalEndCombatKey=G

; Dedicated key to trigger "Take All" in loot/container windows
; Note: Leave empty to disable
TakeAllKey=R

[KeyMap]
; Format: [PHYSICAL_KEY = TARGET_KEY]
; Example: Rebinding WASD movement
W=UP
A=LEFT
S=DOWN
D=RIGHT

; Format: [PHYSICAL_KEY = DISABLED]
; Example: Disabling Save & Load Game keys
F4 = Disabled ; Save Game
F5 = Disabled ; Load Game

```

---

## 🛠️ Compiling from Source

1. Ensure `sfall.h` and `dik.h` are placed in your Fallout Script Editor's `headers` (or `include`) folder.
2. Open `gl_interface_extender.ssl` in Fallout Script Editor and compile it (**F8** / **Compile**).
3. Move the compiled `gl_interface_extender.int` file to `mods/InterfaceExtender/scripts/`.
4. Move, also, `InterfaceExtender.ini` to a valid path (e.g., `mods/InterfaceExtender/`).

---

## 📜 License & Permissions
<p align="justify"><b>Personal Use:</b> Free to use, modify, and build upon for personal configurations or overhaul mod packs.</p>
<p align="justify"><b>Redistribution:</b> Please do not re-upload standalone copies to external hosts without prior authorization.</p>
<p align="justify"><b>Credits:</b> If reusing core logic or code routines in your own public scripts, please credit <b>GalacticWar</b>.</p>
