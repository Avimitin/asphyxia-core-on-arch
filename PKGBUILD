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
  "${pkgname}-plugin::git+https://github.com/asphyxia-core/plugins#commit=${_plugin_rev}"
  "asphyxia-core.service"
  "config.ini.example"
)
sha256sums=('9d02e367907dcf367c06e2d79070053c35e039966c220d1913aeeb1bd4f15fc0'
            'c0efb6abe9c3860cf2d99ea965f5c117bf4062c15af69b362477a4df7d06dba4'
            'e2ab167af0801260f7b5134188fe0acc879521b5c39ee949167741d053920b50'
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
  local install_plugin=(
    "bst@asphyxia"
    "ddr@asphyxia"
    "gitadora@asphyxia"
    "jubeat@asphyxia"
    "mga@asphyxia"
    "museca@asphyxia"
    "nostalgia@asphyxia"
    "popn-hello@asphyxia"
    "popn@asphyxia"
    "sdvx@asphyxia"
  )
  for plug_dir in "${install_plugin[@]}"; do
    mv "${srcdir}/${pkgname}-plugin/${plug_dir}" "${pkgdir}/opt/${_proj}/plugins"
  done

  install -vDm644 "${srcdir}/asphyxia-core.service" "${pkgdir}/usr/lib/systemd/system/${pkgname}.service"
  install -vDm644 "${srcdir}/config.ini.example" "${pkgdir}/opt/${_proj}/config.ini"
}

