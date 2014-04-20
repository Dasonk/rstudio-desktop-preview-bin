# Maintainer: dasonk < dasonk at gmail dot com >
# Contributor: Meow < meow at linux dot cn >

pkgname=rstudio-desktop-preview-bin
pkgver=0.98.792
pkgrel=1
pkgdesc="A new integrated development environment (IDE) for R (The preview binary from the website)."
arch=('x86_64') # May work for i686 but hasn't been tested
license=('GPL')
url="http://www.rstudio.org/ide/download/preview"
depends=('r>=2.11.1' 'qtwebkit')
conflicts=('rstudio-desktop' 'rstudio-desktop-git' 'rstudio-desktop-bin')
provides=("rstudio-desktop=${pkgver}")
options=(!strip)
#_x86md5=be7da6269c6499770957f478f4eeaf2f
_x64md5=db2fc2ce37dc4d16e12bc95c85eaa731
case "$CARCH" in
#	'i686')
		#_arch=i386
		#md5sums=($_x86md5)
		#;;
	'x86_64')
		_arch=amd64
		md5sums=($_x64md5)
		;;
esac    
source=("https://s3.amazonaws.com/rstudio-dailybuilds/rstudio-${pkgver}-${_arch}.deb")

install="$pkgname".install

package() {
  msg "Converting debian package..."
  cd "$srcdir"
  tar zxpf data.tar.gz -C "$pkgdir"
  install -dm755 "$pkgdir/usr/bin"
  cd "$pkgdir/usr/lib/rstudio/bin"
  rm lib*.so.*
  cd "$pkgdir/usr/bin"
  ln -s -f ../lib/rstudio/bin/rstudio rstudio-bin
}
