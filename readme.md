# Asphyxia Core Arch Linux Package

Arch Linux PKGBUILD for Asphyxia Core.

## Usage

```bash
pkgctl build
pacman -U <pkgname>.pkg.tar.zst
vim /opt/asphyxia/config.ini
systemctl start asphyxia-core.service
```

## Additional notes
* User data saved in /opt/asphyxia/savedata.
* Plugin saved in /opt/asphyxia/plugins.
* This package doesn't ship with default plugin in official repository because the default sdvx, gitadora plugin are outdated.
* **Make sure the service is stop before you update config**: This is because asphyxia-core always found config at binary current directory
and I hate running asphyxia-core with root account, so all data are copy and override to a private bind mount directory.
And this workaround leads to an issue that the new file will be overwritten when stop.
