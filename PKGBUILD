# Maintainer: Xaver Hellauer <xaver@hellauer.bayern>
# Contributor: Andy Kluger <AndyKluger@gmail.com>
# Contributor: Markus Weimar <mail@markusweimar.de>
pkgbase=ttf-iosifovich
pkgname=(${pkgbase}{,-term})
pkgver=r1189.30b3ffe9
pkgrel=1
pkgdesc='A slender monospace sans-serif and slab-serif typeface inspired by Pragmata Pro, M+ and PF DIN Mono.'
arch=('any')
url='https://be5invis.github.io/'
license=('custom:OFL')
makedepends=('nodejs' 'npm' 'ttfautohint' 'otfcc')
depends=('fontconfig' 'xorg-font-utils')
conflicts=()
provides=()

source=('LICENSE.md')

sha512sums=('30da782c1f0775cb5c68743aded9f17ff9083ea9345636ecd4c276ad787ef846be2d8f17377e851854d083b4413010bf8b7870022f0aab9f555b674adfd5a0d0')

pkgver() {
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  npm install
  npm run build -- woff2::iosifovich woff2::iosifovich-term
}

package_ttf-iosifovich() {
  install -d "${pkgdir}/usr/share/fonts/TTF"
  install -m644 "$startdir"/dist/iosifovich/ttf/*.ttf "${pkgdir}/usr/share/fonts/TTF/"
  install -d "${pkgdir}/usr/share/licenses/${pkgname}"
  install -m644 LICENSE.md "${pkgdir}/usr/share/licenses/${pkgname}/"
}

package_ttf-iosifovich-term() {
  install -d "${pkgdir}/usr/share/fonts/TTF"
  install -m644 "$startdir"/dist/iosifovich-term/ttf/*.ttf "${pkgdir}/usr/share/fonts/TTF/"
  install -d "${pkgdir}/usr/share/licenses/${pkgname}"
  install -m644 LICENSE.md "${pkgdir}/usr/share/licenses/${pkgname}/"
}

