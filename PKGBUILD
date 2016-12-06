pkgname=xerox5020dn
pkgver=1.0.0.3
pkgrel=1
pkgdesc='CUPS Printer Driver for Xerox Workcentre 5020dn'
url='http://www.support.xerox.com/support/workcentre-5020/downloads/ruru.html?operatingSystem=linux'
arch=('i686' 'x86_64')
license=('custom')
depends_i686=('glibc' 'libcups')
depends_x86_64=('lib32-glibc' 'lib32-libcups')
source=('http://download.support.xerox.com/pub/drivers/WC5020/drivers/linux/en/xrworkcentre5020dn-1.0.0-3.i386.rpm'
        'xerox.license')
sha256sums=('2756845dd66403fad086bcdbae1fde61a4ee794bbdcdd6346d9ebdb7e7a6a628'
            '21a15bb26dda16a007aafa25dec23a7126997c097d5db2b6097305b61394c925')

package() {
	install -Dm644 ${srcdir}/etc/cups/mimexrrb2.convs ${pkgdir}/usr/share/cups/mime/xrrb2.convs
	install -Dm644 ${srcdir}/etc/cups/mimexrrb2.types ${pkgdir}/usr/share/cups/mime/xrrb2.types

	install -Dm644 ${srcdir}/usr/share/cups/model/Xerox/en/wc5020dn.ppd ${pkgdir}/usr/share/cups/model/Xerox/wc5020dn.ppd

	install -dm755 ${pkgdir}/usr/lib/cups/filter
	cp -dp ${srcdir}/usr/lib/cups/filter/* ${pkgdir}/usr/lib/cups/filter

	install -Dm644 xerox.license ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
}
