pkgname=geogebra
pkgver=5.0.279.0
_pkgver=5-0-279-0
pkgrel=1
pkgdesc='Dynamic mathematics software with interactive graphics, algebra and spreadsheet'
arch=('x86_64')
url='http://www.geogebra.org/'
license=('GPL3' 'CCPL:by-sa' 'CCPL:by-nc')
depends=('java-runtime' 'shared-mime-info' 'hicolor-icon-theme' 'xdg-utils'
         'desktop-file-utils' 'gsl')
source=("http://download.geogebra.org/installers/5.0/GeoGebra-Linux-Portable-${_pkgver}.tar.bz2"  "$pkgname.desktop" "$pkgname.svg")  
md5sums=('4ac733795527801184f0e456960775c1'
         'df1ea016e2c0372f93f965514926762a'
         '863782da033f1a337e688b544afb7d07')


prepare() {
    echo -en '#!/bin/sh\nexport GG_CONFIG_PATH="$HOME"\nexport JAVACMD="/usr/bin/java"\nexec "/usr/share/geogebra/geogebra" "$@"' > $srcdir/$pkgname
}

package() {
    install -dm755 "$pkgdir"/usr/bin \
    "$pkgdir"/usr/share/applications \
    "$pkgdir"/usr/share/geogebra \
    "$pkgdir"/usr/share/icons/hicolor/scalable/apps

    install "GeoGebra-Linux-Portable-${_pkgver}/geogebra/"* -t "${pkgdir}/usr/share/geogebra/"
    install -Dm644 $srcdir/$pkgname "${pkgdir}/usr/bin/"
    chmod   +x $pkgdir/usr/bin/$pkgname
    install -Dm644 $srcdir/$pkgname.svg "${pkgdir}/usr/share/icons/hicolor/scalable/apps/${pkgname}.svg"
    install -Dm644 $srcdir/$pkgname.desktop "${pkgdir}/usr/share/applications/${pkgname}.desktop"
}
