<p align="center">
  <img src="https://github.com/user-attachments/assets/85c84eb3-1e22-4741-b452-8dd5765b0b07" width="50%" alt="fallout2_logo" />
</p>

# Key Remapper & Interface Extender

A lightweight, high-performance sfall script for **Fallout 2** that introduces modern control customization, smart UI menu toggles, context-aware shortcut protection, and low-level key remapping with zero input latency.

---

## Key Features

* **$O(1)$ Ultra-Fast Key Remapper**  
  Translates physical keys to target keys using fixed array lookup tables. Native action suppression prevents remapped targets from triggering duplicate inputs.
* **Smart UI Menu Toggles**  
  Re-press the shortcut that opened a menu (Inventory `I`, Skilldex `S`, Pip-Boy Clock `Z`) to instantly close it.
* **Global Menu Exit Key**  
  Configure a single master key (e.g., `TAB` or `ESC`) to exit almost any open UI screen (Inventory, Containers, Barter, Save/Load, Character Screen, Automap, Pip-Boy, Options).
* **Additional Action Shortcuts**  
  Dedicated configurable keys for accepting prompts, ending combat turns, and triggering "Take All" in container interfaces.
* **Context-Aware Input Protection**  
  Automatically suspends custom shortcuts inside text fields (save game names, numeric quantity inputs) when bound to printable letter/digit keys, preventing accidental UI closing while typing.
* **Illegalities Validation**  
  Detects conflicting bindings (e.g., identical Accept and Close bindings) and safely disables the conflict before input loops occur.

---

## Directory Structure

To install the mod manually or include it in your mod manager, structure your Fallout 2 directory as follows:

```text
Fallout 2/
└── mods/
    └── InterfaceExtender/
        ├── InterfaceExtender.ini
        └── scripts/
            └── gl_interface_extender.int
```
INI Search HierarchyThe script dynamically searches for its configuration file in the following order:mods\InterfaceExtender\InterfaceExtender.inimods\InterfaceExtender.iniconfig\InterfaceExtender.iniconfig\InterfaceExtender\InterfaceExtender.inidata\scripts\InterfaceExtender.iniConfiguration (InterfaceExtender.ini)Ini, TOML[Modules]
; Enable (1) or Disable (0) the key remapping engine
KeysRemapper=1

[General]
; Secondary key to end combat turn (e.g., SPACE, RETURN, F1)
AdditionalEndCombatKey=SPACE

; Secondary key to accept prompts and dialogs (e.g., RETURN, SPACE)
AdditionalAcceptKey=RETURN

; Master hotkey to exit open UI menus and screens (e.g., TAB, ESC)
AdditionalCloseKey=TAB

; Dedicated key to trigger "Take All" in loot/container windows
TakeAllKey=A

[KeyMap]
; Format: PHYSICAL_KEY=TARGET_KEY
; Example: Rebinding WASD movement or remapping action keys
W=UP
A=LEFT
S=DOWN
D=RIGHT
G=A

Supported Key Aliases
CategorySupported SyntaxAlphanumericA-Z, 0-9Function KeysF1 through F12NumpadNUMPAD0-NUMPAD9, NUMPADSTAR, NUMPADPLUS, NUMPADMINUS, NUMPADPERIOD, NUMPADSLASH, NUMPADENTERNavigationUP, DOWN, LEFT, RIGHT, HOME, END, PAGEUP (PGUP), PAGEDOWN (PGDN), INSERT (INS), DELETE (DEL)Special KeysESC, TAB, SPACE, ENTER (RETURN), BACKSPACE, CAPS, LCTRL, RCTRL, LSHIFT, RSHIFT, LALT, RALT, PRTSC, PAUSESymbols-, =, [, ], ;, ', `, \, ,, ., /, <, :, _Unbind KeyOFF, NONE, DISABLED, UNBOUND, NULLCompiling from SourceThis script requires the sfall Script Compiler (part of the sfall modding tools or sfall Script Editor).Ensure sfall.h and dik.h are present in your compiler's include directory.Compile gl_interface_extender.ssl:Bashcompile.exe -p gl_interface_extender.ssl
Move the compiled gl_interface_extender.int binary to mods/InterfaceExtender/scripts/.License & PermissionsPersonal Use: Free to use, modify, and build upon for personal configurations or overhaul mod packs.Redistribution: Please do not re-upload standalone copies to external hosts without prior authorization.Credits: If reusing core logic or code routines in your own public scripts, please credit GalacticWar.
