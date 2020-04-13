# Maintainer: Yongtai Li (SiHuan) <sihuan@sakuya.love>

pkgname=qq-linux
pkgver=2.0.0_b2_1082
pkgrel=1
arch=('x86_64')
pkgdesc="Tencent QQ for Linux"
url="https://im.qq.com/linuxqq"
depends=('gtk2' 'glibc' 'gcc-libs' 'nss')
license=('custom')
source=(
    "http://down.qq.com/qqweb/LinuxQQ_1/linuxqq_2.0.0-b2-1082_arm64.deb"
    "qq.desktop"
)
sha512sums=('db498acefae7fb0b77133a883c8decda83d65d0021fb4f1d7f4ce23f6be6b22719664bae642c9aa7ee26e1ebd5649ee7837f31aa8378b6716051fa049e6b9267'
            'de2db57a38e9a0951ab5bae5629a6ebc8ef0b6f944c15ffbdf6914113af1bbc0228bd56e8d054b31196cc18ad88591b4f6bd65f867d20b6f17c6cfd41c37a5aa')
provides=('linuxqq')
conflicts=('linuxqq')

prepare() {
    tar -xvJf "$srcdir/data.tar.xz"
}

package() {
    mkdir -p "$pkgdir/opt/tencent-qq"
    cp -pr "$srcdir/usr/local/bin/"* "$pkgdir/opt/tencent-qq/"
    cp -pr "$srcdir/usr/local/share/tencent-qq/"* "$pkgdir/opt/tencent-qq/"

    mkdir -p "$pkgdir/usr/bin"
    ln -s ../../opt/tencent-qq/qq "$pkgdir/usr/bin/qq"
    
    install -Dm644 "$pkgdir/opt/tencent-qq/qq.png" "$pkgdir/usr/share/icons/hicolor/48x48/apps/qq.png"
    install -Dm644 "$srcdir/qq.desktop" "$pkgdir/usr/share/applications/qq.desktop"
}