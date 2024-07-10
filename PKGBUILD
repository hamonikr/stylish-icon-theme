# Maintainer: Kevin Kim <chaeya@gmail.com>
pkgname=stylish-icon-theme
pkgver=1.0
pkgrel=1
pkgdesc="Stylish icon pack"
arch=('any')
url="https://github.com/hamonikr/stylish-icon-theme"
license=('GPL')
depends=('wget')
makedepends=('devtools' 'base-devel')
source=("https://github.com/hamonikr/stylish-icon-theme/releases/download/v1.0.0/stylish-icon-theme_1.0.0_all.deb")
sha256sums=('SKIP')

prepare() {
    # Extract the package name from the source URL
    debfile=$(basename "${source[0]}")
    bsdtar -xf "${srcdir}/${debfile}" -C "${srcdir}"
}

package() {
    bsdtar -xf "${srcdir}/data.tar.xz" -C "${pkgdir}/"
    bsdtar -xf "${srcdir}/control.tar.xz" -C "${srcdir}"
    install -Dm644 "${srcdir}/control" "${pkgdir}/usr/share/doc/${pkgname}/control"
}