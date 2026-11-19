# Yazi configuration

Terminal-Dateimanager mit Catppuccin-Mocha-Flavor und optionalem Shell-Verzeichniswechsel.

**[Dokumentation](https://aco-arch-dotfiles.readthedocs.io/en/latest/components/#yazi)** ·
[Shell-Integration](https://aco-arch-dotfiles.readthedocs.io/en/latest/shell/) ·
[Installation und Updates](https://aco-arch-dotfiles.readthedocs.io/en/latest/arch-package/)

```bash
curl -fsSL https://raw.githubusercontent.com/Akademie-Olympia/aco-arch-dotfiles/main/install.sh | bash -s -- yazi
```

Paket: `aco-arch-dotfiles-yazi`. Dateien: `~/.config/yazi/yazi.toml`, `theme.toml`,
`package.toml` und `flavors/`. `yazi` startet den Dateimanager; die Zsh-Funktion `y`
übernimmt anschließend das zuletzt besuchte Verzeichnis.

Hier unabhängig auf `main` pushen; nach erfolgreichem Registry-Build mit
`sudo pacman -Syu` aktualisieren. [PACKAGING.md](PACKAGING.md).

### Anpassung

`yazi.toml` steuert das Verhalten, `theme.toml` das Theme und `flavors/` enthält die mitgelieferte Flavor. Mit `yazi` starten; die Zsh-Funktion `y` übernimmt optional das zuletzt besuchte Verzeichnis.

Eigene Änderungen in der aktivierten Benutzerkopie bleiben bei der Synchronisierung erhalten; neue abweichende Vorgaben erscheinen als `.pacnew`. Siehe [Update und Wiederherstellung](https://aco-arch-dotfiles.readthedocs.io/en/latest/verification/).

[![Package safety](https://github.com/Akademie-Olympia/aco-yazi/actions/workflows/package.yml/badge.svg)](https://github.com/Akademie-Olympia/aco-yazi/actions/workflows/package.yml)

[MIT-Lizenz](LICENSE); die mitgelieferte Flavor behält ihre eigenen Lizenzen.
