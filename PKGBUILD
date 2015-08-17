# Maintainer: Felix Yan <felixonmars@gmail.com>

_pkgbase=gevent
pkgname=python2-${_pkgbase}-beta
pkgver=1.0rc2
pkgrel=2
pkgdesc="Python networking library based on greenlet and libev - Beta version"
arch=('i686' 'x86_64')
url="http://www.gevent.org/"
license=('MIT')
depends=('python2-greenlet')
makedepends=('cython2')
conflicts=('python2-gevent')
provides=("python2-gevent=$pkgver")
source=("https://github.com/SiteSupport/gevent/archive/$pkgver.tar.gz")

package() {
  cd "$srcdir/${_pkgbase}-${pkgver}"
  msg "Starting make..."

  unset MAKEFLAGS

  LIBEV_EMBED=1 \
  CARES_EMBED=1 \
  CYTHON=cython2 \
  PYTHON=python2 \
  python2 setup.py install \
    --prefix=/usr \
    --root="$pkgdir"
}

md5sums=('e1bce8e15c7ebb08788978c0f4860f9d')
