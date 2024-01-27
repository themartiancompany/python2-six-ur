# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: 0b100100 <0b100100 at protonmail dot ch>
# Contributor: Felix Yan <felixonmars@archlinux.org>
# Contributor: Jelle van der Waa <jelle@vdwaa.nl>
# Contributer: Allan McRae <allan@archlinux.org>

_pkg="six"
_py='python2'
pkgname="${_py}-${_pkg}"
pkgver=1.16.0
pkgrel=6
pkgdesc="Python 2 and 3 compatibility utilities"
arch=(
  'any'
)
url="https://pypi.python.org/pypi/${_pkg}"
license=('MIT')
makedepends=(
  "${_py}-setuptools"
)
# checkdepends=(
#   "${_py}-pytest"
#   "tk"
# )
_pypi="https://pypi.io/packages/source"
source=(
  "${_pypi}/${_pkg::1}/${_pkg}/${_pkg}-${pkgver}.tar.gz"
)
sha512sums=(
  '076fe31c8f03b0b52ff44346759c7dc8317da0972403b84dfe5898179f55acdba6c78827e0f8a53ff20afe8b76432c6fe0d655a75c24259d9acbaa4d9e8015c0'
)

build() {
  cd \
    "${_pkg}-${pkgver}"
  "${_py}" \
    setup.py \
      build
}

# check() {
#   cd "six-$pkgver"
#   "${_py}" \
#     -m \
#       pytest
# }

package() {
  cd \
    "${_pkg}-${pkgver}"
  "${_py}" \
    setup.py \
      install \
        --root="${pkgdir}" \
	--optimize=1 \
	--skip-build
  install \
    -Dm644 \
    LICENSE \
    -t \
    "${pkgdir}/usr/share/licenses/${pkgname}"
}

# vim:set sw=2 sts=-1 et:
