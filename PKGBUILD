# Maintainer: Travis Vallon <vallontravisnorman@gmail.com>
pkgname='travisconfig'
pkgver=2023.05
pkgrel=1
epoch=1
pkgdesc="A package that setup my Arch Linux configuration files automatically"
arch=('x86_64')
url="https://github.com/travisnormanv/travisconfig.git"
license=('unknown')
groups=('travisconfig')
depends=(
 	'xorg-server'
 	'xorg-xinit'
 	'xorg-xrdb' 
 	'xdm-archlinux' 
 	'rxvt-unicode'
 	'gvim'
 	'i3-wm'
 	'polybar'
 	'dmenu'
 	'firefox'
 	'ranger'
 	'ttf-liberation'
)
makedepends=('git')
install=$pkgname.install
source=("git+$url#branch=develop")
md5sums=('SKIP')

package() {
	cd "$pkgname"

	printf "creating configuration files...\n"
	install -Dm664 ./.Xresources		"$pkgdir/usr/local/share/travisconfig/.Xresources"
	install -Dm664 ./.vimrc			"$pkgdir/usr/local/share/travisconfig/.vimrc"
	install -Dm664 ./i3/config		"$pkgdir/usr/local/share/travisconfig/i3/config"
	install -Dm664 ./polybar/config.ini	"$pkgdir/usr/local/share/travisconfig/polybar/config.ini"
	install -Dm755 ./polybar/launch.sh	"$pkgdir/usr/local/share/travisconfig/polybar/launch.sh"
	install -Dm664 ./.xinitrc		"$pkgdir/usr/local/share/travisconfig/.xinitrc"
	install -Dm755 ./.xsession		"$pkgdir/usr/local/share/travisconfig/.xsession"
	install -Dm755 ./script/travisconfig.sh	"$pkgdir/usr/local/share/travisconfig/script/travisconfig.sh"

	install -Dm644 ./README.md		"$pkgdir/usr/local/share/doc/travisconfig/README.md"

	mkdir -p "$pkgdir/usr/local/share/doc/travisconfig/backups"
}
