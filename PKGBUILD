# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-screensaver-stars
epoch=1
pkgver=2.1.0
_codename=Leia
pkgrel=4
pkgdesc="Starfield screensaver for Kodi"
arch=('x86_64')
url='https://github.com/xbmc/screensaver.stars'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-screensaver')
depends=('kodi')
makedepends=('git' 'cmake' 'kodi-dev')
source=("$pkgname-$pkgver.tar.gz::https://github.com/xbmc/screensaver.stars/archive/$pkgver-$_codename.tar.gz")
sha512sums=('7bc9ffb8b186c07fa7c4166fc7876a5733e6a0d5feb7942794d3db78a98c6e8a03283b086c02bc6ec27ce8a246e39b36fb188815b219a8a016f80d3f2543548a')

build() {
    cd "screensaver.stars-$pkgver-$_codename"
	cmake \
		-DCMAKE_INSTALL_PREFIX=/usr \
		-DCMAKE_BUILD_TYPE=Release \
		-DBUILD_SHARED_LIBS=1 \
		-DUSE_LTO=1
	make
}

package() {
    cd "screensaver.stars-$pkgver-$_codename"
	make DESTDIR="$pkgdir/" install
}

