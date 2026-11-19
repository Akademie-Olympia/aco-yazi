# Installation

## Installieren

::::{tab-set}
:::{tab-item} Installer
```bash
curl -fsSL https://raw.githubusercontent.com/Akademie-Olympia/aco-arch-dotfiles/main/install.sh | bash -s -- yazi
```
:::
:::{tab-item} pacman
Wenn das Repository schon eingerichtet ist (`aco-arch-dotfiles` Installer):

```bash
sudo pacman -S aco-arch-dotfiles-yazi
aco install yazi
```
:::
::::

Der Installer prüft den Signierschlüssel, richtet das Pacman-Repository ein,
installiert `aco-arch-dotfiles-yazi` samt Abhängigkeiten und aktiviert die Konfiguration. Bestehende
Dateien werden vorher gesichert.

## Aktualisieren

```bash
sudo pacman -Syu        # oder: aco update
```

Neue Vorgaben werden mit deinen eigenen Änderungen zusammengeführt. Wo beides
abweicht, legt `aco` eine `.pacnew`-Datei neben deine Datei. Nach Änderungen die
Anwendung neu starten. Yazi neu starten.

## Entfernen

```bash
aco deactivate yazi                 # stellt die gesicherten Einstellungen wieder her
sudo pacman -Rns aco-arch-dotfiles-yazi
```

`pacman` löscht niemals dein Home-Verzeichnis, Backups oder eigene Änderungen.

## Wo liegt was?

| Ort | Inhalt |
| --- | --- |
| `/usr/share/arch-dotfiles/yazi/` | Vorgaben des Pakets (von pacman verwaltet) |
| `~/.local/share/arch-dotfiles/config/yazi/` | Deine bearbeitbare Kopie – hier änderst du |
| `~/.config/yazi` → `yazi.toml`, `theme.toml` | Verknüpfung auf deine Kopie |

`aco path` zeigt das Verzeichnis deiner Kopien. Quellen und Paketrezept:
[`packaging/arch/PKGBUILD`](https://github.com/Akademie-Olympia/aco-yazi/blob/main/packaging/arch/PKGBUILD).
