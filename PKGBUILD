# Contributor: Patrick Leslie Polzer <leslie.polzer@gmx.net>
# Contributor: cdhotfire <cdhotfire@gmail.com>
# Contributor: Shinlun Hsieh <yngwiexx@yahoo.com.tw>
# Maintainer: Elisamuel Resto <ryuji@simplysam.us>

pkgname=chrony
pkgver=1.26
pkgrel=1
pkgdesc="Dial-up friendly NTP daemon and excellent replacement for NTP on desktop systems"
arch=('i686' 'x86_64')
url="http://chrony.tuxfamily.org/"
options=('strip')
license=('GPL')
depends=('readline')
backup=('etc/chrony.conf')
source=("http://download.tuxfamily.org/chrony/${pkgname}-${pkgver}.tar.gz" \
	'chrony')
md5sums=('ad6dd619ff1986e4ff780363c64e2246'
         '43a21b6a904883ac8365f14e52475e89')

build() {
  cd $srcdir/$pkgname-$pkgver
  ./configure --prefix=/usr
  make || return 1
  make DESTDIR=$pkgdir install

  install -D -m0644 $srcdir/$pkgname-$pkgver/examples/chrony.conf.example $pkgdir/etc/chrony.conf && \
  install -D -m0755 $srcdir/chrony $pkgdir/etc/rc.d/chrony
}
