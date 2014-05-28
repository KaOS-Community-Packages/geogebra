pkgname=geogebra
pkgver=4.4.35.0
pkgrel=1
pkgdesc='Dynamic mathematics software with interactive graphics, algebra and spreadsheet'
arch=('x86_64')
url='http://www.geogebra.org/'
license=('GPL3' 'CCPL:by-sa' 'CCPL:by-nc')
depends=('java-runtime' 'shared-mime-info' 'hicolor-icon-theme' 'xdg-utils'
         'desktop-file-utils' 'gsl')
install=geogebra.install
source=(http://download.geogebra.org/installers/4.4/GeoGebra-Linux-Installer-$pkgver.tar.gz)
md5sums=('0f3890b29ea6d7cbed0dab95805054e4')

package() {
  install -dm755 "$pkgdir"/usr/bin \
    "$pkgdir"/usr/share/applications \
    "$pkgdir"/usr/share/geogebra

  cd $pkgname-$pkgver
  sed -i 's/\/usr/\$\{pkgdir\}\/usr/g' install.sh
  source install.sh
  install -Dm644 _license.txt "$pkgdir"/usr/share/licenses/$pkgname/LICENSE

  rm -rf "$pkgdir"/usr/share/mime/
} 
