pkgname=koompi-xf86-input-libinput
pkgver=1.0.1
pkgrel=1
pkgdesc="Generic input driver for the X.Org server based on libinput"
arch=('x86_64')
license=('custom')
url="http://xorg.freedesktop.org/"
depends=('koompi-libinput')
makedepends=('xorg-server-devel' 'libxi' 'libx11' 'xorgproto')
optdepends=('xorg-xinput: input configuration for X')
conflicts=('xorg-server<1.19.0' 'X-ABI-XINPUT_VERSION<24' 'X-ABI-XINPUT_VERSION>=25')
provides=('xf86-input-libinput')
conflicts=('xf86-input-libinput')
groups=('xorg-drivers')
source=("git+https://gitlab.freedesktop.org/xorg/driver/xf86-input-libinput")
sha512sums=('SKIP')
validpgpkeys=('SKIP')

build() {
  cd xf86-input-libinput

  ./autogen.sh  --prefix=/usr \
                --disable-static
  make
}

package() {
  cd xf86-input-libinput

  make DESTDIR="${pkgdir}" install

  install -m755 -d "${pkgdir}/usr/share/licenses/xf86-input-libinput"
  install -m644 COPYING "${pkgdir}/usr/share/licenses/xf86-input-libinput/"
}
