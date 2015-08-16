# Maintainer: Nicolas Pouillard (http://nicolaspouillard.fr)
# Contributors:
#   Peter Simons <simons@cryp.to>
#   Andreas Hilboll <andreas@hilboll.de>
#   kljohann@gmail.com
pkgname=mr
pkgver=1.20130826
pkgrel=1
pkgdesc='Checkout, update, or perform other actions on a set of VC repositories.'
arch=('any')
url='http://kitenet.net/~joey/code/mr/'
license=('GPL2')
depends=('perl' 'perl-libwww' 'perl-html-parser' 'perl-uri')
makedepends=('git' 'rsync')
optdepends=('git: support for git repositories'
            'cvs: support for cvs repositories'
            'svn: support for subversion repositories'
            'mercurial: support for mercurial repositories'
            'bzr: support for bzr repositories'
            'darcs: support for darcs repositories')
source=($pkgname::git://git.kitenet.net/$pkgname#tag=$pkgver)
md5sums=(SKIP)

build() {
  cd "$pkgname"
  make
}

check() {
  cd "$pkgname"
  make test
}

package() {
  cd "$pkgname"
  install -m755 -D mr "${pkgdir}/usr/bin/mr"
  install -m755 -D webcheckout "${pkgdir}/usr/bin/webcheckout"
  install -m644 -D mr.1 "${pkgdir}/usr/share/man/man1/mr.1"
  install -m644 -D webcheckout.1 "${pkgdir}/usr/share/man/man1/webcheckout.1"
  install -m644 -D README "${pkgdir}/usr/share/doc/${pkgname}/README"
  install -m644 -D lib/git-fake-bare "${pkgdir}/usr/share/mr/git-fake-bare"
  install -m644 -D lib/git-subtree "${pkgdir}/usr/share/mr/git-subtree"
  install -m644 -D lib/git-svn "${pkgdir}/usr/share/mr/git-svn"
  install -m644 -D lib/unison "${pkgdir}/usr/share/mr/unison"
  install -m644 -D lib/vcsh "${pkgdir}/usr/share/mr/vcsh"
  install -m644 -D lib/repo "${pkgdir}/usr/share/mr/repo"
  install -m644 -D lib/vis "${pkgdir}/usr/share/mr/vis"
}
