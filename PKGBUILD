# Maintainer: Toncho Zhelev <toncho.zhelev@gmail.com>
pkgname='zterm'
pkgver=r3.525f786
pkgrel=1
# epoch=
pkgdesc="My personal termial emulator, based on st"
arch=('i686' 'x86_64' 'armv7h' 'aarch64')
url="https://github.com/PifeVoxd/zterm"
license=('MIT')
groups=()
depends=('libxft' 'tmux')
makedepends=('make' 'git')
source=('zterm::git+ssh://git@my.github.com/PifeVoxd/zterm.git')
md5sums=('SKIP')

pkgver() {
  cd "$pkgname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short=7 HEAD)"
}

build() {
	cd "$pkgname"
	make
}

package() {
	cd "$pkgname"
	make PREFIX=/usr DESTDIR="$pkgdir/" install
}
