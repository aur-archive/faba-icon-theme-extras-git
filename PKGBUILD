# Maintainer: Martin Wimpress <code@flexion.org>

_pkgname=faba-icon-theme-extras
pkgname=${_pkgname}-git
pkgver=1.85137c5
pkgrel=2
pkgdesc="Extra icons for Faba icon theme."
arch=('any')
url="http://mokaproject.com/faba-icon-theme/"
license=('GPL3')
depends=('faba-icon-theme' 'gtk-update-icon-cache')
makedepends=('git')
conflicts=("${_pkgname}")
provides=("${_pkgname}")
replaces=("${_pkgname}")
options=(!strip)
source=(${_pkgname}::"git+https://github.com/moka-project/${_pkgname}.git")
sha256sums=('SKIP')
install=${_pkgname}.install

pkgver() {
    cd ${srcdir}/${_pkgname}
    echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

package() {
    rm -f "${pkgdir}"/usr/share/icons/Faba/index.theme
    install -d -m 755 "${pkgdir}"/usr/share/icons/Faba
    cp -dr --no-preserve=ownership "${_pkgname}"/Faba "${pkgdir}"/usr/share/icons/
    find "${pkgdir}"/usr/share/icons/ -type d -exec chmod 755 {} \;
    find "${pkgdir}"/usr/share/icons/ -type f -exec chmod 644 {} \;
}
