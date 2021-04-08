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
    cp -r etc/udev/rules.d/* $pkgdir/etc/udev/rules.d/
    cp -r etc/NetworkManager/conf.d/* $pkgdir/etc/NetworkManager/conf.d/
    cp -r lib/systemd/system/* $pkgdir/lib/systemd/system/
    cp -r lib/udev/rules.d/* $pkgdir/lib/udev/rules.d/
    cp -r usr/lib/* $pkgdir/usr/lib/
    cp -r usr/sbin/* $pkgdir/usr/sbin/
    cp -r var/lib/lxc/android/ $pkgdir/var/lib/lxc/    
}
