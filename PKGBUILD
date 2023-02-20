# Maintainer: Bardia Moshiri <fakeshell@bardia.tech>

pkgname=lxc-android
provides=('lxc-android')
pkgver=12.0
pkgrel=1
pkgdesc="LXC container configuration for Android"
arch=('any')
url="https://github.com/droidian/lxc-android"
license=('Apache')
depends=('lxc' 'cpio')
makedepends=('git')
source=('lxc-android::git+https://github.com/manjaro-libhybris/lxc-android.git')
md5sums=('SKIP')

package() {
    cd lxc-android
    install -d ${pkgdir}/etc/udev/rules.d/
    install -m 644 etc/udev/rules.d/50-firmware.rules ${pkgdir}/etc/udev/rules.d/
    install -m 644 etc/udev/rules.d/60-persistent-v4l.rules ${pkgdir}/etc/udev/rules.d/
    install -m 644 etc/udev/rules.d/90-alsa-restore.rules ${pkgdir}/etc/udev/rules.d/
    install -m 644 etc/udev/rules.d/90-alsa-ucm.rules ${pkgdir}/etc/udev/rules.d/

    install -d ${pkgdir}/etc/NetworkManager/conf.d/
    install -m 644 etc/NetworkManager/conf.d/99-wifi-disable-random-mac.conf ${pkgdir}/etc/NetworkManager/conf.d/99-wifi-disable-random-mac.conf

    install -d ${pkgdir}/etc/systemd/system/
    install -m 644 etc/systemd/system/lxc@android.service ${pkgdir}/etc/systemd/system/

    install -d ${pkgdir}/usr/lib/systemd/system/
    install -m 644 lib/systemd/system/android-mount.service ${pkgdir}/usr/lib/systemd/system/

    install -d ${pkgdir}/usr/lib/udev/rules.d/
    install -m 644 lib/udev/rules.d/65-android.rules ${pkgdir}/usr/lib/udev/rules.d/
    install -m 644 lib/udev/rules.d/99-android.rules ${pkgdir}/usr/lib/udev/rules.d/

    install -d ${pkgdir}/usr/lib/android-tools-adbd/
    install -m 755 usr/lib/android-tools-adbd/pre-start ${pkgdir}/usr/lib/android-tools-adbd/

    install -d ${pkgdir}/usr/bin
    install -m 755 usr/bin/mount-android.sh ${pkgdir}/usr/bin/mount-android.sh

    install -d ${pkgdir}/usr/lib/lxc-android/
    install -m 755 usr/lib/lxc-android/mount-android ${pkgdir}/usr/lib/lxc-android/
    install -m 755 usr/lib/lxc-android/lxc-android-stop ${pkgdir}/usr/lib/lxc-android/
    install -m 755 usr/lib/lxc-android/lxc-android-notify ${pkgdir}/usr/lib/lxc-android/

    install -d ${pkgdir}/var/lib/lxc/android/rootfs
    install -m 644 var/lib/lxc/android/config ${pkgdir}/var/lib/lxc/android/
    install -m 755 var/lib/lxc/android/pre-start.sh ${pkgdir}/var/lib/lxc/android/
    
    ln -s /android/apex ${pkgdir}/apex
    ln -s /android/vendor ${pkgdir}/vendor
}
