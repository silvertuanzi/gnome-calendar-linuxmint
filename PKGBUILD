# Maintainer: Silver Tuanzi

pkgname=gnome-calendar-linuxmint
_pkgname=gnome-calendar
pkgver=48.1
_realpkgver=48.1+mint1
_pkgver=gigi
pkgrel=3
pkgdesc="Simple and beautiful calendar application designed to perfectly fit the GNOME desktop. Linux Mint version to fit the Cinnamon desktop."
url="https://apps.gnome.org/Calendar"
arch=(x86_64)
license=(GPL-3.0-or-later)
depends=(
  dconf evolution-data-server geoclue glib2 glibc graphene gtk4 libgcc libadwaita hicolor-icon-theme libedataserverui4 libgweather-4 libsoup3 libical
)
makedepends=(
  git glib2-devel meson
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

source=("http://packages.linuxmint.com/pool/upstream/g/gnome-calendar/gnome-calendar_${_realpkgver}+${_pkgver}.tar.xz" '0001-Support-libical-4.0.0.patch')
sha256sums=('16e5c6ba5f3640c1e39372bcc5c254a85648918a3711e4b713714679bbe92a52' 'SKIP')

prepare() {
  cd "$srcdir/gnome-calendar"
  patch -p1 <"$srcdir/0001-Support-libical-4.0.0.patch"
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

