# Maintainer: awumii <awumii@protonmail.com>
pkgname=nautilus-blackbox-git
pkgver=1.0.0
pkgrel=1
pkgdesc="A Nautilus extension to open a Black Box terminal within Nautilus"
arch=('any')
url="https://github.com/awumii/nautilus-blackbox"
#license=('GPL3') no license yet
depends=('nautilus' 'python-nautilus')
makedepends=('meson')
source=("$pkgname::git+$url")
sha256sums=('SKIP')

pkgver() {
  cd $pkgname
  git describe --tags | sed 's/^v//;s/-/+/g'
}

build() {
  cd "$srcdir/$pkgname"
  meson setup builddir
  ninja -C builddir
}

package() {
  cd "$srcdir/$pkgname"
  DESTDIR="$pkgdir" ninja -C builddir install
}
