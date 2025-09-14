# Maintainer: Silver Tuanzi

pkgname=gnome-calendar-linuxmint
_pkgname=gnome-calendar
pkgver=48.1
_realpkgver=48.1+mint1
_pkgver=gigi
pkgrel=1
pkgdesc="Simple and beautiful calendar application designed to perfectly fit the GNOME desktop. Linux Mint version to fit the Cinnamon desktop."
url="https://apps.gnome.org/Calendar"
arch=(x86_64)
license=(GPL-3.0-or-later)
depends=(
  cairo
  dconf
  evolution-data-server
  gcc-libs
  geoclue
  glib2
  glibc
  graphene
  gsettings-desktop-schemas
  gtk3
  hicolor-icon-theme
  libhandy
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

source=("http://packages.linuxmint.com/pool/upstream/g/gnome-calendar/gnome-calendar_${_realpkgver}+${_pkgver}.tar.xz")
sha256sums=('16e5c6ba5f3640c1e39372bcc5c254a85648918a3711e4b713714679bbe92a52')

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

