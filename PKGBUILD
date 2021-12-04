# Contributor: Bhushan Shah < bshah at kde dot org >

pkgname=lxc-android
provides=('lxc-android')
pkgver=0.1
pkgrel=6
pkgdesc="LXC container configuration for Android"
arch=('any')
url="https://github.com/gemian/lxc-android"
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
  	
  	install -d ${pkgdir}/usr/lib/systemd/system/
  	install -m 644 lib/systemd/system/android-mount.service ${pkgdir}/usr/lib/systemd/system/
  
  	install -d ${pkgdir}/usr/lib/udev/rules.d/
  	install -m 644 lib/udev/rules.d/65-android.rules ${pkgdir}/usr/lib/udev/rules.d/
  	install -m 644 lib/udev/rules.d/99-android.rules ${pkgdir}/usr/lib/udev/rules.d/
  
  	install -d ${pkgdir}/usr/lib/android-tools-adbd/
  	install -m 755 usr/lib/android-tools-adbd/pre-start ${pkgdir}/usr/lib/android-tools-adbd/
  	
  	install -d ${pkgdir}/usr/bin
  	install -m 755 usr/sbin/mount-android.sh ${pkgdir}/usr/bin/mount-android.sh
  
  	install -d ${pkgdir}/usr/lib/lxc-android/
  	install -m 644 usr/lib/lxc-android/70-*.rules ${pkgdir}/usr/lib/lxc-android/
  	install -m 755 usr/lib/lxc-android/copy-udev-rules ${pkgdir}/usr/lib/lxc-android/
  	install -m 755 usr/lib/lxc-android/mount-android ${pkgdir}/usr/lib/lxc-android/
  
  	install -d ${pkgdir}/var/lib/lxc/android/rootfs
  	install -m 644 var/lib/lxc/android/config ${pkgdir}/var/lib/lxc/android/
  	install -m 755 var/lib/lxc/android/pre-start.sh ${pkgdir}/var/lib/lxc/android/
    
  	install -d ${pkgdir}/vendor
}
