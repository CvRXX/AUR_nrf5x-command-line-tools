# Maintainer: Alexis Polti <alexis@free.fr>
# Corrected by Nim65s <guilhem@saurel.me>
!
pkgname=nrf5x-command-line-tools
pkgver=10.6.0
pkgrel=0
pkgdesc="Tools for programming Nordic nRF51, nRF52 and nRF91 MCU using J-Link"
arch=('i686' 'x86_64')
url="https://www.nordicsemi.com/Software-and-Tools/Development-Tools/nRF-Command-Line-Tools"
license=('custom')
depends=('jlink-software-and-documentation')
provides=('nrfjprog')
conflicts=('nrfjprog')
options=()
_source="https://www.nordicsemi.com/-/media/Software-and-other-downloads/Desktop-software/nRF-command-line-tools/sw/Versions-10-x-x/nRFCommandLineTools${pkgver//./}Linux"
source_i686=("${_source}i386tar.gz")
source_x86_64=("${_source}amd64tar.gz")

md5sums_i686=('d2b1f0ad3c63b5c6f48f4732e61c7929')
md5sums_x86_64=('cb3367525aa4a3352a5551a23882bb92')

package() {
    cd ${srcdir}
    echo "nRF-Command-Line-Tools_${pkgver//./_}_Linux-amd64.tar.gz"
    tar xf "nRF-Command-Line-Tools_${pkgver//./_}_Linux-amd64.tar.gz"

    # Install nrfjprog and mergehex
    install -dm755 "${pkgdir}/opt/nrfjprog" "${pkgdir}/opt/mergehex"
    install -dm755 "${pkgdir}/usr/bin" "${pkgdir}/usr/share/licenses/${pkgname}"

    cp -r --preserve=mode nrfjprog/* "${pkgdir}/opt/nrfjprog"
    cp --preserve=mode mergehex/* "${pkgdir}/opt/mergehex"
    cp --preserve=mode nrfjprog/LICENSE.txt "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"

    ln -s "/opt/nrfjprog/nrfjprog" "${pkgdir}/usr/bin"
    ln -s "/opt/mergehex/mergehex" "${pkgdir}/usr/bin"
}
