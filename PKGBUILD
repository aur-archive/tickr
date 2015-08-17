# Maintainer: archtux <antonio dot arias99999 at gmail dot com>

pkgname=tickr
pkgver=0.6.4
pkgrel=1
pkgdesc="GTK-based RSS Reader that displays feeds as a smooth scrolling line on your Desktop, as known from TV stations."
arch=('i686' 'x86_64')
url="http://www.newsrssticker.com/"
license=('GPL3')
depends=('gtk2' 'libxml2')
source=(http://www.newsrssticker.com/src/$pkgname-$pkgver.tar.gz)
md5sums=('57ed386f50829e3aa5f5a575640a5d5b')

prepare() {
   cd $srcdir/$pkgname-$pkgver

   ./configure --prefix=/usr
}

build() {
   cd $srcdir/$pkgname-$pkgver

   make
}

package() {
   cd $srcdir/$pkgname-$pkgver

   make DESTDIR=$pkgdir install

   # Desktop icon
   install -Dm644 tickr.desktop $pkgdir/usr/share/applications/tickr.desktop

   # Sample URL-list
   install tickr-url-list $pkgdir/usr/share/tickr/tickr-url-list   

   # Man page
   install -Dm644 tickr.1 $pkgdir/usr/share/man/man1/tickr.1 
}