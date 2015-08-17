## Contributor: quantax -- contact via Arch Linux forum or AUR
## Contributor: Dylan D'Arcy <dylan.somebody at gmail dot com>

pkgname=ut1999-chaosut
pkgver=1.1
pkgrel=3
pkgdesc="The chaotic Unreal Tournament mod."
arch=('i686')
url="http://chaotic.beyondunreal.com/"
license=('custom')
groups=(ut1999-goty)
depends=(ut1999)
makedepends=(umodunpack)
install=install.sh
source=($pkgname-$pkgver.zip::'http://www.ut-files.com/index.php?dir=GameTypes/ChaosUT/&file=chaosut_v1-1_full.zip'
        install.sh)
md5sums=('d94a31c812cbff5be586e9d11a150a84'
         'e850b42c2f28649e4fe37a8b25ab78d3')

build() {
    install --directory -- "$pkgdir/opt/ut"
    cd "$pkgdir/opt/ut"
    install --directory ChaosUTaddons System
    touch System/UnrealTournament.ini

    umodunpack --base . "$srcdir/CUTDesktop.umod" || return 1
    umodunpack --base . "$srcdir/CUTServerSetup.umod" || return 1
    umodunpack --base . "$srcdir/Chrekinstall.umod" || return 1
    umodunpack --base . "$srcdir/chaosut_v1-1_full.umod" || return 1

    mv ChaosUTaddons/Chreks Help/chaosut
    mv Help/*.* Help/chaosut
    mv chrekbanner.bmp Help/chaosut/Chreks
    rm -fr -- ChaosUTaddons System/UnrealTournament.ini
}

