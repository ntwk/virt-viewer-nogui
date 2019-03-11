# virt-viewer-nogui

This repository contains an Arch Linux `PKGBUILD` and patch for
virt-viewer.  The purpose of the patch is to hide the user interface
GTK widgets present in the upstream version of virt-viewer.

## Installation

Clone this repository and then build the package using the Arch Linux
`makepkg` utility.

It may be necessary to first import the upstream author's public key
to your keyring in order for `makepkg` to verify the integrity of the
source via the `.asc` signature file.

    'gpg --recv-key <keyID>'

Where `keyID` consists of the low 64 bits of the public key
fingerprint which is found in the `validpgpgkeys` field of the
`PKGBUILD`.

> Source: https://tools.ietf.org/html/rfc4880#section-12.2

## Usage

The viewer itself is run using the `remote-viewer` command.

With the GUI widgets no longer visible, be sure to specify the
keyboard shortcut to toggle fullscreen mode:

    'remote-viewer --hotkeys=toggle-fullscreen=shift+f11'

## Theming

The background canvas color of the main viewer window relies on your
system's GTK 3 theme.  A dark theme variant may be preferred and can
be specified on the command line via the `GTK_THEME` environment
variable:

    'GTK_THEME=Adwaita:dark remote-viewer'
