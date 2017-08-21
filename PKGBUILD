# Maintainer: Eric Vidal <eric@obarun.org>

pkgname=svnserve-s6serv
pkgver=0.1
pkgrel=2
pkgdesc="svnserve service for s6"
arch=(x86_64)
license=('beerware')
depends=('subversion' 's6' 's6-rc' 's6-boot')
conflicts=()
source=('svnserve.daemon.run.s6'
		'svnserve.log.run.s6'
		'svnserve.logd'
		'LICENSE')
md5sums=('dfe6f49fe4d972d51e9ef2cdd7c86566'
         'a3d170e0c2b35a430b29d8fe588b52e0'
         '5067159d214a07dd968416876e53c80b'
         '191a37ae657aa17e37e75d0242865dba')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

package() {
	
	# daemon
	install -Dm 0755 "$srcdir/svnserve.daemon.run.s6" "$pkgdir/etc/s6-serv/available/classic/svnserve/run"
	
	# log
	install -Dm 0755 "$srcdir/svnserve.log.run.s6" "$pkgdir/etc/s6-serv/available/classic/svnserve/log/run"
	install -Dm 0644 "$srcdir/svnserve.logd" "$pkgdir/etc/s6-serv/log.d/serv/svnserve"
	
	install -Dm 0644 "$srcdir/LICENSE" "$pkgdir/usr/share/licenses/svnserve-s6serv/LICENSE"
}
