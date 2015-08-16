# Maintainer : Martin Wimpress <code@flexion.org>
# Contributor: Giovanni Ricciardi <kar98k.sniper@gmail.com>

pkgname=mate-window-manager
pkgver=1.6.2
pkgrel=4
pkgdesc="A window manager for MATE"
url="http://mate-desktop.org"
arch=('i686' 'x86_64' 'armv6h' 'armv7h')
license=('GPL')
depends=('gtk2' 'libcanberra' 'libgtop' 'libice' 'libsm' 'libxt' 'mate-desktop'
         'mate-dialogs' 'startup-notification')
makedepends=('mate-common' 'mate-doc-utils' 'perl-xml-parser')
options=('!emptydirs')
groups=('mate')
source=("http://pub.mate-desktop.org/releases/1.6/${pkgname}-${pkgver}.tar.xz")
sha1sums=('dce0fd1953d75b4aad88d4818228eac677fb1d7b')
install=${pkgname}.install

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    ./configure \
        --prefix=/usr \
        --sysconfdir=/etc \
        --localstatedir=/var \
        --enable-startup-notification \
        --disable-static \
        --disable-scrollkeeper
    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" install
}
