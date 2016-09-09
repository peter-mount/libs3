# Maintainer: Peter Mount <peter@retep.org>

pkgname="libs3"
pkgver="2.0"
pkgrel="1"
pkgdesc="Amazon S3 library"
arch="x86_64"
url="https://github.com/peter-mount/libs3"
license="LGPL"
source=""
subpackages="$pkgname-dev"
depends="libxml2 curl"
depends_dev="libxml2-dev curl-dev"
#triggers="$pkgname-bin.trigger=/lib:/usr/lib:/usr/glibc-compat/lib"

builddeps() {
  sudo apk add $depends $depends_dev
}

package() {
  wget https://github.com/bji/libs3/archive/$pkgver.zip
  rm -rf libs3-$pkgver
  unzip $pkgver.zip
  cd libs3-$pkgver
  make
  mkdir -p "$pkgdir/usr/bin"
  cp -rp build/bin/* "$pkgdir/usr/bin"
  mkdir -p "$pkgdir/usr/lib"
  cp -rp build/lib/* "$pkgdir/usr/lib"
}

dev() {
# depends="$pkgname $depends_dev"
  mkdir -p "$subpkgdir/usr/include"
  cp -rp libs3-$pkgver/build/include/* "$subpkgdir/usr/include"
}
