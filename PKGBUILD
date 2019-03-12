# Maintainer: Xaver Hellauer <xaver@hellauer.bayern>
# Contributor: Andy Kluger <AndyKluger@gmail.com>
# Contributor: Markus Weimar <mail@markusweimar.de>
pkgbase=ttf-iosevka-xha
pkgname=(${pkgbase}{,-term})
pkgver=r1187.6780d860
pkgrel=1
pkgdesc='A slender monospace sans-serif and slab-serif typeface inspired by Pragmata Pro, M+ and PF DIN Mono.'
arch=('any')
url='https://be5invis.github.io/'
license=('custom:OFL')
makedepends=('nodejs' 'npm' 'ttfautohint' 'otfcc')
depends=('fontconfig' 'xorg-font-utils')
conflicts=()
provides=()
source=(
	'LICENSE.md'
	'README.md'
	'build-plans.toml'
	'emptyfont.toml'
)

sha512sums=('30da782c1f0775cb5c68743aded9f17ff9083ea9345636ecd4c276ad787ef846be2d8f17377e851854d083b4413010bf8b7870022f0aab9f555b674adfd5a0d0'
            '99258f0a6116c20590121efc214175bacff6fd1c5b122078e9f743221090720fe05e986da34e5a16a93291e9234e67829de6d974fa7123a21125c0a797dfe7e6'
            '55e201626ead9a00965c447f3d9af4c49e25b0f9397f462e4c355313d403b5954911fdff9cecff972bc3b03d43eeb74c6ffd861257b786cab7e70e7e7fad6cf0'
            '583e7fbfefdd879af88582499aae4d296fc6afd9132acd3f62dd66ab4368be2758b0a99ebf0b72ba2a3a66d78c8651ecd2753a837c5cf02b1382fab829116fc2')


pkgver() {
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  npm install
  npm run build -- contents::iosevka-xha contents::iosevka-xha-term
}

package_ttf-iosevka-xha() {
  install -d "${pkgdir}/usr/share/fonts/TTF"
  install -m644 "$startdir"/dist/iosevka-xha/ttf/*.ttf "${pkgdir}/usr/share/fonts/TTF/"
  install -d "${pkgdir}/usr/share/licenses/${pkgname}"
  install -m644 LICENSE.md "${pkgdir}/usr/share/licenses/${pkgname}/"
}

package_ttf-iosevka-xha-term() {
  install -d "${pkgdir}/usr/share/fonts/TTF"
  install -m644 "$startdir"/dist/iosevka-xha-term/ttf/*.ttf "${pkgdir}/usr/share/fonts/TTF/"
  install -d "${pkgdir}/usr/share/licenses/${pkgname}"
  install -m644 LICENSE.md "${pkgdir}/usr/share/licenses/${pkgname}/"
}
