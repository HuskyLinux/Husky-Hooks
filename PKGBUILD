# Maintainer: The-Repo-Club <The-Repo-Club@github.com>
# Contributor: The-Repo-Club <The-Repo-Club@github.com>
# shellcheck disable=all

pkgname=husky-hooks
pkgver=2022.10.03
pkgrel=1
pkgdesc='HuskyLinux pacman hooks'
arch=('any')
groups=('linuxrepos')
license=('MIT')
url=https://github.com/HuskyLinux/${pkgname}/tree/main/
depends=(libnotify)

source=(
  "$url/husky-os-release.hook"
  "$url/husky-lsb-release.hook"
  "$url/${pkgname}.hook"
  "$url/${pkgname}-runner"
  "$url/husky-reboot-required"
  "$url/husky-reboot-required.hook"
)
sha256sums=('8ad3f996bd9b9ab73a80fa659fd41cab6dc6e7d1c297bf464513224f7cc9dc81' '341a14c328849a852330fce7a1068bfae3bc7e3ca77b0d959f86e0b944d402da' 'e810cea18d82be7fa4f1390e457b4d862962290b00846c4af49f7379f4f608f8' '43396e466cfac0e86e269b001768a3080de7725ba0ee6ccf2b59f0d5830bd549' '6977bc1c6c435323366fd08be62bbec9be45d4775199c7163d2519bb46d49536' 'e897e0ca9497db2054a5f399d1d1f2acd55697998daf84899b5d308815b4b504')

package() {
  local hooks=$pkgdir/etc/pacman.d/hooks
  local bin=$pkgdir/usr/bin

  install -Dm644 husky-lsb-release.hook $hooks/husky-lsb-release.hook
  install -Dm644 husky-os-release.hook $hooks/husky-os-release.hook
  install -Dm644 ${pkgname}.hook $hooks/${pkgname}.hook
  install -Dm644 husky-reboot-required.hook $hooks/husky-reboot-required.hook

  install -Dm755 husky-reboot-required $bin/husky-reboot-required
  install -Dm755 ${pkgname}-runner $bin/${pkgname}-runner
}
