# Maintainer: Pritunl <contact@pritunl.com>

pkgname=pritunl-dev
_pkgname=pritunl
pkgver=1.3.613.97beta1
pkgrel=1
pkgdesc="Enterprise VPN Server (Development Release)"
arch=("any")
license=("custom")
url="https://github.com/${_pkgname}/${_pkgname}"
depends=(
    "python"
    "python2"
    "python2-flask"
    "python2-pyopenssl"
    "python2-pymongo"
    "net-tools"
    "iproute2"
    "openvpn"
)
optdepends=(
    "mongodb"
)
makedepends=(
    "python2-distribute"
    "python2-flask"
    "python2-pyopenssl"
    "python2-pymongo"
)
provides=("${_pkgname}")
conflicts=("${_pkgname}")
install=${_pkgname}.install
source=("${url}/archive/${pkgver}.tar.gz")
sha256sums=("5b870ecd5f7d6ab1ba924e6b28c4a080776c3a53dcd66f6eabc2886a8ae28ea3")
options=("emptydirs")
backup=(
    "etc/${_pkgname}.conf"
    "var/lib/${_pkgname}/${_pkgname}.db"
    "var/log/${_pkgname}.log"
    "var/log/${_pkgname}.log.1"
)

build() {
    cd "${srcdir}/${_pkgname}-${pkgver}"
    python2 setup.py build
}

package() {
    cd "${srcdir}/${_pkgname}-${pkgver}"
    mkdir -p "${pkgdir}/var/lib/${_pkgname}"
    python2 setup.py install --root="${pkgdir}" --prefix=/usr --no-upstart
}
