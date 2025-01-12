# Maintainer: avimitin <dev@avimit.in>

pkgname=asphyxia-core
pkgver=v1.50
pkgrel=1
pkgdesc='Asyphyxia Core w/ all plugins'
arch=('x86_64')
_core_url="https://github.com/asphyxia-core/asphyxia-core.github.io/releases/download/${pkgver}/asphyxia-core-linux-x64.zip"
_plugin_rev="9fa01f4104df8583b43c16665176bb1764409705"
source=(
  "${pkgname}-${pkgver}.zip::${_core_url}"
  "${pkgname}-plugin::git+https://github.com/asphyxia-core/plugins#commit=${_plugin_rev}"
  "asphyxia-core.service"
)
sha256sums=('9d02e367907dcf367c06e2d79070053c35e039966c220d1913aeeb1bd4f15fc0'
            'c0efb6abe9c3860cf2d99ea965f5c117bf4062c15af69b362477a4df7d06dba4'
            '12c649cc1bc27693121740c19ed2c9edb53abc9fa6ecd949519cf08898264ce8')
makedepends=('git')

package () {
  install -Dm755 "${srcdir}/asphyxia-core" "${pkgdir}/usr/bin/asphyxia-core"

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
    install -dm755 "${srcdir}/${pkgname}-plugin/${plug_dir}" "${pkgdir}/usr/share/asphyxia-core/plugins/${plug_dir}"
  done

  install -Dm644 "${srcdir}/asphyxia-core.service" "${pkgdir}/usr/lib/systemd/system/asphyxia-core.service"
}

