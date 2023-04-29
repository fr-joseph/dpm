# Dynamic Package Manager (DPM)

dpm is a package management tool for Arch Linux, wrapping GNU stow, pacman and yay.

it's functionality is split into many small "dpm-" binaries

## OVERVIEW

all packages are installed to "/stow" rather than "/"

they can be dynamically enabled/disabled by stowing/unstowing them to "/"

## MANIFEST FILES

you can stow/unstow/install/uninstall apps from manifest files

these are markdown files, where lines starting with #
are treated as a comment, and every other line is
treated as the name of a package

this allows you to group apps under markdown headings
the process will strip out the headings for you when
manipulating the manifest file

example packages.md file:

```md
# my packages

## media
sxiv
vlc

## web
firefox
qutebrowser
```

will be compiled to:

```
firefox
qutebrowser
sxiv
vlc
```

## USAGE EXAMPLES

`dpm-compile-manifest`

```bash
dpm-compile-manifest packages.md packages.txt
```

`dpm-help`

```bash
dpm-help
```

`dpm-install`

```bash
dpm-install htop
```

`dpm-install-aur`

```bash
dpm-install-aur neovim-remote
```

`dpm-ls`

```bash
dpm-ls
```

`dpm-process-package-list`

```bash
dpm-process-package-list packages.txt dpm-install
dpm-process-package-list packages.txt dpm-unstow
```

`dpm-stow`

```bash
dpm-stow htop
```

`dpm-stow-all`

```bash
dpm-stow-all
```

`dpm-uninstall`

```bash
dpm-uninstall htop
```

`dpm-unstow`

```bash
dpm-unstow htop
```

`dpm-unstow-all`

```bash
dpm-unstow-all
```
