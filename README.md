# Independent taskbar per monitor

A [Windhawk](https://windhawk.net) mod for Windows 11 multi-monitor setups: **every taskbar acts like
its own main taskbar.**

*Deutsche Beschreibung weiter unten.*

## Features

- **Only its own windows:** each taskbar shows only the windows on its own monitor. When a window is
  dragged to another monitor, its button slides in sideways on the new taskbar.
- **Own pins per taskbar:** right-click on the taskbar you want → *Pin to taskbar* / *Unpin from
  taskbar* only applies to that taskbar. No Explorer restart, the pin order stays unchanged.
- **Own pin properties per taskbar:** right-click a pin → right-click the app name → *Properties* only
  changes the pin of that taskbar (e.g. Steam with `steam://open/friends` on one monitor and the normal
  Steam window on another).
- **Bring running apps to the front:** clicking the pin of an app that is already running brings its
  window to the front instead of starting a second instance.
- **Fixes a Windows bug** where a re-shown window's taskbar button stays narrow with a cut-off label.

## Settings

| Setting | Options |
|---|---|
| Windows on the taskbar | own monitor only · primary taskbar shows all · all taskbars show all |
| Programs on all taskbars | list of programs (e.g. `discord.exe`) whose windows appear everywhere |
| Pins | own pins per taskbar · same pins everywhere |
| Unassigned pins | primary taskbar only · all taskbars |
| Bring running apps to the front | on/off, from any monitor or only from the clicked taskbar's monitor |
| Slide in sideways | on/off |
| Ctrl+click menu | on/off |
| Configure the taskbar settings automatically | on/off |
| Diagnostic log | on/off |

## Installation

Once the mod is available in the Windhawk catalog: Windhawk → *Explore* → search for
**Independent taskbar per monitor** → *Install*.

Until then:
1. Install and open [Windhawk](https://windhawk.net).
2. Click **Create a new mod**.
3. Replace the example code with the contents of
   [`taskbar-independent-per-monitor.wh.cpp`](taskbar-independent-per-monitor.wh.cpp).
4. Click **Compile Mod**, then **Exit Editing Mode**.

The mod sets *Show my taskbar on all displays* = on and *When using multiple displays, show my taskbar
apps on* = All taskbars itself and restores the previous values when it's disabled or removed.

**Uninstall:** Windhawk → the mod → **Remove**.

## Notes

- Windows 11 taskbar only (tested with 25H2 and *Combine taskbar buttons: Never*).
- Not compatible with the Windows 10 taskbar (ExplorerPatcher, "Windows 10 taskbar on Windows 11").
- *Disable grouping on the taskbar* changes the same parts of the taskbar and isn't needed on Windows 11.

---

## Deutsch

Windhawk-Mod für Windows 11 mit mehreren Monitoren: **Jede Taskleiste verhält sich wie eine eigene
Hauptleiste.**

- Jede Leiste zeigt nur die Fenster ihres Monitors.
- **Eigene Pins pro Leiste:** „An Taskleiste anheften“ / „Von Taskleiste lösen“ per Rechtsklick gilt nur
  für die Leiste, auf der man klickt.
- **Eigene Eigenschaften pro Leiste:** Rechtsklick auf den Pin → Rechtsklick auf den App-Namen →
  „Eigenschaften“ ändert nur den Pin dieser Leiste.
- **Laufende App nach vorn holen** statt sie ein zweites Mal zu starten.
- Einstellbar: welche Fenster jede Leiste zeigt, Programme auf allen Leisten, eigene oder gemeinsame Pins.

**Installieren:** In Windhawk unter *Erkunden* nach „Eigenständige Taskleiste pro Monitor“ suchen, oder
bis dahin: *Neue Mod erstellen* → Inhalt von `taskbar-independent-per-monitor.wh.cpp` einfügen →
*Mod kompilieren* → *Editor beenden*. Die nötigen Windows-Einstellungen setzt die Mod selbst und stellt
beim Entfernen die vorherigen Werte wieder her.

**Deinstallieren:** In Windhawk bei der Mod auf *Entfernen* klicken.

## License

[MIT](LICENSE)
