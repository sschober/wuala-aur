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
source=(http://wua.la/files/${pkgname}.tar.gz)

build() {
	cd ${srcdir}/${pkgname}

	# Directories
	install -d ${pkgdir}/usr/{share/${pkgname}/,bin/}

	# Application
	install -D * ${pkgdir}/usr/share/${pkgname}/

	# Binaries
	#ln -s /usr/share/${pkgname}/${pkgname} ${pkgdir}/usr/bin/${pkgname}
	#ln -s /usr/share/${pkgname}/${pkgname}cmd ${pkgdir}/usr/bin/${pkgname}-cmd
	install -D ${startdir}/extra/${pkgname}-* ${pkgdir}/usr/bin/

	# Desktop
	install -D ${startdir}/extra/${pkgname}.desktop ${pkgdir}/usr/share/applications/${pkgname}.desktop
	install -D ${startdir}/extra/${pkgname}.png ${pkgdir}/usr/share/icons/hicolor/64x64/apps/${pkgname}.png

	# License
	install -D ${startdir}/extra/LICENSE ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE

	# User
	install -o ${USER} -m 700 -d ${pkgdir}/${HOME}/{${pkgname}/,.kde4/Autostart/}
	install -o ${USER} -m 700 -D ${pkgdir}/usr/share/${pkgname}/* ${pkgdir}/${HOME}/${pkgname}/
	#ln -s /usr/bin/${pkgname}-tray ${pkgdir}/${HOME}/.kde4/Autostart/${pkgname}-tray

	# Old
	#rm -rf ${pkgdir}/${HOME}/${pkgname}/Prog4/
}

sha1sums=('3e4914e13329cea56b29168359e2051f1b615f38')
