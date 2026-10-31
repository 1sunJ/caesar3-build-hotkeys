# Caesar III Build Hotkeys for Augustus

**English** | [한국어](README.ko.md)

A modified build of [Augustus](https://github.com/Keriew/augustus), the enhanced open-source Caesar III engine, that adds keyboard build hotkeys.
It uses the same key layout as the Julius build hotkeys mod, so you can switch between the two engines without relearning anything.

```
A → 3        Fountain
G → 1 → 5    Small temple of Mars
H            Housing
B            Roadblock
```

It is based on Augustus `master` at commit [`13ad05a`](https://github.com/Keriew/augustus/commit/13ad05ab4182c335e9739e1687ae6376b7229ab6) (2026-10-30).
The last official release, 4.0.0, dates from December 2023, so the current development version was used to get the newest features and complete translations.
The in-game version string is `4.0.0.359-13ad05a`.

## Features

1. **Category keys**: one key opens a sidebar build menu (water, health, religion, …).
2. **Pick items with numbers**: while a build menu is open, press a key on the number row to select that item. For submenus such as temples or farms, keep typing numbers.
3. **Menu numbers**: each menu item shows its key after the name, like `(3)`.
4. **Sidebar labels**: each sidebar build button shows its key in the bottom-right corner.

No gameplay rules are changed. For save compatibility see [Saves](#saves).

## Default hotkeys

| Category | Key | Category | Key |
|---|---|---|---|
| Housing | `H` | Education | `S` |
| Clear land | `X` | Entertainment | `N` |
| Road | `R` | Administration | `V` |
| Water | `A` | Engineering | `E` |
| Health | `K` | Military | `M` |
| Religion | `G` | Industry | `I` |
| **Roadblock** | `B` | | |

- Housing, clear land, road and roadblock select the build tool directly.
- Every key can be changed in the game. See [Settings](#settings).

### Differences from the Julius mod

| Item | Details |
|---|---|
| `Shift`+`R` rotate building | Stock Augustus uses `R` to rotate buildings. It moves to `Shift`+`R` so that `R` can be the road key. |
| `Shift`+`X` mothball building | Stock Augustus uses `X` to mothball/enable a building. It moves to `Shift`+`X` so that `X` can be the clear land key. |
| `B` roadblock | Julius has no roadblock, so this key is new. |
| `-` `=` | Augustus menus can have more than 10 items, so the 11th and 12th items use `-` and `=` on the number row. |
| First submenu item | Submenus such as small temples, large temples, altars and trees start with "Auto cycle". That makes the small temple of Mars `G` → `1` → `5`. |

All other stock Augustus hotkeys, such as `Q` (clone the building under the cursor), are unchanged.

### Inside a menu

| Key | Action |
|---|---|
| `1`–`9`, `0` (numpad too) | Pick the 1st–10th item |
| `-`, `=` | Pick the 11th and 12th item |
| Same category key | Close the menu |
| Another category key | Switch to that menu |
| `H` `X` `R` `B` | Close the menu and pick housing, clear land, road or roadblock |
| `Esc` / right click | Close the menu |

When no menu is open, the number keys open the advisors as before.

### Menu order

This is the order when every building is allowed. **Buildings the current mission doesn't allow are hidden, and the numbers count only the visible items**, so go by the number shown on screen.

| Menu (key) | Items |
|---|---|
| Water (`A`) | 1 Reservoir · 2 Aqueduct · 3 Fountain · 4 Well |
| Health (`K`) | 1 Barber · 2 Baths · 3 Doctor · 4 Hospital · 5 Latrine |
| Religion (`G`) | 1 Small temples ▶ · 2 Large temples ▶ · 3 Grand temple ▶ · 4 Altar ▶ · 5 Lararium · 6 Oracle · 7 Small mausoleum · 8 Large mausoleum · 9 Nymphaeum |
| Education (`S`) | 1 School · 2 Academy · 3 Library · 4 Mission post |
| Entertainment (`N`) | 1 Theater · 2 Amphitheater · 3 Arena · 4 Tavern · 5 Colosseum · 6 Hippodrome · 7 Actor colony · 8 Gladiator school · 9 Lion house · 0 Chariot maker |
| Administration (`V`) | 1 Gardens ▶ · 2 Trees ▶ · 3 Paths ▶ · 4 Parks ▶ · 5 Statues ▶ · 6 Governor's mansions ▶ · 7 Plaza · 8 Forum · 9 Senate · 0 City mint · `-` Triumphal arch |
| Engineering (`E`) | 1 Engineer's post · 2 Low bridge · 3 Ship bridge · 4 Shipyard · 5 Dock · 6 Wharf · 7 Work camp · 8 Architects' guild · 9 Lighthouse · 0 Highway station |
| Military (`M`) | 1 Palisade · 2 Watchtower · 3 Wall · 4 Tower · 5 Gatehouse · 6 Prefecture · 7 Fort ▶ · 8 Barracks · 9 Supply post · 0 Armory · `-` Military academy |
| Industry (`I`) | 1 Farms ▶ · 2 Raw materials ▶ · 3 Workshops ▶ · 4 Market · 5 Granary · 6 Warehouse · 7 Cart depot · 8 Caravanserai |

▶ marks a submenu. In-game names depend on your language.

The sidebar road button opens a menu with road, highway and roadblock, and the clear land button opens clear land and repair area. `R` and `X` pick road and clear land directly. To get keys for highway and repair area too, assign them to "Highway" and "Repair area" in the hotkey settings.
## Installation

**Requirements**: the original Caesar III game files (Steam, GOG or CD, with the 1.0.1.0 patch).

1. Close the game.
2. Unzip `augustus-build-hotkeys-13ad05a.zip` to any folder. Use a **new folder** rather than unzipping over another Augustus installation.
3. Run `augustus.exe`.
4. On first launch, choose the folder that contains the Caesar III data files. For the Steam version it is usually:
   ```
   C:\Program Files (x86)\Steam\steamapps\common\Caesar 3\C3
   ```
   If you have run Augustus before, it remembers that folder and won't ask.

The `assets` folder must stay next to `augustus.exe`. Don't mix it with the `assets` folder of another Augustus version.

### Language

Choose the language in *Options → General settings*. Augustus ships with translations for many languages. For Korean, Chinese or Japanese, the game folder needs the matching localized Caesar III data or font patch, as with stock Augustus.

### Saves

- Saves from older Augustus versions, Julius and the original Caesar III load fine.
- Saves made with this build **may not open in older Augustus versions** (for example 4.0.0), because the development version keeps updating the save format. Back up your saves if you might go back.

## Uninstall

Delete the folder you unzipped. Other Augustus versions ignore the extra settings entries, so you can leave them.

## Settings

Settings are stored under `%APPDATA%\augustus\augustus\` (hotkeys: `augustus-hotkeys.ini`).

- **Turn the shortcuts on or off**: in *Options → User Interface → City View*, check or uncheck "Enable build menu shortcuts". Turning it off removes the sidebar labels, menu numbers and number-key selection. The category keys (`A`, `G`, …) keep working.
  (`ui_enable_build_menu_shortcuts=1` / `0` in `augustus.ini`. This is an existing Augustus option; this build only turns it on by default.)
- **Change keys**: open *Options → Hotkeys* and find the build entries. A changed key shows up on the sidebar buttons right away.

### If you already customized your hotkeys

The new keys are added automatically even if `augustus-hotkeys.ini` already exists. However, **keys already used by another action are never taken over**, and those entries stay empty. For example, if your old file saved `R` as rotate building, the road key stays empty. Assign such keys yourself in the hotkey settings, or press "Reset to defaults".

## Troubleshooting

| Problem | What to check |
|---|---|
| DLL error right after starting | Make sure `SDL2.dll` and `SDL2_mixer.dll` are in the same folder as `augustus.exe` |
| Broken graphics or missing new buildings | Make sure this package's `assets` folder is next to `augustus.exe` |
| A key doesn't open its menu | Like the sidebar button, a menu won't open if the current mission allows nothing in it. Menus also don't open while you are dragging to build something |
| Numbers don't pick menu items | Check that "Enable build menu shortcuts" is on in *Options → User Interface → City View* |
| Garbled text | Check the language setting and, for Korean/Chinese/Japanese, that the localized game files are in the game folder |

## Building from source

For those who want to build `augustus.exe` themselves. (Windows, 64-bit)

**Requirements**: Git, Visual Studio 2022 (Desktop development with C++ workload), CMake 3.15 or newer

The already-patched source is also available as the `build-hotkeys` branch of [1sunJ/augustus](https://github.com/1sunJ/augustus). Instead of step 1 you can run `git clone -b build-hotkeys https://github.com/1sunJ/augustus.git augustus`.

Run these commands in this `augustus` folder:

```bash
# 1. Get the Augustus source, check out the base commit and apply the patch
git clone https://github.com/Keriew/augustus.git
cd augustus
git checkout 13ad05ab4182c335e9739e1687ae6376b7229ab6
git apply ../patch/augustus-13ad05a-build-hotkeys.patch

# 2. Extract the SDL2 development files under ext/SDL2
#    https://github.com/libsdl-org/SDL/releases/tag/release-2.32.8        → SDL2-devel-2.32.8-VC.zip
#    https://github.com/libsdl-org/SDL_mixer/releases/tag/release-2.8.1   → SDL2_mixer-devel-2.8.1-VC.zip
#    Result: ext/SDL2/SDL2-2.32.8/, ext/SDL2/SDL2_mixer-2.8.1/

# 3. Build (links the C runtime statically, so no VC++ redistributable is needed)
cd ..
cmake -S augustus -B build -G "Visual Studio 17 2022" -A x64 \
  -DCMAKE_POLICY_VERSION_MINIMUM=3.5 \
  -DCMAKE_MSVC_RUNTIME_LIBRARY=MultiThreaded
cmake --build build --config Release
```

The result is `build/Release/augustus.exe`. To run it, put these next to it:

- `lib/x64/SDL2.dll` and `lib/x64/SDL2_mixer.dll` from the SDL2 packages
- the source's `res/assets` folder, named `assets`

`CMAKE_POLICY_VERSION_MINIMUM=3.5` is only needed with CMake 4.x. You can drop it on older versions.
Linux and macOS builds follow Augustus's [build guide](https://github.com/Keriew/augustus/blob/master/doc/BUILDING.md). The patch applies on any platform.

### Changed source files

| File | Change |
|---|---|
| `src/core/hotkey_config.c/.h` | 9 new category hotkeys and their defaults; rotate building and mothball moved to `Shift`; hotkey file version 2 adds the new defaults to existing files |
| `src/input/hotkey.c/.h` | Category key handling; number row and numpad keys pick menu items while a build menu is open |
| `src/window/build_menu.c` | Picking items and switching menus by key; housing, clear land, road and roadblock keys inside a menu |
| `src/graphics/text.c/.h` | Menu labels for the 11th and 12th items (`-`, `=`) |
| `src/window/city.c/.h` | Opening build menus with category keys |
| `src/widget/sidebar/city.c` | Key labels on the sidebar build buttons |
| `src/core/config.c` | "Enable build menu shortcuts" on by default |
| `src/window/hotkey_config.c` | Category entries in the hotkey settings screen |

The category names come from the game's own sidebar tooltips, so no translation files were changed.

## Package contents

```
augustus-build-hotkeys-13ad05a/
├── augustus.exe                             Modified executable (64-bit)
├── SDL2.dll                                 SDL 2.32.8
├── SDL2_mixer.dll                           SDL_mixer 2.8.1
├── assets/                                  Augustus graphics and sounds (as of 13ad05a)
├── augustus-13ad05a-build-hotkeys.patch     Source changes
├── README.md                                This document (English)
├── README.ko.md                             Korean version
└── licenses/
    ├── Augustus-LICENSE.txt                 GNU AGPL v3
    ├── SDL2-LICENSE.txt                     zlib License
    └── SDL2_mixer-LICENSE.txt               zlib License
```

## License

- Augustus is licensed under the **GNU AGPL v3**, and so is this modified build. Its complete source is Augustus commit [`13ad05a`](https://github.com/Keriew/augustus/tree/13ad05ab4182c335e9739e1687ae6376b7229ab6) with the included `augustus-13ad05a-build-hotkeys.patch` applied. If you redistribute this program, include the patch file (or the modified source).
- The graphics and sounds in the `assets` folder belong to the Augustus project and are covered by `assets/LICENSE`.
- SDL2 and SDL2_mixer are under the zlib license.
- No Caesar III game data (graphics, sounds, maps, …) is included; it belongs to its original copyright holders. Please buy the game.

This is not an official Augustus release. Please don't contact the Augustus developers about problems with this build.
