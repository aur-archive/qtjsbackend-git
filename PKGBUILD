# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=qtjsbackend-git
pkgver=v5.1.0.beta1.4.g6f2625e
pkgrel=1
pkgdesc="A cross-platform application and UI framework (QtV8)"
arch=('i686' 'x86_64')
url="http://qt-project.org/"
license=('GPL3' 'LGPL')
depends=('qtbase-git')
makedepends=('git' 'python2')
options=('!libtool' 'debug')
source=(git://gitorious.org/qt/qtjsbackend.git#branch=dev
        'use-python2.patch')
md5sums=('SKIP'
         '55a9360023dc2b9e8d90c111cd06baa6')

pkgver() {
  cd qtjsbackend
  git describe --always | sed 's|-|.|g'
}

prepare() {
  cd qtjsbackend
  patch -p2 -i "${srcdir}"/use-python2.patch
}

build() {
  cd qtjsbackend
  /opt/qt-git/bin/qmake
  make
}

package() {
  cd qtjsbackend
  make INSTALL_ROOT="${pkgdir}" install
}
