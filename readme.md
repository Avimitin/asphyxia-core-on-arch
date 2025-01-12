# Asphyxia Core Arch Linux Package

Arch Linux PKGBUILD for Asphyxia Core.

## Usage

```bash
pkgctl build
pacman -U <pkgname>.pkg.tar.zst
systemctl start asphyxia-core@<port>.service
```

> User data saved in %S/asphyxia-core, for most systemd distro, it is /var/lib/asphyxia-core.

## Additional notes

This package already shipped all asphyxia plugins.
If you are not satisfied with the big package, you can comment out the corresponding PKGBUILD install script:

```diff
--- a/PKGBUILD
+++ b/PKGBUILD
@@ -21,15 +21,15 @@ package () {
   install -Dm755 "${srcdir}/asphyxia-core" "${pkgdir}/usr/bin/asphyxia-core"

   local install_plugin=(
-    "bst@asphyxia"
-    "ddr@asphyxia"
+    # "bst@asphyxia"
+    # "ddr@asphyxia"
     "gitadora@asphyxia"
-    "jubeat@asphyxia"
-    "mga@asphyxia"
-    "museca@asphyxia"
-    "nostalgia@asphyxia"
-    "popn-hello@asphyxia"
-    "popn@asphyxia"
+    # "jubeat@asphyxia"
+    # "mga@asphyxia"
+    # "museca@asphyxia"
+    # "nostalgia@asphyxia"
+    # "popn-hello@asphyxia"
+    # "popn@asphyxia"
     "sdvx@asphyxia"
   )
   for plug_dir in "${install_plugin[@]}"; do
```
