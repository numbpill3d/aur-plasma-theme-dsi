# Maintainer: numbpill3d <void@nothing>
# Contributor: numbpill3d <void@nothing>
pkgname=plasma-theme-dsi
pkgver=r7.gdbcba01
pkgrel=1
pkgdesc='Nintendo DSi-inspired KDE Plasma theme suite by deadgirl (numbpill3d)'
arch=('any')
url='https://github.com/numbpill3d/DSi-clearware-white-rice-Desktop-Theme-Plasma-KDE'
license=('GPL-2.0-or-later')
depends=('plasma-workspace' 'kwin')
optdepends=('kde-icon-theme: the Breeze icon theme the DSi icons build on')
source=('git+https://github.com/numbpill3d/DSi-clearware-white-rice-Desktop-Theme-Plasma-KDE.git')
sha256sums=('SKIP')

pkgver() {
  cd "$srcdir/DSi-clearware-white-rice-Desktop-Theme-Plasma-KDE"
  printf 'r%s.g%s\n' "$(git rev-list --count HEAD)" "$(git rev-parse --short=7 HEAD)"
}

package() {
  cd "$srcdir/DSi-clearware-white-rice-Desktop-Theme-Plasma-KDE"

  # Plasma 6 desktop theme
  install -d "$pkgdir/usr/share/plasma/desktoptheme/DSi"
  cp -r dsi-plasma-theme/. "$pkgdir/usr/share/plasma/desktoptheme/DSi/"

  # Colour scheme
  install -Dm644 dsi-color-scheme/DSi.colors "$pkgdir/usr/share/color-schemes/DSi.colors"

  # Icon theme
  install -d "$pkgdir/usr/share/icons/DSi"
  cp -r dsi-icon-theme/. "$pkgdir/usr/share/icons/DSi/"

  # Cursor theme (X cursor themes live under <theme>/cursors)
  install -d "$pkgdir/usr/share/icons/DSi/cursors"
  cp -r dsi-cursor-theme/cursors/. "$pkgdir/usr/share/icons/DSi/cursors/"

  # KWin window decoration (a KWin/Decoration service plugin)
  install -d "$pkgdir/usr/share/kwin/themes/dsi"
  cp -r dsi-window-decoration/. "$pkgdir/usr/share/kwin/themes/dsi/"

  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
