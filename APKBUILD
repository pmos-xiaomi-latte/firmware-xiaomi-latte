pkgname=firmware-xiaomi-latte
pkgver=1
pkgrel=2
pkgdesc="Firmware files for Xiaomi Mi Pad 2"
url="https://github.com/pmos-xiaomi-latte/firmware-proprietary"
arch="x86_64"
depends="linux-firmware-intel"
license="proprietary"
options="!strip !check !archcheck !spdx !tracedeps pmb:cross-native"
_commit="5683cfb5a0bb9c47f7a27e001c840a6c3485ad09"
source="$pkgname.tar.gz::$url/archive/$_commit.tar.gz
	firmware.files"

package() {
	cd "$srcdir/$pkgname-$_commit/"
	while IFS="" read -r _i || [ -n "$_i" ]; do
		[ ! -d $(dirname $_i) ] && mkdir -p $(dirname $_i)
		install -Dm644 $_i "$pkgdir/$_i"
	done < "$srcdir/firmware.files"
}

sha512sums="
c8119956ec449f2f4189647001b3c1784c573229d7da933f2ec478e6d9ca26bb928354b71998388da2c48fd971587d04d493a444ea09149d1c897b1766738a9d  firmware-xiaomi-latte.tar.gz
e6116ee2997f129dfd97f089b738ec10cdb06217f56d487f981050abcfc2d971eeb3c2bd64ed6bac0c9e95c40129d886f15bcc9caf8d73d986729d6d70b35a4f  firmware.files
"
