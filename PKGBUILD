pkgname=hephaestus
pkgver=20120227
pkgrel=1
pkgdesc="Pantheon Linux livecd/liveusb generation scripts"
arch=('any')
url="http://pantheonlinux.org"
license=('GPL')
depends=('devtools' 'libisoburn' 'squashfs-tools' 'archiso-git')
optdepends=('qemu: quickly test isos')
makedepends=('mercurial')
provides=('hephaestus')
conflicts=('hephaestus')
source=()
md5sums=()

_gitroot=https://.git
_gitname=hephaestus

build() {
  cd ${srcdir}
  msg "Connecting to projects.archlinux.org GIT server..."

  if [ -d ${srcdir}/$_gitname ]; then
    cd $_gitname && git pull origin
    msg "Local files are updated."
  else
    git clone $_gitroot
  fi

  msg "Git clone done or server timeout"
  msg "Starting make..."

  if [ -d ${srcdir}/$_gitname-build ]; then
    rm -rf ${srcdir}/$_gitname-build
  fi

  git clone ${srcdir}/$_gitname ${srcdir}/$_gitname-build || return 1
  cd ${srcdir}/$_gitname-build/bin || return 1
  make DESTDIR="$pkgdir" install
}

# vim:set ts=2 sw=2 et:

