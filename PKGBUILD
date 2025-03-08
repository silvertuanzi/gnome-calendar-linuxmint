# Maintainer: Silver Tuanzi

pkgname=gnome-calendar-linuxmint
_pkgname=gnome-calendar
pkgver=41.2
_realpkgver=43.really41+mint2
_pkgver=wilma
pkgrel=2
pkgdesc="Simple and beautiful calendar application designed to perfectly fit the GNOME desktop. Linux Mint version to fit the Cinnamon desktop."
url="https://apps.gnome.org/Calendar"
arch=(x86_64)
license=(GPL-3.0-or-later)
depends=(
  dconf
  evolution-data-server
  gcc-libs
  geoclue
  glib2
  glibc
  graphene
  gsettings-desktop-schemas
  gtk3
  libgweather-4
  libical
  libsoup3
  libdazzle
  pango
)
makedepends=(
  git
  glib2-devel
  meson
)
provides=(
    ${_pkgname}
)
conflicts=(
    ${_pkgname}
)
optdepends=(
  'gnome-online-accounts-gtk: Manage online accounts'
  'xdg-desktop-portal-impl: Various user settings (e.g. 24-hour clock)'
)

source=("http://packages.linuxmint.com/pool/upstream/g/gnome-calendar/gnome-calendar_${_realpkgver}+${_pkgver}.tar.xz" "fix.patch")
sha256sums=('c4e67d3973ee5353c983d2ac5d3362914ca7ee2289fb1cd76d3d018d5a5df689' 'SKIP')

prepare() {
  cd $_pkgname
  patch -Np1 -i ../fix.patch
}

build() {
  arch-meson $_pkgname build
  meson compile -C build
}

check() {
  meson test -C build --print-errorlogs
}

package() {
  meson install -C build --destdir "$pkgdir"
}

