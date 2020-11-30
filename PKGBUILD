# Maintainer: Raphiel Rollerscaperers <raphielscape@raphielgang.org>
# Based on PKGBUILD from: Timofey Titovets <nefelim4ag@gmail.com>

pkgname=raph-ananicy-git
pkgver=2.11.r0.g2d474a9
pkgrel=1
pkgdesc="Ananicy - is Another auto nice daemon, with community rules support"
arch=('any')
url="https://github.com/raphielscape/Ananicy.git"
license=('GPL3')
depends=('systemd' 'bash' 'schedtool' 'python')
makedepends=('git' 'make')
source=("$pkgname"::'git+https://github.com/raphielscape/Ananicy.git#branch=master')
md5sums=('SKIP')
install=$pkgname.install
backup=( 'etc/ananicy.d/ananicy.conf' )

pkgver() {
  cd "$pkgname"
  git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

package() {
  cd "$srcdir/${pkgname}/"
  make install PREFIX="$pkgdir"
  mkdir -p "$pkgdir/usr/"
  mv -v "$pkgdir/lib" "$pkgdir/usr/"
}
