# Maintainer: avimitin <dev@avimit.in>

_proj=asphyxia
pkgname=asphyxia-core
pkgver=v1.50
pkgrel=1
pkgdesc='Asyphyxia Core w/ all plugins'
arch=('x86_64')
url="https://asphyxia-core.github.io"
_core_url="https://github.com/asphyxia-core/asphyxia-core.github.io/releases/download/${pkgver}/asphyxia-core-linux-x64.zip"
_plugin_rev="9fa01f4104df8583b43c16665176bb1764409705"
source=(
  "${pkgname}-${pkgver}.zip::${_core_url}"
  "asphyxia-core.service"
  "config.ini.example"
)
sha256sums=('9d02e367907dcf367c06e2d79070053c35e039966c220d1913aeeb1bd4f15fc0'
            'e726061cab91edd0e2aa50c11dd742b79d67872bb2e13897b78807b10d34f2e1'
            'd460cc135a833bbd462d6b983bb2e56ec78182ead76c7b41421df0addc8adbe5')
depends=(
  'glibc'
  'gcc-libs'
)
options=(!strip staticlibs !docs)
makedepends=('git')
install=asphyxia-core.install

package () {
  install -vDm755 "${srcdir}/asphyxia-core" "${pkgdir}/opt/${_proj}/${pkgname}"

  install -vd "${pkgdir}/opt/${_proj}/plugins"
  install -vd "${pkgdir}/opt/${_proj}/savedata"

  install -vDm644 "${srcdir}/asphyxia-core.service" "${pkgdir}/usr/lib/systemd/system/${pkgname}.service"
  install -vDm644 "${srcdir}/config.ini.example" "${pkgdir}/opt/${_proj}/config.ini"
}

