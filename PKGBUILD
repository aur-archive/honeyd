# Maintainer: Michael P <ptchinster@archlinux.us>
# Contributor: Michael P <ptchinster@archlinux.us>

pkgname=honeyd
pkgver=1.5c
pkgrel=5
pkgdesc="A small daemon that creates virtual hosts on a network."
depends=('libdnet' ' libevent' 'libdnsres' 'libpcap' 'pcre' 'zlib')
source=(http://www.honeyd.org/uploads/$pkgname-$pkgver.tar.gz)
md5sums=('9887b44333e380a2205f64fa245cb727')
arch=(i686 x86_64)
url="http://www.honeyd.org"
license=("GPL")

build()
{
	cd $srcdir/$pkgname-$pkgver
  
	mkdir -p $pkgdir/usr/share/honeyd

	./configure --prefix=/usr
	make || return 1
	make prefix=$pkgdir/usr install
  
	# Fix permissions on webserver dirs
	for dir in webserver webserver/htdocs webserver/htdocs/graphs \
	webserver/htdocs/images webserver/htdocs/styles webserver/htdocs/templates \
	webserver/htdocs/templates/inc
		do chmod 755 $pkgdir/usr/share/honeyd/$dir
	done
}

