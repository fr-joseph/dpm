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

Compile a manifest file to a raw list of package names:

```bash
dpm-compile-manifest packages.md packages.txt
```

Print help:

```bash
dpm-help
```

Install a package via pacman and enable/stow it:

```bash
dpm-install htop
```

Install a package via yay and enable/stow it:

```bash
dpm-install-aur neovim-remote
```

List installed packages, enabled and available:

```bash
dpm-ls
```

Process a raw package list, running a function on each line:

```bash
dpm-process-package-list packages.txt dpm-install
dpm-process-package-list packages.txt dpm-unstow
```

Enable/stow a package:

```bash
dpm-stow htop
```

Enable/stow all packages:

```bash
dpm-stow-all
```

Unstow/disable and uninstall a package:

```bash
dpm-uninstall htop
```

Unstow/disable a package:

```bash
dpm-unstow htop
```

Unstow/disable all packages:

```bash
dpm-unstow-all
```
