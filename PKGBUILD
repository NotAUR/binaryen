install_prefix=''
binaryen_folder_path=''

pkgname=('binaryen')
pkgver=119
pkgrel=1
pkgdesc="Optimizer and compiler/toolchain library for WebAssembly"
arch=('x86_64')
url="https://github.com/WebAssembly/binaryen"
license=('Apache')

source+=(
  "https://github.com/WebAssembly/binaryen/releases/download/version_${pkgver}/binaryen-version_${pkgver}-x86_64-linux.tar.gz"
)
sha512sums+=(
  '09287200b1584e68379c16423a4559ce6af0eff9e2d0abf4cc22f8a72689c7246596c195e4e86973618e048857eac12b97fdf8530000d440dcda4514449e1336'
)

set_variables() {
  binaryen_folder_path="$srcdir/binaryen-version_${pkgver}"
  install_prefix='/usr/local'
}

prepare() {
  set_variables

  cd "${binaryen_folder_path}" || return 1
}

package() {
  set_variables

  cd "${binaryen_folder_path}" || return 1

  find . -exec install -D -m 755 {} "${pkgdir}/${install_prefix}/{}" \;
}

