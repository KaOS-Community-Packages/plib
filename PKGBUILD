pkgname=plib
pkgver=1.8.5
pkgrel=1
pkgdesc="Set of libraries to write games and other realtime interactive applications"
arch=('x86_64')
url="http://plib.sourceforge.net/"
license=('custom:LGPL')
makedepends=('libgl' 'libxi' 'libxmu')
source=("http://plib.sourceforge.net/dist/${pkgname}-${pkgver}.tar.gz")
md5sums=('47a6fbf63668c1eed631024038b2ea90')

build() {
  export CFLAGS="-fPIC ${CFLAGS}"
  export CPPFLAGS="-fPIC ${CFLAGS}"
  export CXXFLAGS="-fPIC ${CFLAGS}"
  cd ${srcdir}/$pkgname-$pkgver
  ./configure --prefix=/usr
  make
}

package() {
  cd ${srcdir}/$pkgname-$pkgver

  make DESTDIR="${pkgdir}" install
  install -D -m644 COPYING ${pkgdir}/usr/share/licenses/$pkgname/COPYING
}
