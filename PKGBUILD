# Merged with official ABS kjsembed PKGBUILD by dr460nf1r3, 2021/12/05 (all respective contributors apply herein)
# Contributor: Antonio Rojas <arojas@archlinux,org>
# Contributor: Felix Yan <felixonmars@archlinux.org>
# Contributor: Andrea Scarpino <andrea@archlinux.org>
# Contributor: Pierre Schmitz <pierre@archlinux.de>

pkgname=dolphin-git
pkgver=21.11.90.r26.g6cd5e10f2
pkgrel=1
pkgdesc='KDE File Manager'
arch=(x86_64)
url='https://apps.kde.org/dolphin/'
license=(LGPL)
depends=(baloo-widgets knewstuff-git kio-extras-git kcmutils-git kparts-git kactivities-git kuserfeedback-git)
makedepends=(extra-cmake-modules-git kdoctools-git)
optdepends=('kde-cli-tools: for editing file type options' 'ffmpegthumbs: video thumbnails' 'kdegraphics-thumbnailers: PDF and PS thumbnails'
            'konsole: terminal panel' 'purpose: share context menu')
conflicts=(${pkgname%-git})
provides=(${pkgname%-git})
groups=(kde-applications-git kde-system-git)
source=("git+https://invent.kde.org/system/${pkgname%-git}.git")
sha256sums=('SKIP')

pkgver() {
    git -C ${pkgname%-git} describe --long | sed 's/^v//;s/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
  cmake -B build -S ${pkgname%-git} \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
