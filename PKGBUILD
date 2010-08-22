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
source=("http://wua.la/files/${pkgname}.tar.gz"
	"wuala-jar-location.patch"
	"${pkgname}.png"
	"${pkgname}.desktop"
	"LICENSE")
md5sums=('b1405b131f5a33b25a83765bdddc5e2f'
         'dad792eb6d07a97f0498ee21cbd02740'
         '5c0d0ec01eaa7075fc7e3197d2a0a2ee'
         '6073b5fdda17ab8b423bde329adfa80f'
         '1085f1b2c391b8c72cb4b53b15191336')
sha1sums=('3e4914e13329cea56b29168359e2051f1b615f38'
          'c18d5e9342beb1cf321fe9c29bb5e21838cdb5db'
          'cae514b2e405ad0dfbad7cdbe04b7f82bd6294a9'
          'a3d25486b347e03143b1d86ff2a7d83f03ed4bad'
          '77427bc6023ad469b2158b1a22d4fea997244681')

build() {
	cd ${srcdir}/${pkgname}

	patch -Np1 -i ${srcdir}/wuala-jar-location.patch || return 1

	JAVA_DIR=${pkgdir}/usr/share/java/${pkgname}
	DOC_DIR=${pkgdir}/usr/share/doc/${pkgname}
	BIN_DIR=${pkgdir}/usr/bin

	# Directories
	install -d ${JAVA_DIR} ${DOC_DIR} ${BIN_DIR}

	# binary
	install -D wuala{,cmd} ${pkgdir}/usr/bin/

	# jar
	install -D loader3.jar ${JAVA_DIR}/

	# readme and copyright
	install -D readme.txt copyright ${DOC_DIR}


	# Desktop
	install -D ${srcdir}/${pkgname}.desktop ${pkgdir}/usr/share/applications/${pkgname}.desktop
	install -D ${srcdir}/${pkgname}.png ${pkgdir}/usr/share/icons/hicolor/64x64/apps/${pkgname}.png

	# License
	install -D ${srcdir}/LICENSE ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE

}
