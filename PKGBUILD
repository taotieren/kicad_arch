# Contributor: taotieren <admin@taotieren.com>

pkgname=bin2hex-git
_pkgname=bin2hex
pkgver=aa6b51a
pkgrel=1
pkgdesc="Convert raw binary files to Intel \"IHEX\" type files (used for loading large chunks of data into an Arduino board)"
arch=('any')
url="https://github.com/krupski/bin2hex"
license=('GPLv3')
provides=(${pkgname})
conflicts=(${pkgname} ${_pkgname})
#replaces=(${pkgname})
depends=('glibc')
makedepends=('git')
backup=()
options=('!strip')
#install=${pkgname}.install
source=("${_pkgname}::git+${url}.git")
sha256sums=('SKIP')

pkgver() {
    cd "${srcdir}/${_pkgname}"
    git describe --always | sed 's|-|.|g'
}

build() {
    cd "${srcdir}/${_pkgname}"
    make
}

package() {
    install -Dm755 "${srcdir}/${_pkgname}/${_pkgname}" "${pkgdir}/usr/bin/${_pkgname}"
    install -Dm644 "${srcdir}/${_pkgname}/LICENSE" "${pkgdir}/usr/share/licenses/${_pkgname}/LICENSE"
}
