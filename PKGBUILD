# Maintainer: Diego <cdprincipe@at@gmail@dot@com>

pkgname=solaar-git
pkgver=0.9.1.710.454fbcb
pkgrel=1
pkgdesc="Linux devices manager for the Logitech Unifying Receiver"
arch=("any")
url="http://pwr.github.io/Solaar/"
license=('GPL')
depends=('udev-logitech-unifying-git'
         'systemd'
         'python'
         'python-pyudev'
         'python-gobject'
         )
optdepends=('gtk3: required for GUI application'
            'gobject-introspection: required for GUI application'
            'python-gobject: required for GUI application'
            )
makedepends=('git')
provides=('solaar')
conflicts=('solaar')
install=solaar.install
source=('git://github.com/pwr/Solaar.git')
md5sums=('SKIP')

pkgver() {
  cd Solaar
#  echo $(head ChangeLog | grep -o '[0-9].*[0-9]').$(git rev-list --count HEAD).$(git rev-parse --short HEAD)
  echo $(cat "$srcdir/Solaar/lib/solaar/__init__.py" | grep version | grep -o '[0-9].*[0-9]').$(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

package() {
  cd "$srcdir/Solaar"
  python setup.py install --root="$pkgdir/" --optimize=1  
}

