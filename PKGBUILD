# Maintainer: Pier Luigi Fiorini <pierluigi.fiorini@gmail.com>
# Contributor: Lukas Jirkovsky <l.jirkovsky@gmail.com>

pkgname=xf86-video-intel-xwayland-git2
pkgver=0.0.0
pkgrel=2
pkgdesc="X.org Intel video drivers for XWayland"
arch=('i686' 'x86_64')
url="http://wayland.freedesktop.org/"
license=('MIT')
depends=('weston' 'wayland' 'xwayland-git')
makedepends=('randrproto' 'inputproto' 'dri2proto' 'xf86driproto' 'xf86dgaproto' 'libxxf86dga' 'resourceproto' 'scrnsaverproto' 'git' 'xorg-util-macros')
conflicts=('xf86-video-intel')
provides=('xf86-video-intel')
source=(git://anongit.freedesktop.org/xorg/driver/xf86-video-intel#branch=xwayland)
md5sums=('SKIP')

pkgver() {
  cd xf86-video-intel
  git describe --always | sed 's|-|.|g' 
}

build() {
  cd xf86-video-intel
  CFLAGS="-w" ./autogen.sh --prefix=/usr/ \
    --enable-dri \
    --with-default-accel=sna
  make
}

package() {
  cd xf86-video-intel
  make DESTDIR="${pkgdir}" install
}
