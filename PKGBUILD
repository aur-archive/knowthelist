# Maintainer: jfperini <@jfperini>
# Contributor: jfperini <@jfperini>

pkgname=knowthelist
pkgver=2.3.0
pkgrel=2
pkgdesc="Knowthelist the awesome party music player."
url="https://github.com/knowthelist/knowthelist"
license=('GPL v2')
arch=('any')
depends=('qt4' 'taglib' 'gstreamer0.10' 'gstreamer0.10-base-plugins' 'boost' 'alsa-lib')
makedepends=('git')
conflicts=('knowthelist-git')
source=('https://github.com/'$pkgname'/'$pkgname'/archive/v'$pkgver'.tar.gz')
md5sums=('be16a478a95af5a5f3c5d457b9ae23ac')

build()
{

      cd "$srcdir/$pkgname-$pkgver"
      
      msg2 "  -> Build program..."
      qmake-qt4 $pkgname.pro
      make
      
}

package() {

      cd "$srcdir/$pkgname-$pkgver"
      
      rm -rf {.git,.gitignore,CONTRIBUTORS,COPYING,CREDITS,LICENSE.txt,README.md}
      
      msg2 "  -> Installing program..."
      install -d $pkgdir/{usr/bin,usr/share}
      cp -u "./$pkgname" "$pkgdir/usr/bin"

      msg2 "  -> Installing icons..."
      install -Dm644 "./dist/$pkgname.png" "$pkgdir/usr/share/pixmaps/$pkgname.png"
      
      msg2 "  -> Installing .desktop file..."
      install -Dm644 "./dist/$pkgname.desktop" "$pkgdir/usr/share/applications/$pkgname.desktop"
      
} 