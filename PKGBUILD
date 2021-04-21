# Contributor: Bhushan Shah < bshah at kde dot org >

pkgname=lxc-android
provides=('lxc-android')
pkgver=0.1
pkgrel=2
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
    install -Dm644 etc/udev/rules.d/* -t "$pkgdir/etc/udev/rules.d/"
    install -Dm644 etc/NetworkManager/conf.d/* -t  $pkgdir/etc/NetworkManager/conf.d/
    install -Dm644 lib/systemd/system/* -t $pkgdir/usr/lib/systemd/system/
    install -Dm644 lib/udev/rules.d/* -t $pkgdir/usr/lib/udev/rules.d/
    install -Dm644 usr/lib/android-tools-adbd/* -t $pkgdir/usr/lib/android-tools-adbd/
    install -Dm644 usr/lib/lxc-android/* -t $pkgdir/usr/lib/lxc-android/
    install -Dm644 usr/sbin/* -t $pkgdir/usr/bin/
    install -Dm644 var/lib/lxc/android/* -t $pkgdir/var/lib/lxc/    
}
