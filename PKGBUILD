pkgname=douane-dialog
pkgver=1
pkgrel=1
pkgdesc="Douane Firewall Kernel GTK GUI"
arch=('i686' 'x86_64')
url="http://douaneapp.com/"
license=('GPL2')
depends=('')
makedepends=('git'
'boost'
'log4cxx'
'gtkmm3'
'dbus-c++')
source=('git+https://github.com/Douane/douane-dialog.git'
'git+https://github.com/Douane/douane-dbus.git')
md5sums=('SKIP'
'SKIP')
 
prepare() {
cd "$srcdir/$pkgname"
git submodule init
git config submodule.douane-dbus.url $srcdir/douane-dbus
git submodule update
}
 
pkgver() {
cd "$srcdir/$pkgname"
# Use the tag of the last commit
git describe --long | sed -E 's/([^-]*-g)/r\1/;s/-/./g'
}
 
build() {
cd "$srcdir/$pkgname"
 
msg2 "Starting make..."
make
}
 
package() {
# Install
cd "$srcdir/$pkgname"
msg2 "Starting make install..."
make DESTDIR="${pkgdir}" install
 
}
