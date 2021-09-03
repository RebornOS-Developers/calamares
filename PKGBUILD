# Maintainer: Rafael <rafael@rebornos.org>

pkgname=calamares
pkgver=3.2.41.1
pkgrel=1
pkgdesc="Distribution-Independent Installer Framework"
arch=('x86_64')
url="https://github.com/calamares/calamares"
license=('GPL')
makedepends=('cmake' 'extra-cmake-modules' 'kpmcore' 'boost-libs' 'yaml-cpp')
depends=('qt5-svg' 'qt5-webengine' 'yaml-cpp' 'networkmanager' 'boost' 'upower' 
         'kcoreaddons' 'kconfig' 'ki18n' 'kservice' 'kwidgetsaddons' 'kpmcore' 
         'squashfs-tools' 'rsync' 'cryptsetup' 'qt5-xmlpatterns' 'doxygen' 
         'dmidecode' 'gptfdisk' 'hwinfo' 'kparts' 'polkit-qt5' 'python' 'qt5ct' 
         'solid' 'qt5-tools')
provides=("${pkgname}-${pkgver}")
source=("${url}/releases/download/v${pkgver}/${pkgname}-${pkgver}.tar.gz")
sha512sums=('65f108405e5fd36f88bee3f66f2ea6bc1c45581d033a9565c813648dcb4b3c38ece40203d9f3d728a53504d06d9e215d0f7960a21834d7781fa288b78d046be8')

build() {
           mkdir -p ${srcdir}/${pkgname}-${pkgver}/build
           cd ${srcdir}/${pkgname}-${pkgver}/build
           cmake -DCMAKE_BUILD_TYPE=Debug ..
           make
}

package() {
           cd ${srcdir}/${pkgname}-${pkgver}/build
           make DESTDIR=${pkgdir} install
}

