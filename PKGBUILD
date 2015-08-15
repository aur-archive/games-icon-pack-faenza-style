# Maintainer: Spike29 <leguen.yannick@gmail.com>

pkgname='games-icon-pack-faenza-style'
pkgver='20110916'
pkgrel='2'
pkgdesc="A set of icons in the Faenza style for various GNU/Linux games"
arch=('any')
license=('GPL3')
url="http://half-left.deviantart.com/art/Games-Icon-Pack-Faenza-Style-189876623"
depends=('faenza-icon-theme')
makedepends=('unzip')
source=('http://www.deviantart.com/download/189876623/games_icon_pack___faenza_style_by_half_left-d351pqn.zip')
md5sums=('8755db7e54f99a5a6dfc60a62c3eca09')
_theme="1"

build() {
	cd $srcdir
	tar xzf Game-Icons-pack.tar.gz
}

package() {
	mkdir -p $pkgdir/usr/share/icons/
	cp -r $srcdir/Game-Icons $pkgdir/usr/share/icons/
	
	# choosing the right Faenza theme
	echo "Which Faenza theme do you want to use with this icon pack ?"
	echo "(1) Faenza"
	echo "(2) Faenza-Dark"
	echo "(3) Faenza-Darker"
	echo "(4) Faenza-Darkest"
	read _theme
	
	# modifying index.theme in order to match the chosen Faenza theme
	if [ $_theme = "2" ]
	then 
		sed -e 's/Inherits=Faenza/Inherits=Faenza-Dark/g' -i \
		"$pkgdir/usr/share/icons/Game-Icons/index.theme"
	elif [ $_theme = "3" ]
	then 
		sed -e 's/Inherits=Faenza/Inherits=Faenza-Darker/g' -i \
		"$pkgdir/usr/share/icons/Game-Icons/index.theme"
	elif [ $_theme = "4" ]
	then 
		sed -e 's/Inherits=Faenza/Inherits=Faenza-Darkest/g' -i \
		"$pkgdir/usr/share/icons/Game-Icons/index.theme"
	fi
}
