# Änderungen – Taskbar Monitor Pins

## 1.4.0 – 27.09.2026
- **Neuer Name:** „Independent taskbar per monitor“ (deutsch: „Eigenständige Taskleiste pro Monitor“),
  Mod-ID `taskbar-independent-per-monitor`, Autor 2ndSky95. Vorbereitet für den offiziellen Windhawk-Katalog.
- **Neue Einstellungen:**
  - *Fenster auf der Taskleiste:* nur eigener Monitor / Hauptleiste zeigt alle / alle Leisten zeigen alles.
  - *Programme auf allen Taskleisten:* Liste von Programmen (z.B. `discord.exe`), deren Fenster überall erscheinen.
  - *Pins:* eigene Pins pro Leiste oder überall dieselben Pins.
  - *Welche Fenster nach vorn geholt werden:* von jedem Monitor oder nur vom Monitor der angeklickten Leiste.
- Einstellungen, Beschreibung und Strg+Klick-Menü auf Englisch und Deutsch (Windhawk zeigt automatisch die
  passende Sprache). Code-Kommentare und Log auf Englisch.
- Verknüpfungs-Kopien pro Leiste liegen jetzt im Speicherordner der Mod (Windhawk räumt ihn beim Entfernen
  selbst auf) statt in `%APPDATA%\SkyTaskbarPins`.
- Verträglichkeit geprüft (645 Mods): keine gleichartige Mod vorhanden; Hinweis zu „Disable grouping on the
  taskbar“ und zur Windows-10-Taskleiste in der Beschreibung.

## 1.3.0 – 27.09.2026
- **Einstellungen in Windhawk wieder sichtbar:** Statt „Mod-Einstellungen nicht verfügbar“ zeigt der Reiter
  „Einstellungen“ jetzt alle Optionen (der Einstellungsblock war für Windhawk falsch abgeschlossen).
- **Beschreibung mit Anleitung** auf der Windhawk-Detailseite (Installieren, Deinstallieren, Hinweise).
- **Sauberes Entfernen:** Beim „Entfernen“ in Windhawk stellt die Mod die vorherigen Taskleisten-Einstellungen
  sicher wieder her (Werte werden jetzt im Speicher gehalten, weil Windhawk den Mod-Speicher vorher löscht) und
  löscht ihre Verknüpfungs-Kopien (`%APPDATA%\SkyTaskbarPins`).
- Option „Taskleisten-Einstellungen automatisch setzen“ ausschalten stellt die vorherigen Werte sofort wieder her.
- Ordner „Zum Weitergeben“ mit der Mod-Datei und einer kurzen Anleitung.

## 1.2.2 – 27.09.2026
- **Abgeschnittenes Label behoben:** Wurde Steam (oder eine andere App, die ihr Fenster beim Schließen nur
  versteckt) wieder geöffnet, blieb der Button auf der Leiste in Pin-Breite stehen – nur Symbol und ein
  abgeschnittener Buchstabe. Ursache ist ein Windows-Fehler (tritt auch ohne Mod auf): Die Leiste verwendet den
  alten Pin-Button wieder und berechnet seine Breite nicht neu. Die Mod lässt die Breite jetzt neu berechnen.

## 1.2.1 – 27.09.2026
- **Fokus-Fehler behoben:** War die Steam-Freundesliste über M1 offen, holte ein Klick auf Steam auf M2 nur die
  Freundesliste nach vorn, statt Steam zu öffnen. Hat eine App auf einer Leiste eigene Einstellungen, holt der Pin
  jetzt nur Fenster auf seinem eigenen Monitor nach vorn – sonst startet er die App ganz normal.

