#!/bin/bash

# Created from the original PKGBUILD by Guillaume Horel <guillaume.horel@gmail.com>, Caleb Maclennan <caleb@alerque.com> and William Turner <willtur.will@gmail.com>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/python-pyclipper/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/python-pyclipper/discussions>

_langname="python"
_relname="MutatorMath"
_pacname="mutatormath"

pkgname="${_langname}-${_pacname}"
pkgver=3.0.1
pkgrel=2
pkgdesc="Piecewise linear interpolation of multiple, arbitrarily placed, masters"
arch=(
  "any"
)
url="https://github.com/LettError/MutatorMath"
license=(
  "BSD"
)
depends=(
  "python"
  "python-defcon"
  "python-fontmath"
  "python-fonttools"
)
makedepends=(
  "python-setuptools"
)
_zipname="${_relname}-${pkgver}"
source=(
  "https://files.pythonhosted.org/packages/source/${_relname::1}/${_relname}/${_zipname}.zip"
)
sha512sums=(
  "9f0af87f4811b27dd3b0e791a230fe0fa1e90e9605673d8753fb3966155483a37fd126646e4deeae79233e8ecc22ee042ae5f985a1bdc5e2696997eff444b801"
)

build() {

  cd "${_zipname}"

  python setup.py build
}

check() {

  cd "${_zipname}"

  python setup.py test
}

package() {

  cd "${_zipname}"

  python setup.py install --root="${pkgdir}" --optimize=1 --skip-build

  install -Dm0644 -t "${pkgdir}/usr/share/licenses/${pkgname}/" LICENSE
}
