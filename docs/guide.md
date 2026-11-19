# Yazi im Alltag

Yazi ist ein schneller Dateimanager im Terminal mit drei Spalten (Eltern · aktueller Ordner · Vorschau).
Er ist auf Tastatur ausgelegt, kennt aber auch die Maus. In ACO startest du ihn mit {kbd}`Super + Y` oder im Terminal mit **`y`**.

## `y` statt `yazi`

Der Zsh-Befehl `y` (aus dem [Zsh-Paket](https://aco-zsh.readthedocs.io/en/latest/)) startet Yazi und wechselt beim Beenden mit {kbd}`q`
**in den Ordner, in dem du gelandet bist**. Mit {kbd}`Q` beendest du, ohne das Verzeichnis zu ändern. So wird Yazi
zum bequemen `cd`: `y`, mit `h j k l` navigieren, `q`.

## Navigation und Dateien

| Taste | Aktion |
| --- | --- |
| {kbd}`h` / {kbd}`l` oder {kbd}`←` / {kbd}`→` | Ordner hoch / hinein (bzw. Datei öffnen) |
| {kbd}`j` / {kbd}`k` oder {kbd}`↓` / {kbd}`↑` | Auswahl bewegen |
| {kbd}`g` {kbd}`g` / {kbd}`G` | Zum Anfang / Ende |
| {kbd}`Space` | Datei markieren (dann auf alle Markierten wirken) |
| {kbd}`y` / {kbd}`x` / {kbd}`p` | Kopieren / ausschneiden / einfügen |
| {kbd}`d` / {kbd}`D` | In den Papierkorb / endgültig löschen |
| {kbd}`a` | Datei anlegen (Endung `/` = Ordner) |
| {kbd}`r` | Umbenennen |
| {kbd}`.` | Versteckte Dateien ein/aus |
| {kbd}`/` / {kbd}`n` / {kbd}`N` | Im Ordner suchen / nächster / voriger Treffer |
| {kbd}`z` | Per **fzf** Datei oder Ordner finden |
| {kbd}`Z` | Per **zoxide** häufig besuchte Ordner anspringen |
| {kbd}`~` oder {kbd}`F1` | Alle Tasten anzeigen |
| {kbd}`q` | Beenden |

Die vollständige Liste zeigt Yazi selbst mit {kbd}`~`; sie ist immer aktuell.

## Was dieses Paket festlegt

`yazi.toml`:

| Einstellung | Wert | Wirkung |
| --- | --- | --- |
| `ratio` | `[1, 3, 4]` | Spaltenbreite: schmale Eltern, mittlerer Ordner, breite Vorschau |
| `sort_by` | `natural` | `file2` vor `file10` |
| `sort_dir_first` | `true` | Ordner zuerst |
| `show_hidden` | `true` | Versteckte Dateien sichtbar |
| `scrolloff` | `5` | Fünf Zeilen Abstand zum Rand beim Scrollen |
| `mouse_events` | Klick, Scroll, Touch, Bewegung, Ziehen | Volle Mausunterstützung |

`theme.toml` wählt das Flavor `catppuccin-mocha` (liegt im Paket unter `flavors/`). `package.toml` hält die Version des Flavors fest
(Yazi-Paketmanager `ya pkg`), damit alles reproduzierbar bleibt.

## Vorschau und Abhängigkeiten

Das Paket installiert, was Yazi für Vorschauen und Suche braucht: `file` (Dateityp), `poppler` (PDF), `imagemagick` (Bilder),
`ffmpeg` (Video), `7zip` (Archive), `fd`/`ripgrep`/`fzf` (Suche), `zoxide` (Ordnersprünge), `jq`. Fehlt eines davon,
fehlt nur die zugehörige Vorschau oder Suchfunktion.

## Typische Änderungen

```toml
# ~/.config/yazi/yazi.toml
[mgr]
show_hidden = false     # Versteckte Dateien erst mit '.'
ratio = [ 1, 2, 3 ]     # breiter Ordner, schmalere Vorschau
```

Eigene Tasten gehören in eine neue Datei `keymap.toml` im selben Ordner.

## Fehlersuche

- **Keine Bildvorschau:** Das Terminal muss Bildprotokolle unterstützen – Kitty und Ghostty tun es, Foot nur eingeschränkt.
- **`y` wechselt den Ordner nicht:** Du startest `yazi` direkt oder bist in einer Shell ohne die ACO-Zsh-Konfiguration.
- **Flavor fehlt:** `ya pkg install` stellt die in `package.toml` festgehaltenen Pakete wieder her.

## Anpassen und zurücksetzen

`~/.config/yazi` ist ein Link auf deine bearbeitbare Kopie unter
`~/.local/share/arch-dotfiles/config/yazi/`. Dort kannst du alles ändern; `pacman -Syu` überschreibt
deine Änderungen **nicht**. Bringt ein Update neue Vorgaben mit, landen sie als `.pacnew`-Datei neben deiner
Version, und du übernimmst, was du willst (`aco sync` führt zusammen, `aco status` zeigt den Zustand).
Zurück zu den Vorgaben: `aco deactivate yazi` stellt die früheren Einstellungen wieder her,
`aco install yazi` aktiviert die Paketvorgaben erneut.
