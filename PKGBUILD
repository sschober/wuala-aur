# Wuala: Installer: Arch
# Contributor: Xavion <Xavion (dot) 0 (at) Gmail (dot) com>

pkgname=wuala
pkgver=3
pkgrel=20100622
pkgdesc="A new way of storing, sharing and publishing files on the Internet.  It's free, simple and secure."
arch=("any")
url="http://wua.la/"
license=("custom")
depends=("java-runtime" "rpcbind" "nfs-utils")
options=(!emptydirs)
source=("http://wua.la/files/${pkgname}.tar.gz" "wuala-jar-location.patch")
md5sums=('b1405b131f5a33b25a83765bdddc5e2f'
         'dad792eb6d07a97f0498ee21cbd02740')
sha1sums=('3e4914e13329cea56b29168359e2051f1b615f38'
	  'c18d5e9342beb1cf321fe9c29bb5e21838cdb5db')

build() {
	cd ${srcdir}/${pkgname}

	patch -Np1 -i ../wuala-jar-location.patch || return 1

	JAVA_TARG=${pkgdir}/usr/share/java/${pkgname}

	# Directories
	install -d ${pkgdir}/usr/{share/${pkgname}/,bin/}
	install -d ${JAVA_TARG}

	# binary
	install -D wuala{,cmd} ${pkgdir}/usr/bin/

	# jar
	install -D loader3.jar ${JAVA_TARG}/

	# readme and copyright
	install -D readme.txt copyright ${pkgdir}/usr/share/${pkgname}/


	# Desktop
	install -D ${startdir}/extra/${pkgname}.desktop ${pkgdir}/usr/share/applications/${pkgname}.desktop
	install -D ${startdir}/extra/${pkgname}.png ${pkgdir}/usr/share/icons/hicolor/64x64/apps/${pkgname}.png

	# License
	install -D ${startdir}/extra/LICENSE ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE

}
