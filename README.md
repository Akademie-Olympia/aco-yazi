# Yazi configuration

Terminal file manager with the Catppuccin Mocha flavor and optional shell directory tracking.

**[Documentation](https://aco-docs.readthedocs.io/en/latest/yazi/)** ·
[Guide](https://aco-docs.readthedocs.io/en/latest/yazi/guide/) ·
[Design & dependencies](https://aco-docs.readthedocs.io/en/latest/yazi/design/) ·
[Installation and updates](https://aco-arch-dotfiles.readthedocs.io/en/latest/arch-package/)

```bash
curl -fsSL https://raw.githubusercontent.com/Akademie-Olympia/aco-arch-dotfiles/main/install.sh | bash -s -- yazi
```

Package: `aco-arch-dotfiles-yazi`. This standalone repository holds the development sources and the package recipe in
`packaging/arch/PKGBUILD`. The documentation of this component lives in the shared
[aco-docs](https://github.com/Akademie-Olympia/aco-docs) repository (one Read the Docs project for all small components).
Push to `main`; after a successful registry build update with `sudo pacman -Syu`. Details and local builds: [PACKAGING.md](PACKAGING.md).

### Customisation

`yazi.toml` controls behaviour, `theme.toml` the theme and `flavors/` holds the bundled flavor. Start with `yazi`; the Zsh function `y` optionally changes into the last visited directory.

Your own changes in the activated user copy survive synchronisation; new differing defaults appear as `.pacnew`.
See [update and recovery](https://aco-arch-dotfiles.readthedocs.io/en/latest/verification/).

[![Package safety](https://github.com/Akademie-Olympia/aco-yazi/actions/workflows/package.yml/badge.svg)](https://github.com/Akademie-Olympia/aco-yazi/actions/workflows/package.yml)

[MIT licence](LICENSE).
