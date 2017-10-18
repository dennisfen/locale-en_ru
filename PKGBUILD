# Maintainer: Denis Borisevich <denis@borisevich.me>
pkgname=locale-en_ru
pkgver=0.5.2
pkgrel=1
pkgdesc="An English locale for Russia."
arch=(any)
url="http://en-ru.sourceforge.net/"
license=('GPL')
provides=(locale-en_RU)
conflicts=(locale-en_RU)
replaces=(locale-en_RU)
install="$pkgname.install"
source=(
    "https://sourceforge.net/projects/en-ru/files/$pkgver/locale-en_RU-$pkgver.tar.gz/download"
)
md5sums=(
    "37f20c816b58815ddcbf780cef06069e"
)
sha512sums=(
    "71e77f389aca60d5e41eccb797cf6d7da9425348355c573650efc5aa0b8ee208740666f3142623b8ccd64424a99011aa57963335d82a9d7872ffab025faaf6f0"
)
validpgpkeys=()

build() {
	cd "locale-en_RU-$pkgver"
    mkdir build
    cd build
	../configure --prefix=/usr \
        --disable-rpm \
        --disable-html \
        --enable-ruble-sign=auto
	make
}

check() {
	cd "locale-en_RU-$pkgver/build"
	make -k check
}

package() {
	cd "locale-en_RU-$pkgver/build"
	make DESTDIR="$pkgdir/" install
}
