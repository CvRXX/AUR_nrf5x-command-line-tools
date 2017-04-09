# Maintainer: Jakub Luzny (jakub@luzny.cz)
pkgname=nrf5x-command-line-tools
pkgver=9.4.0
pkgrel=2
pkgdesc="Tools for programming Nordic nRF51 MCU using J-Link"
arch=('i686' 'x86_64')
url="https://www.nordicsemi.com/eng/Products/Bluetooth-low-energy/nRF51822"
license=('unknown')
depends=('jlink-software-and-documentation')
provides=('nrfjprog')
conflicts=('nrfjprog')
options=()
source_i686=("nRF5x-Command-Line-Tools_${pkgver//./_}_Linux-i386.tar::https://www.nordicsemi.com/eng/nordic/download_resource/52615/16/91173052/97746")
source_x86_64=("nRF5x-Command-Line-Tools_${pkgver//./_}_Linux-x86-64.tar::https://www.nordicsemi.com/eng/nordic/download_resource/51386/21/10116804/94917")

md5sums_i686=('da219aea4379847d8d8e5a243494ed09')
md5sums_x86_64=('b47a9353daa50c7c4119ab9b8cb44b8a')

package() {
    # Install nrfjprog and mergehex
    install -dm755 "${pkgdir}/opt/nrfjprog" "${pkgdir}/opt/mergehex" "$pkgdir/usr/bin"

    cd ${srcdir}/nrfjprog
    cp --preserve=mode * "${pkgdir}/opt/nrfjprog"

    cd ${srcdir}/mergehex
    cp --preserve=mode * "${pkgdir}/opt/mergehex"

	ln -s "/opt/nrfjprog/nrfjprog" "${pkgdir}/usr/bin"
	ln -s "/opt/mergehex/mergehex" "${pkgdir}/usr/bin"
}
