# Maintainer: Marc Etzhold <majorx234 at googlemail dot com>
pkgname=wampcpp
pkgver=0.8.1
pkgrel=0
pkgdesc="A Websocket Server with RPC and Publisher/Subscriber-Concept"
arch=('any')
url=""
license=('BSD')
depends=('boost' 'websocketpp' 'jsoncpp')
makedepends=('cmake')

_tag=master
_dir=${pkgname}
source=("${_dir}"::"git+https://github.com/majorx234/wamp_cpp.git"#tag=${_tag})
sha256sums=('SKIP')

build() {
  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Build project
  cmake "${srcdir}/wampcpp" \
        -DCMAKE_INSTALL_PREFIX="/usr" 
  make
}

package() {
  cd ${srcdir}/build
  make DESTDIR="$pkgdir/" install
}
