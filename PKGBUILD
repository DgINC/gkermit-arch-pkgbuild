pkgname=gkermit
pkgver=1.0
pkgrel=2
pkgdesc="A utility for transferring files using the Kermit protocol"
arch=('x86_64')
license=('GPLv2+')
url="http://www.kermitproject.org/gkermit.html"
source=('ftp://ftp.kermitproject.org/kermit/archives/gku100.tar.gz'
	'gkermit-1.00-2-build.patch')
sha512sums=('7dd8476b9f92b3a5453493486313cf6f2018b698f0c2d7076a7bfaf4be3ff94024602a41495449591bd0c5ca699b324205847ce1b3498e27c418c0a0175cf64f'
            '0eed012e0b4bef896ff736821269f52334b72350e089c85036cb4e3db6e3b69f62ed766dd70b7254d13dfbc16123e71d38eab8c5fa27c03ebf9d077eaaafb071')

prepare() {
  cd "$srcdir"
  patch -p1 < gkermit-1.00-2-build.patch
}

build() {
  cd "$srcdir"
  make posix
}

package() {
  cd "$srcdir"
  install -Dm0755 gkermit "$pkgdir"/usr/bin/gkermit
  install -Dm0644 gkermit.nr "$pkgdir"/usr/share/man/man1/gkermit.1
}
