# Maintainer: Lutfa Ibtihaji Ilham <sysadmin@cepucyber.com>
# Maintainer: Sander Boom <sanderboom@gmail.com>
# Contributor: realitygaps <realitygaps at yahoo dot com>

pkgname=sublime-text-dev
pkgver=3.3143
pkgrel=1
pkgdesc="Sophisticated text editor for code, html and prose - dev build"
arch=('i686' 'x86_64')
url="http://www.sublimetext.com/3"
license=('custom')
depends=('libpng' 'gtk2')
optdepends=('gksu: sudo-save support')
conflicts=('sublime-text-nightly')
provides=('sublime-text-nightly')
install=${pkgname}.install

source=('sublime_text_3.desktop')
source_i686=("https://download.sublimetext.com/sublime_text_3_build_${pkgver:2}_x32.tar.bz2")
source_x86_64=("https://download.sublimetext.com/sublime_text_3_build_${pkgver:2}_x64.tar.bz2")

sha256sums=('f355c6bec64e962a5735d0a7d1e11ac39b5b82aacaaf23b222c0bc202e15d866')
sha256sums_i686=('92ffefa470f0777897ed0dfb7c1635426105271da9b5affbe8c1e82039718e29')
sha256sums_x86_64=('9ce120c4f28b239d3b3860ee672d9d87e1397a4c08ee6c4e62fd6e261a296519')

package() {
  cd "${srcdir}"

  install -dm755 "${pkgdir}/opt"
  cp --preserve=mode -r "sublime_text_3" "${pkgdir}/opt/sublime_text_3"

  for res in 128x128 16x16 256x256 32x32 48x48; do
    install -dm755 "${pkgdir}/usr/share/icons/hicolor/${res}/apps"
    ln -s "/opt/sublime_text_3/Icon/${res}/sublime-text.png" "${pkgdir}/usr/share/icons/hicolor/${res}/apps/sublime-text.png"
  done

  install -dm755 "${pkgdir}/usr/share/applications"
  install -Dm644 "sublime_text_3.desktop" "${pkgdir}/usr/share/applications/sublime_text_3.desktop"

  install -dm755 "${pkgdir}/usr/bin"
  ln -s "/opt/sublime_text_3/sublime_text" "${pkgdir}/usr/bin/subl3"
}
