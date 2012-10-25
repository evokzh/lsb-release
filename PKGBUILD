# Maintainer: Sven-Hendrik Haase <sh@lutzhaase.com>
# Contributor: Malte Rabenseifner <malte@zearan.de>
# Contributor: John Gerritse <reaphsharc@gmail.com>

pkgname=lsb-release
pkgver=1.4
pkgrel=12
pkgdesc="LSB version query program"
arch=('any')
url="http://www.linuxbase.org/"
license=('GPL2')
install=lsb-release.install
source=(http://downloads.sourceforge.net/lsb/$pkgname-$pkgver.tar.gz)
md5sums=('30537ef5a01e0ca94b7b8eb6a36bb1e4')

build() {
  cd "$srcdir/$pkgname-$pkgver"

  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"

  install -dm755 "$pkgdir/etc"
  echo "DISTRIB_ID=archlinux" > "$pkgdir/etc/lsb-release"
  echo "DISTRIB_RELEASE=rolling" >> "$pkgdir/etc/lsb-release"
  echo "DISTRIB_DESCRIPTION=\"Arch Linux\"" >> "$pkgdir/etc/lsb-release"

  install -Dm 644 lsb_release.1.gz "$pkgdir/usr/share/man/man1/lsb_release.1.gz"
  install -Dm 755 lsb_release "$pkgdir/usr/bin/lsb_release"
}
