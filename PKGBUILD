# Author: Vitor Lopes <vmnlop@gmail.com>

_pkgname=jade-menu-data
pkgname="$_pkgname-git"
pkgver=r6.9215bff
pkgrel=1
pkgdesc="freedesktop.org application menu definition files for JADE"
arch=('any')
url="https://github.com/codesardine/Jade-menu-data"
license=('GPL')
makedepends=('git')
provides=("$_pkgname")
replaces=('$_pkgname')
source=("$_pkgname"::"git+$url.git")
md5sums=('SKIP')

pkgver() {
    cd "$_pkgname"
    (
        printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
    )
}

package() {
    cd "$_pkgname"
    mkdir -p "${pkgdir}/etc/xdg/menus" "${pkgdir}/usr/share/desktop-directories"
    cp $srcdir/$_pkgname/jade-xdg-menu/jade-applications.menu $pkgdir/etc/xdg/menus
    cp -r $srcdir/$_pkgname/jade-desktop-directories/* $pkgdir/usr/share/desktop-directories
    
}

