# Maintainer: SpepS <dreamspepser at yahoo dot it>

_pkgbasename=chuck
pkgname=(bin32-$_pkgbasename-jack)
pkgver=1.2.1.3
pkgrel=4
pkgdesc="Concurrent, on-the-fly audio programming language."
arch=('x86_64')
url="http://chuck.cs.princeton.edu/"
license=('GPL')
depends=('lib32-gcc-libs' 'lib32-libsndfile' 'lib32-jack')
makedepends=('gcc-multilib' 'bison' 'flex')
provides=('chuck-jack')
conflicts=('chuck-jack')
source=(http://chuck.cs.princeton.edu/release/files/$_pkgbasename-$pkgver.tgz)
md5sums=('ac8459b4067c2491fbdeb61d122a5985')

build() {

  export CC='gcc -m32'
  export CXX='g++ -m32'

  cd $srcdir/$_pkgbasename-$pkgver/src
  CFLAGS="$CFLAGS -fno-strict-aliasing"
	
  # This can be linux-alsa linux-jack linux-oss osx win32
  make linux-jack
}

package() {

  cd $srcdir/$_pkgbasename-$pkgver/src
  install -D -m 755 chuck $pkgdir/usr/bin/chuck-jack
}
