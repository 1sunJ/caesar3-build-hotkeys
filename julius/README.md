# Caesar III Build Hotkeys for Julius

**English** | [한국어](README.ko.md)

A modified build of [Julius](https://github.com/bvschaik/julius) **1.8.0**, the open-source Caesar III engine, that adds keyboard build hotkeys.
You can pick every building with the keyboard alone, without clicking the sidebar buttons.

```
A → 3        Fountain
G → 1 → 4    Small temple of Mars
H            Housing
```

## Features

1. **Category keys**: one key opens a sidebar build menu (water, health, religion, …).
2. **Pick items with numbers**: while a build menu is open, press `1`–`9` to select that item. For submenus such as temples or farms, keep typing numbers.
3. **Menu numbers**: each build menu item shows its number on the left.
4. **Sidebar labels**: each sidebar build button shows its key in the bottom-right corner.

No gameplay rules are changed, so **saves stay fully compatible with the original Julius 1.8.0 and the original Caesar III.**

## Default hotkeys

| Category | Key | Category | Key |
|---|---|---|---|
| Housing | `H` | Education | `S` |
| Clear land | `X` | Entertainment | `N` |
| Road | `R` | Administration | `V` |
| Water | `A` | Engineering | `E` |
| Health | `K` | Military | `M` |
| Religion | `G` | Industry | `I` |

- Housing, clear land and road have no submenu, so their keys select the build tool directly.
- The keys don't overlap the existing ones (overlays `W` `F` `D` `C` `T`, pause `P`, legions `L`, clone, …).
- Every key can be changed in the game. See [Settings](#settings).

### Inside a menu

| Key | Action |
|---|---|
| `1`–`9` (numpad too) | Pick the n-th item |
| Same category key | Close the menu |
| Another category key | Switch to that menu |
| `H` `X` `R` | Close the menu and pick housing, clear land or road |
| `Esc` / right click | Close the menu |

When no menu is open, the number keys open the advisors as before.

### Menu order

This is the order when every building is allowed. **Buildings the current mission doesn't allow are hidden, and the numbers count only the visible items**, so go by the number shown on screen.

| Menu (key) | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
|---|---|---|---|---|---|---|---|---|---|
| Water (`A`) | Reservoir | Aqueduct | Fountain | Well | | | | | |
| Health (`K`) | Barber | Baths | Doctor | Hospital | | | | | |
| Religion (`G`) | Small temples ▶ | Large temples ▶ | Oracle | | | | | | |
| Education (`S`) | School | Academy | Library | Mission post | | | | | |
| Entertainment (`N`) | Theater | Amphitheater | Colosseum | Hippodrome | Gladiator school | Lion house | Actor colony | Chariot maker | |
| Administration (`V`) | Forum | Senate | Governor's house | Governor's villa | Governor's palace | Small statue | Medium statue | Large statue | Triumphal arch |
| Engineering (`E`) | Gardens | Plaza | Engineer's post | Low bridge | Ship bridge | Shipyard | Dock | Wharf | |
| Military (`M`) | Wall | Tower | Gatehouse | Prefecture | Fort ▶ | Military academy | Barracks | | |
| Industry (`I`) | Farms ▶ | Raw materials ▶ | Workshops ▶ | Market | Granary | Warehouse | | | |

▶ marks a submenu. For example, the small temples submenu (`G` → `1`) lists Ceres, Neptune, Mercury, Mars and Venus in that order.

## Installation

**Requirements**: the original Caesar III game files (Steam, GOG or CD, with the 1.0.1.0 patch). If you already use Julius, use that same folder.

1. Close the game.
2. Open the game folder. For the Steam version it is usually:
   ```
   C:\Program Files (x86)\Steam\steamapps\common\Caesar 3\C3
   ```
3. If `julius.exe`, `SDL2.dll` or `SDL2_mixer.dll` are already there, **rename them as a backup** (for example `julius.exe.bak`).
4. Copy these 3 files from the package into the game folder:
   - `julius.exe`
   - `SDL2.dll`
   - `SDL2_mixer.dll`
5. Run `julius.exe`.

### Running it from Steam's Play button

Steam's Play button runs `c3.exe` in the game folder. To start this build from it:

1. Rename the original `c3.exe` to `c3.exe.bak`.
2. Copy this package's `julius.exe` and rename the copy to `c3.exe`.

Steam's "Verify integrity of game files" may restore the original `c3.exe`. If that happens, replace it again.

### Other languages

The mod uses whatever language your Caesar III data is in. The one new setting is translated into English and Korean; other languages show it in English.
Korean players need the Julius Korean patch (`korean-v2.555` and the Korean language files) in the game folder, as with the original Julius.

## Uninstall

1. Delete the copied `julius.exe`, `SDL2.dll` and `SDL2_mixer.dll`.
2. Rename your backups back to their original names.

The extra entries in the settings file are ignored by the original Julius, so you can leave them.

## Settings

Open the Julius configuration screen from the main menu or the in-game options menu.

- **Show or hide the labels**: check or uncheck "Show hotkeys on build buttons and menus". Turning it off only hides the sidebar labels and menu numbers; the hotkeys keep working.
  (`ui_show_build_hotkeys=1` / `0` in `julius.ini`)
- **Change keys**: open *Configure hotkeys* at the bottom of the configuration screen and find the build entries. A changed key shows up on the sidebar buttons right away.
- **Clear keys**: keys you clear there stay cleared after saving.

### If you already customized your hotkeys

The new category keys are added automatically even if `julius-hotkeys.ini` already exists. However, **keys already used by another action are never taken over**; those entries stay empty and you can assign them yourself in the hotkey settings.

## Troubleshooting

| Problem | What to check |
|---|---|
| A message says the original game files are needed | Make sure `julius.exe` is in the folder with the Caesar III data files (`c3.eng`, `C3.sg2`, …) |
| DLL error right after starting | Make sure `SDL2.dll` and `SDL2_mixer.dll` were copied too |
| A key doesn't open its menu | Like the sidebar button, a menu won't open if the current mission allows nothing in it. Menus also don't open while you are dragging to build something |
| Garbled Korean text | Check that the Julius Korean patch files are in the game folder and the language is set to Korean |

## Building from source

For those who want to build `julius.exe` themselves. (Windows, 32-bit)

**Requirements**: Git, Visual Studio 2022 (Desktop development with C++ workload), CMake 3.15 or newer

The already-patched source is also available as the `build-hotkeys` branch of [1sunJ/julius](https://github.com/1sunJ/julius). Instead of step 1 you can run `git clone -b build-hotkeys https://github.com/1sunJ/julius.git julius`.

Run these commands in this `julius` folder:

```bash
# 1. Get the Julius 1.8.0 source and apply the patch
git clone https://github.com/bvschaik/julius.git
cd julius
git checkout v1.8.0
git apply ../patch/julius-1.8.0-build-hotkeys.patch

# 2. Extract the SDL2 development files under ext/SDL2
#    https://github.com/libsdl-org/SDL/releases/tag/release-2.32.8        → SDL2-devel-2.32.8-VC.zip
#    https://github.com/libsdl-org/SDL_mixer/releases/tag/release-2.8.1   → SDL2_mixer-devel-2.8.1-VC.zip
#    Result: ext/SDL2/SDL2-2.32.8/, ext/SDL2/SDL2_mixer-2.8.1/

# 3. Build (links the C runtime statically, so no VC++ redistributable is needed)
cd ..
cmake -S julius -B build -G "Visual Studio 17 2022" -A Win32 \
  -DCMAKE_POLICY_VERSION_MINIMUM=3.5 \
  -DCMAKE_POLICY_DEFAULT_CMP0091=NEW \
  -DCMAKE_MSVC_RUNTIME_LIBRARY=MultiThreaded
cmake --build build --config Release
```

The result is `build/Release/julius.exe`. To run it, put `lib/x86/SDL2.dll` and `lib/x86/SDL2_mixer.dll` from the SDL2 packages next to it.

- `CMAKE_POLICY_VERSION_MINIMUM=3.5` is only needed with CMake 4.x. You can drop it on older versions.
- MinGW, Linux and macOS builds follow Julius's [build guide](https://github.com/bvschaik/julius/blob/master/doc/BUILDING.md). The patch applies on any platform.

### Changed source files

| File | Change |
|---|---|
| `src/core/hotkey_config.c/.h` | 9 new category hotkeys, their defaults, and adding new defaults to existing hotkey files |
| `src/input/hotkey.c/.h` | Category key handling; number keys pick menu items while a build menu is open |
| `src/window/build_menu.c` | Picking items and switching menus by key; item numbers |
| `src/window/city.c/.h` | Opening build menus with category keys |
| `src/widget/sidebar/city.c` | Key labels on the sidebar build buttons |
| `src/core/config.c/.h`, `src/window/config.c` | "Show hotkeys" setting |
| `src/window/hotkey_config.c` | Category entries in the hotkey settings screen |
| `src/translation/*` | Setting text (English, Korean) |

## Package contents

```
julius-build-hotkeys-1.8.0/
├── julius.exe                           Modified executable (32-bit)
├── SDL2.dll                             SDL 2.32.8
├── SDL2_mixer.dll                       SDL_mixer 2.8.1
├── julius-1.8.0-build-hotkeys.patch     Source changes (against Julius v1.8.0)
├── README.md                            This document (English)
├── README.ko.md                         Korean version
└── licenses/
    ├── Julius-LICENSE.txt               GNU AGPL v3
    ├── SDL2-LICENSE.txt                 zlib License
    └── SDL2_mixer-LICENSE.txt           zlib License
```

## License

- Julius is licensed under the **GNU AGPL v3**, and so is this modified build. Its complete source is [Julius v1.8.0](https://github.com/bvschaik/julius/tree/v1.8.0) with the included `julius-1.8.0-build-hotkeys.patch` applied. If you redistribute this program, include the patch file (or the modified source).
- SDL2 and SDL2_mixer are under the zlib license.
- No Caesar III game data (graphics, sounds, maps, …) is included; it belongs to its original copyright holders. Please buy the game.

This is not an official Julius release. Please don't contact the Julius developers about problems with this build.
