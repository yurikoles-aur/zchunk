# Maintainer: Nikita Puzyryov <PuzyryovN@gmail.com>
pkgname=zchunk
pkgver=1.1.11
pkgrel=1
pkgdesc="A file format that allows easy deltas while maintaining good compression"
arch=(x86 x86_64)
url="https://github.com/zchunk/zchunk"
license=('BSD')
depends=('libcurl.so' 'zstd')
provides=('libzck.so')
makedepends=('meson' 'ninja')
source=("$pkgname-$pkgver.tar.gz::$url/archive/$pkgver.tar.gz")
sha256sums=('febbbfb1de7720641e7e36cef6ae0ce8ed18684e3faf539f703a5497f830267f')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  arch-meson build/
  ninja -C build/
}

check() {
  cd "$srcdir/$pkgname-$pkgver/build"
  meson test
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  DESTDIR="$pkgdir/" ninja -C build/ install
}
