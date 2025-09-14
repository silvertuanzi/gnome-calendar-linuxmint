48.1 is gtk4 version.

Linuxmint 22.2 patched libadwaita to support mint-themes. However, libadwaita on ArchLinux isn't patched.

So use [libadwaita-without-adwaita](https://aur.archlinux.org/packages?O=0&K=libadwaita-without-adwaita) to support mint themes. Or just use 41.2 version by `git checkout`.

This newest version only add support [gnome-online-accounts-gtk](https://aur.archlinux.org/packages/gnome-online-accounts-gtk). This package provided by Arch requires `gnome-control-center` to manage online accounts.

If you don't need this, just use the version in Arch official repository.
