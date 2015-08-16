# Maintainer: Maxime Gauduin <alucryd@gmail.com>

pkgname=light-locker
pkgver=1.4.0
pkgrel=1
pkgdesc='A simple locker forked from gnome-screensaver'
arch=('i686' 'x86_64')
url='https://github.com/the-cavalry/light-locker'
license=('GPL2')
depends=('gtk3' 'libxxf86misc' 'lightdm' 'libxss' 'upower')
makedepends=('gnome-common' 'intltool')
source=("https://github.com/the-cavalry/${pkgname}/releases/download/v${pkgver}/${pkgname}-${pkgver}.tar.bz2")
sha256sums=('560f20390b24513d5bf7b691bac5d745b76eb21ac3bccd877b73cb7f6d137ec3')

build () {
  cd ${pkgname}-${pkgver}

  ./configure --prefix='/usr' --sysconfdir='/etc' --localstatedir='/var' --disable-{schemas-compile,static} --with-{mit-ext,systemd,upower,xf86gamma-ext,x} --without-console-kit
  make
}

package() {
  cd ${pkgname}-${pkgver}

  make DESTDIR="${pkgdir}" install
}

# vim: ts=2 sw=2 et:
