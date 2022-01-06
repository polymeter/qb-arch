# Maintainer: Manuel Webersen <polymeter-aur@bitjam.de>
pkgname=qb-git
pkgver=r4.9decede
pkgrel=1
pkgdesc='Simple helper for use with borgbackup'
arch=('any')
url="https://github.com/polymeter/qb"
license=('MIT')
groups=()
depends=('borg')
makedepends=('git')
provides=('qb')
conflicts=('qb')
install=
source=('git+https://github.com/polymeter/qb')
noextract=()
md5sums=('SKIP')

pkgver() {
    cd "$srcdir/${pkgname%-git}"
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
    cd "$srcdir/${pkgname%-git}"
    install -Dm 644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"

    install -Dm 755 qb "$pkgdir/usr/bin/qb"

    install -Dm 644 examples/systemd/qb@.service $pkgdir/usr/lib/systemd/system/qb@.service
}
