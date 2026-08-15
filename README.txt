================================================================================================================================
|                                               KEY REMAPPER & INTERFACE EXTENDER                                              |  
================================================================================================================================

    A lightweight sfall script for Fallout 2 (and fan-made games built on its engine) that introduces modern control
customization, smart UI menu toggles and efficient key remapping with zero input latency.


--------------------------------------------------------------------------------------------------------------------------------
| 📋 [ KEY FEATURES ]                                                                                                          |
--------------------------------------------------------------------------------------------------------------------------------

* ⚡ Ultra-Fast O(1) Key Remapper
  Translates physical keys to target keys using fixed array lookup tables. Native action suppression prevents remapped targets
  from triggering duplicate inputs.

* 🧠 Smart UI Menu Toggles
  Re-press the shortcut that opened a menu (Inventory 'I', Skilldex 'S', Pip-Boy Clock 'Z') to instantly close it.

* 🔑 Global Menu Exit Key
  Configure a single master key (e.g., TAB or Q) to exit almost any open UI screen (Inventory, Containers, Barter, Save/Load,
  Character Screen, Automap, Pip-Boy, Options).

* ➕ Additional Action Keys
  Dedicated configurable keys for accepting prompts, ending combat, and triggering "Take All" in container interfaces.

* 🛡️ Context-Aware Input Protection
  Automatically suspends custom bindings based on context (e.g., inside text fields for save game names when bound to printable
  letter/digit keys, preventing accidental inputs while typing).

* ⚖️ Illegalities Validation
  Detects conflicting bindings (e.g., identical Accept and Close bindings) and safely disables the conflict before input loops
  occur.


--------------------------------------------------------------------------------------------------------------------------------
| 📦  [ INSTALLATION ]                                                                                                         |
--------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------
| 📌 Prerequisites                                             |
----------------------------------------------------------------

* sfall (v3.8.40 or higher) is installed in your Fallout 2 root directory (ddraw.dll must be present).
  Download: https://github.com/sfall-team/sfall

----------------------------------------------------------------
| 🗃️ Directory Structure                                       |
----------------------------------------------------------------

To install the mod manually or include it in your mod manager, structure your Fallout 2 directory as follows:

Fallout 2/
└── 📁 mods/
    └── 📁 InterfaceExtender/
        ├── 📄 InterfaceExtender.ini
        ├── 📁 presets/
        │   └── 📄 InterfaceExtender_MODERN.ini
        └── 📁 scripts/
            └── 📄 gl_interface_extender.int

ℹ* Note: InterfaceExtender_MODERN.ini can be used as a foundation for your custom settings.


--------------------------------------------------------------------------------------------------------------------------------
| ⚙️ [ CONFIGURATION (InterfaceExtender.ini) ]                                                                                 |
--------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------
| 🔍 [ INI SEARCH HIERARCHY ]                                  |
----------------------------------------------------------------

1. mods\InterfaceExtender\InterfaceExtender.ini
2. mods\InterfaceExtender.ini
3. config\InterfaceExtender\InterfaceExtender.ini
4. config\InterfaceExtender.ini
5. data\scripts\InterfaceExtender.ini
6. ..\InterfaceExtender.ini

----------------------------------------------------------------
| ⌨️ AVAILABLE KEYS FOR .INI CONFIGURATION:                    |
----------------------------------------------------------------

ℹ* Note: Fallout 2 uses the US Keyboard Layout.
--------------------------------------------------------------------------------------------------------------------------------
|                                         ℹ️ AVAILABLE KEYS FOR .INI CONFIGURATION ℹ️                                         |
--------------------------------------------------------------------------------------------------------------------------------
|  Numbers:  1, 2, 3, 4, 5, 6, 7, 8, 9, 0                                                                                      |
| Functions: F1, F2, F3, F4, F5, F6, F7, F8, F9, F10, F11, F12                                                                 |
|  Letters:  A, B, C, D, E, F, G, H, I, J, K, L, M, N, O, P, Q, R, S, T, U, V, W, X, Y, Z                                      |
|  Movement: UP, DOWN, LEFT, RIGHT, INSERT, DELETE, HOME, END, PAGEUP, PAGEDOWN                                                |
|  Numpad:   NUMPAD0-9, MULTIPLY (*), NUMLOCK, SUBTRACT, ADD (+), DECIMAL, NUMPADEQUALS, NUMPADENTER, NUMPADCOMMA, DIVIDE      |
|  Special:  ESCAPE, BACKSPACE, TAB, ENTER, LCONTROL, LSHIFT, RSHIFT, LALT, SPACEBAR, CAPSLOCK, SCROLLLOCK, RCTRL,             |
|              PRINTSCREEN, RALT, PAUSE, LWIN, RWIN, APPS                                                                      |
|  Symbols:  MINUS (-), EQUALS (=), LBRACKET ([), RBRACKET (]), SEMICOLON (;), APOSTROPHE ('), GRAVE (`), BACKSLASH (\),       |
|              COMMA (,), PERIOD (.), SLASH (/), LESS (<), COLON (:), UNDERLINE (_)                                            |
|------------------------------------------------------------------------------------------------------------------------------|
|     ⚠️ WARNING: Always place key-disabling entries at the very bottom of your section, after all custom key rebinds. ⚠️     |
|                                                 Syntax: KEY_NAME = DISABLED.                                                 |
|------------------------------------------------------------------------------------------------------------------------------|

----------------------------------------------------------------
| 📝 InterfaceExtender.ini (Example)                           |
----------------------------------------------------------------

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
AdditionalAcceptKey=E

; Adds a secondary shortcut to end combat.
; Recommended: Set to the same key used to start combat or any preferred shortcut.
AdditionalEndCombatKey=G

; Customizes the "Take All" key in the loot interface.
; Recommended: 'R' (same as in the modern fallout games).
; Note: By engine default, "Take All" inherits whatever key is bound to 'Start Combat' (default 'A').
TakeAllKey=R


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


--------------------------------------------------------------------------------------------------------------------------------
| 📜 [ LICENSE & PERMISSIONS ]                                                                                                 |
--------------------------------------------------------------------------------------------------------------------------------

    This project is released under custom terms. Please see the LICENSE.txt file for full details regarding personal use,
redistribution, and attribution.

