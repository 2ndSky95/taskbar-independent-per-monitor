# Independent taskbar per monitor

A [Windhawk](https://windhawk.net) mod for Windows 11 multi-monitor setups: **every taskbar acts like
its own main taskbar.**

![Each taskbar shows only the windows of its own monitor](images/windows-per-monitor.png)

![Separate pinned items for each taskbar](images/pins-per-taskbar.png)

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
| Slide animation | on/off |
| Show taskbar apps on all taskbars | required for the mod; applied internally, your Windows setting isn't changed |

## Installation

Once the mod is available in the Windhawk catalog: Windhawk → *Explore* → search for
**Independent taskbar per monitor** → *Install*.

Until then:
1. Install and open [Windhawk](https://windhawk.net).
2. Click **Create a new mod**.
3. Replace the example code with the contents of
   [`taskbar-independent-per-monitor.wh.cpp`](taskbar-independent-per-monitor.wh.cpp).
4. Click **Compile Mod**, then **Exit Editing Mode**.

*Show my taskbar on all displays* must be enabled. The mod shows taskbar apps on all taskbars
internally while it's running; the *When using multiple displays, show my taskbar apps on* setting
isn't changed.

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
*Mod kompilieren* → *Editor beenden*. „Taskleiste auf allen Anzeigen anzeigen“ muss an sein. Die Einstellung
„Apps anzeigen auf“ ändert die Mod nicht, sie wirkt nur intern, solange die Mod läuft.

**Deinstallieren:** In Windhawk bei der Mod auf *Entfernen* klicken.

## License

[MIT](LICENSE)
