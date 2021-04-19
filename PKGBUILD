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
            '3f608a8203970706020bc58e71d89a0dd78d3d482ba0615ad4530ea17e01a4174c24e6f607b1e9c814799dbf7c96fcc4eea371228ab2517deb1f50151a6a30f0')

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