## 1.2.0 – 27.09.2026
- **Eigenschaften pro Leiste:** Rechtsklick auf einen Pin → in der Jump List Rechtsklick auf den App-Namen →
  „Eigenschaften“ ändert jetzt nur den Pin dieser Leiste (z.B. Steam auf M1 mit `steam://open/friends`, Steam auf
  M2 normal). Die Mod legt dafür je Leiste eine eigene Kopie der Verknüpfung an
  (`%APPDATA%\SkyTaskbarPins\M<Nummer>\`) und startet beim Klick auf den Pin diese Kopie, sobald sie geändert wurde.
- Pins mit eigenem Start-Befehl (Argumente) starten immer normal, statt nur ein laufendes Fenster nach vorn zu holen.
- Hinweis: Ein geändertes Symbol in den Eigenschaften wird auf der Leiste nicht angezeigt (Windows nimmt das
  Symbol der App).

## 1.1.2 – 27.09.2026
- **Kein Umsortieren mehr beim Anheften:** Wurde eine App, die schon auf einer anderen Leiste angeheftet ist,
  per Rechtsklick zusätzlich angeheftet, nahm Windows' Pin-Verwaltung sie aus der Liste und hängte sie hinten
  wieder an – sie rutschte auf allen Leisten ans Ende. Die Mod erledigt das jetzt selbst
  (`PinManager::PinItemFromTrustedCaller` abgefangen), die Pin-Reihenfolge bleibt unverändert.
- Hinweis: Bereits verschobene Pins bleiben, wo sie sind – einfach einmal per Ziehen zurechtrücken.

## 1.1.0 – 27.09.2026
- **Fehler behoben:** Hat eine App Fenster auf mehreren Monitoren (Steam + Freundesliste, WhatsApp + Anruf,
  mehrere Editor-Fenster), erschienen alle ihre Fenster auf jeder dieser Leisten. Jetzt filtert die Mod dort,
  wo auch Windows selbst filtert (`IsTaskAllowed`) – jede Leiste zeigt nur die Fenster ihres Monitors.
- **Animation rein seitlich:** Beim Verschieben gleitet der Button jetzt waagerecht herein, ohne Anteil von
  unten – auch beim Verschieben auf die Hauptleiste.
- **Kein Doppel-Symbol mehr** beim Wechsel Fenster ↔ Pin auf derselben Leiste (Fenster schließen oder auf einen
  anderen Monitor ziehen): das Symbol bleibt ruhig stehen, nur die Beschriftung verschwindet.
- Hinweis: Beim Öffnen einer angehefteten App taucht die Beschriftung kurz ohne Symbol von unten auf – das macht
  Windows im Modus „nie zusammenfassen“ auch ohne Mod so.
- Schutz gegen Absturzschleifen: startet der Explorer mehrmals kurz nacheinander neu, schaltet die Mod ihre
  riskanten Teile bis zum nächsten Update selbst ab.

## 1.0.0 – 27.09.2026
- **Anheften/Lösen per Rechtsklick pro Leiste:** „An Taskleiste anheften“ heftet nur auf dieser Leiste an,
  auch wenn die App schon auf einer anderen angeheftet ist. „Von Taskleiste lösen“ löst nur auf dieser Leiste;
  erst auf der letzten Leiste wird die App wirklich gelöst.
- Fehler behoben: Anheften auf M1/M3 wurde von Windows sofort wieder rückgängig gemacht.
- **Kein Explorer-Neustart** mehr bei Pin-Änderungen (Registry-Überwachung entfernt).
- **Kein Flackern** beim Verschieben: nur die alte Leiste wird aufgeräumt.
- **Seitliches Hereingleiten** statt „von unten auftauchen“, wenn ein Fenster den Monitor wechselt.
- **Start-Abgleich:** nach Explorer-Start und Mod-Update werden Pins und Fenster aller Leisten geprüft und
  korrigiert (behebt Geister-Pins und „alle Pins überall“ bei spät geladener Mod).
- Fokus-Funktion findet jetzt auch Fenster gepackter Apps (z.B. Windows-Editor).
- Neue Einstellungen: Seitlich hereingleiten, Pins ohne Zuordnung (Hauptleiste/alle), Strg+Klick-Menü an/aus,
  Taskleisten-Einstellungen automatisch setzen (mit Wiederherstellung beim Entfernen der Mod).
- Einstellungsliste „Pins pro Monitor“ entfernt (ersetzt durch Rechtsklick).

## 0.8.7 – 27.09.2026
- Absturz beim Neuladen der Mod behoben (WinEvent-Hook wurde im falschen Thread entfernt).
