# $Id: 3bcffd857f534eb5d2639eea7e60bf6674c4387a $
# Maintainer: Ido Rosen <ido@kernel.org>
# Contributor: frio <development@frio.name>
#
# NOTE: To request changes to this package, please submit a pull request
#       to the GitHub repository at https://github.com/ido/packages-archlinux
#       Otherwise, open a GitHub issue.  Thank you! -Ido
#

pkgname=lxc-docker
pkgver=0.7.0
pkgrel=4
pkgdesc="Docker - the Linux container runtime"
arch=('x86_64')
url="https://github.com/dotcloud/docker"
license=('Apache License 2.0')
depends=('bridge-utils' 'iproute2' 'device-mapper' 'lxc')
provides=('lxc-docker')
source=(
    "https://get.docker.io/builds/Linux/x86_64/docker-${pkgver}" 
    'docker.service'
    'docker.bash'
    'docker.zsh'
    'docker.install'
#    'docker.sysctl'  
)
conflicts=('lxc-docker-git' 'lxc-docker-nightly')
replaces=('dotcloud-docker')
sha512sums=(
    '518a8a797501aec2586ed4dc16f0ac8e6246a576706c02dc51d6e024690536fe8f4c3cb40745fc49fd5280a3358bf2099475c5ec27e8ab6057c14bf85c6b7cdb'
    'fdb7591a4c2df7fc805c6e5aa3bb5c3406b0702e62df286e4b3541be5a6a3169514523ab892ca8ac9d223492da35f9ed51f99a6ad6885424564b8bf618fe91b5'
    '614bc37c646a3404c91e72897083ae9e4f8aca63f761b7d7e94fe029ca8bbc2c7e2f29379e55f84fa470e978bd997632621d46615a45a24fa4675ab9cdfb1888'
    '0a4f82a6f9aaa4520ecde3946545400d9f206fd81bd55f520a198be6f607bc54f6736d6c9d0e3684cb6f1b97f256d151950551c1db48375dc646ef26ef1e126d'
    'edbc12e91b52386a0e119b557b24e483c90c563ef3e7f2bde590baae09d9d88c7cdc2c979ca7cbf1cf249faf62f32da31b530cb9ac698d0dacfb8f18c8059410'
#    '8e09f5c0bda88f52a3497dc28d0193d8ba598e9db246c576cf4902abe5653ce66f942446e4d433f27b637fdcd0bccf322c2b2c9defbd978236859e6027798c7f'
)
install='docker.install'

package() {
  # install systemd service unit
  install -D -m 644 "$srcdir/docker.service" "$pkgdir/usr/lib/systemd/system/docker.service"

  # install docker binary
  install -D -m 755 "$srcdir/docker-$pkgver" "$pkgdir/usr/bin/docker"

#  install -D -m 644 "$srcdir/docker.sysctl" "$pkgdir/etc/sysctl.d/docker.conf"
  install -D -m 644 "$srcdir/docker.bash" "$pkgdir/usr/share/bash-completion/completions/docker"
  install -D -m 644 "$srcdir/docker.zsh" "$pkgdir/usr/share/zsh/site-functions/_docker"

}
