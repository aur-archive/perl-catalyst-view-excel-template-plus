# Maintainer: jsteel <jsteel at aur.archlinux.org>

pkgname='perl-catalyst-view-excel-template-plus'
_pkgname='Catalyst-View-Excel-Template-Plus'
pkgver='0.03'
pkgrel='2'
pkgdesc="A Catalyst View for Excel::Template::Plus"
arch=('any')
license=('PerlArtistic' 'GPL')
depends=('perl-excel-template-plus')
options=('!emptydirs')
url="http://search.cpan.org/dist/$_pkgname"
source=(http://search.cpan.org/CPAN/authors/id/R/RB/RBO/$_pkgname-$pkgver.tar.gz)
md5sums=('b74670b444ca46078ed9dd48b7cb93fa')

build() {
  ( export PERL_MM_USE_DEFAULT=1 PERL5LIB=""                 \
      PERL_AUTOINSTALL=--skipdeps                            \
      PERL_MM_OPT="INSTALLDIRS=vendor DESTDIR='$pkgdir'"     \
      PERL_MB_OPT="--installdirs vendor --destdir '$pkgdir'" \
      MODULEBUILDRC=/dev/null

    cd "$srcdir"/$_pkgname-$pkgver

    /usr/bin/perl Makefile.PL

    make
  )
}

check() {
  cd "$srcdir"/$_pkgname-$pkgver

  ( export PERL_MM_USE_DEFAULT=1 PERL5LIB=""
    make test
  )
}

package() {
  cd "$srcdir"/$_pkgname-$pkgver

  make install
}
