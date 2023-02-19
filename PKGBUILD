# Maintainer: Bardia Moshiri <fakeshell@bardia.tech>

pkgname=plymouth-hybris
provides=(plymouth)
conflicts=(plymouth)
pkgver=0.9.5
pkgrel=3
pkgdesc="Plymouth is a free application which provide bootsplash for Linux, which handles user interaction during the boot process"
license=("GPL2")
arch=('aarch64')
depends=('systemd' 'lsb-release')
makedepends=('libgudev' 'libpng' 'pango' 'libdrm' 'libxslt' 'docbook-xsl' 'pkgconf' 'systemd' 'make' 'autoconf' 'automake')
source=("git+https://github.com/droidian/plymouth")
sha256sums=('SKIP')

prepare() {
  mv plymouth plymouth-hybris
  cd $pkgbase
  git checkout -b bookworm
  git checkout d784c2826438ddb456a6524cb4e432a3e3e9d1e3
}

build() {
  ls
  pwd
  cd $pkgbase
  ./configure
  make
}

package() {
  cd $pkgbase
  make DESTDIR="$pkgdir" install
}
