# Asphyxia Core Arch Linux Package

Arch Linux PKGBUILD for Asphyxia Core.

## Usage

```bash
pkgctl build
pacman -U <pkgname>.pkg.tar.zst
systemctl start asphyxia-core@<port>.service
```

> User data saved in %S/asphyxia-core, for most systemd distro, it is /var/lib/asphyxia-core.
