# Maintainer: Antonio Rojas <arojas@archlinux.org>

pkgname=libbluedevil-frameworks-git
pkgver=r213.cfea814
pkgrel=1
pkgdesc='KDE bluetooth framework libraries'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/playground/libs/libbluedevil'
license=('GPL2')
depends=('qt5-base')
makedepends=('extra-cmake-modules' 'git')
provides=('libbluedevil-frameworks')
conflicts=('libbluedevil-frameworks' 'libbluedevil')
source=("git://anongit.kde.org/libbluedevil.git#branch=frameworks")
sha256sums=('SKIP')

pkgver() {
  cd libbluedevil
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../libbluedevil \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_LIBDIR=lib
  make
}

package() {
  cd build
  make DESTDIR="$pkgdir" install
}
