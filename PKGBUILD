# Maintainer: artoo <flower_of_life@gmx.net>

pkgname=manjaro-tools-git
pkgver=r19.ee2ca5c
pkgrel=1
pkgdesc='Tools for Manjaro Linux'
arch=('any')
license=('GPL')
url='https://github.com/udeved/manjaro-tools'
depends=('namcap' 'openssh' 'subversion' 'rsync')
provides=('devtools')
conflicts=('devtools' 'arch-install-scripts' 'manjaro-tools')
replaces=('devtools' 'manjaro-tools')
backup=('etc/manjaro-tools/manjaro-tools.conf')
source=("git+https://github.com/udeved/manjaro-tools.git")
sha256sums=('SKIP')

pkgver() {
	cd ${srcdir}/manjaro-tools
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd ${srcdir}/manjaro-tools
	make PREFIX=/usr SYSCONFDIR=/etc
}

package() {
	cd ${srcdir}/manjaro-tools
	make SYSCONFDIR=/etc PREFIX=/usr DESTDIR=${pkgdir} install
}