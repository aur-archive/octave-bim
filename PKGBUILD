#
# Maintainer: Clemens Buchacher <drizzd@aon.at>
#
# You can use the newpkg script from
# https://github.com/drizzd/octave-forge-archlinux to automatically generate
# new octave-forge PKGBUILDs or update existing ones. Patches welcome.
#

_pack=bim
pkgname=octave-$_pack
pkgver=1.1.5
pkgrel=1
pkgdesc="Package for solving Diffusion Advection Reaction (DAR) Partial Differential Equations "
arch=(any)
url="http://octave.sourceforge.net/$_pack/"
license=('GPL')
groups=('octave-forge')
depends=('octave>=3.8.0' 'octave-fpl' 'octave-msh')
makedepends=()
optdepends=()
backup=()
options=()
install=$pkgname.install
_archive=$_pack-$pkgver.tar.gz
source=("http://downloads.sourceforge.net/octave/$_archive")
noextract=("$_archive")
md5sums=('b25450de30820c2662d5134470d9ee0f')

build() {
  cd "$srcdir"
  mkdir -p builddir
  octave -q -f --eval "pkg build -verbose -nodeps builddir $_archive"
}

package() {
  mkdir -p "$pkgdir/usr/share/octave/packages"
  mkdir -p "$pkgdir/usr/lib/octave/packages"
  cp "$srcdir/builddir/$_archive" "$pkgdir/usr/share/octave/$_pack.tar.gz"
}
