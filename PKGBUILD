# Maintainer: Niels Martignène <niels.martignene@gmail.com>

pkgname=ruby-gli
pkgver=2.12.2
pkgrel=1
pkgdesc="Git-Like Interface Command Line Parser"
arch=(any)
url="http://davetron5000.github.io/gli/"
license=('APACHE')
depends=('ruby')
source=("http://gems.rubyforge.org/gems/gli-${pkgver}.gem")
noextract=("gli-${pkgver}.gem")
sha256sums=('829d5dc46cbc210fbd9a8b9adf0e1ee07f896f46bc462fffadd9ed0a09eb0af4')

package() {
  cd "$srcdir"
  # _gemdir is defined inside package() because if ruby[gems] is not installed on
  # the system, makepkg will exit with an error when sourcing the PKGBUILD.
  local _gemdir="$(ruby -rubygems -e'puts Gem.default_dir')"

  gem install --no-user-install --ignore-dependencies \
    -i "${pkgdir}${_gemdir}" -n "${pkgdir}/usr/bin" "gli-${pkgver}.gem"
}
