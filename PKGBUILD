# Contributor: Bhushan Shah < bshah at kde dot org >

pkgname=lxc-android
provides=('lxc-android')
pkgver=0.1
pkgrel=1
pkgdesc="LXC container configuration for Android"
arch=('any')
url="https://github.com/gemian/lxc-android"
license=('Apache')
depends=('lxc' 'cpio')
makedepends=('git')
source=('lxc-android::git+https://github.com/hybris-mobian/lxc-android.git#branch=bullseye')
md5sums=('SKIP')

package() {
    cd lxc-android
    cp -r usr/ etc/ var/ $pkgdir
    cp -r lib/ $pkgdir/usr/
}
