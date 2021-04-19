pkgname=gkermit
pkgver=1.0
pkgrel=1
pkgdesc="A utility for transferring files using the Kermit protocol"
arch=('x86_64')
license=('GPLv2+')
url="http://www.kermitproject.org/gkermit.html"
source=('ftp://ftp.kermitproject.org/kermit/archives/gku100.tar.gz'
	'gkermit-1.00-build.patch')
sha512sums=('7dd8476b9f92b3a5453493486313cf6f2018b698f0c2d7076a7bfaf4be3ff94024602a41495449591bd0c5ca699b324205847ce1b3498e27c418c0a0175cf64f'
            '41ab53ac9f6ede9b92ad8832a0e2afd60310981addf3ba1b587d3f0ea117dfc5c79080d66381d2311df7e9a2db390041924bb301d0558a21d70127a7d81f8e0c')

prepare() {
  cd "$srcdir"
  patch -p1 < gkermit-1.00-build.patch
}

build() {
  cd "$srcdir"
  make posix
}

package() {
  cd "$srcdir"
  install -Dm0755 gkermit "$pkgdir"/usr/bin/gkermit
  install -Dm0644 gkermit.nr "$pkgdir"/usr//share/man/man1/gkermit.1
}
