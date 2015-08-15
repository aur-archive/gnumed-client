# Maintainer: FreeWilly

pkgname=gnumed-client
pkgver=1.5.4
pkgrel=1
pkgdesc="Electronic Medical Record software in multiple languages to assist and improve longitudinal care"
arch=('any')
url="http://wiki.gnumed.de/bin/view/Gnumed"
license=('GPL')
depends=('python2' 'python2-egenix-mx-base' 'wxpython') 
optdepends=('python-pyenchant' 'python2-gnuplot' 'kdepim-console' 'aspell' 'xsane'
            'texlive-latexextra' 'gtklp' 'mc' 'python2-psycopg2')
source=(http://www.gnumed.de/downloads/client/1.5/$pkgname.$pkgver.tgz)
backup=(etc/gnumed/gm_ctl_client.conf etc/gnumed/gnumed.conf etc/gnumed/gnumed-client.conf)
md5sums=('c7f8c93451d0d68e26c20eb6c2b98a09')

build() {
  sed 's/python/python2/g' -i "$srcdir"/$pkgname.$pkgver/client/gnumed
}

package() {
  cd "$srcdir"/$pkgname.$pkgver

  # launcher
  install -Dm755 client/gnumed "$pkgdir"/usr/bin/gnumed
  install -Dm644 client/gnumed-client.desktop "$pkgdir"/usr/share/applications/gnumed-client.desktop

  # config files
  install -Dm644 client/connectors/gm_ctl_client.conf "$pkgdir"/etc/gnumed/gm_ctl_client.conf
  install -m644 client/doc/gnumed.conf.example "$pkgdir"/etc/gnumed/gnumed.conf
  install -m644 client/etc/gnumed/gnumed-client.conf.example "$pkgdir"/etc/gnumed/gnumed-client.conf

  # graphics
  install -Dm644 client/bitmaps/gnumedlogo.png "$pkgdir"/usr/share/icons/gnumedlogo.png
  install -Dm644 client/bitmaps/gm_icon-serpent_and_gnu.xpm "$pkgdir"/usr/share/pixmaps/gm_icon-serpent_and_gnu.xpm
  install -Dm644 client/bitmaps/empty-face-in-bust.png "$pkgdir"/usr/share/gnumed/bitmaps/empty-face-in-bust.png
  install -m644 client/bitmaps/gnumedlogo.png "$pkgdir"/usr/share/gnumed/bitmaps/gnumedlogo.png
  install -m644 client/bitmaps/serpent.png $pkgdir/usr/share/gnumed/bitmaps/serpent.png

  # languages
#  install -Dm644 client/po/fr-gnumed.mo "$pkgdir"/usr/share/po/fr/LC_MESSAGES/gnumed.mo
  install -Dm644 client/po/fr-gnumed.mo "$pkgdir"/usr/share/locale/fr/LC_MESSAGES/gnumed.mo
#  install -Dm644 client/po/de-gnumed.mo "$pkgdir"/usr/share/po/de/LC_MESSAGES/gnumed.mo
  install -Dm644 client/po/de-gnumed.mo "$pkgdir"/usr/share/locale/de/LC_MESSAGES/gnumed.mo
#  install -Dm644 client/po/es-gnumed.mo "$pkgdir"/usr/share/po/es/LC_MESSAGES/gnumed.mo
  install -Dm644 client/po/es-gnumed.mo "$pkgdir"/usr/share/locale/es/LC_MESSAGES/gnumed.mo
#  install -Dm644 client/po/it-gnumed.mo "$pkgdir"/usr/share/po/it/LC_MESSAGES/gnumed.mo
  install -Dm644 client/po/it-gnumed.mo "$pkgdir"/usr/share/locale/it/LC_MESSAGES/gnumed.mo
#  install -Dm644 client/po/nb-gnumed.mo "$pkgdir"/usr/share/po/nb/LC_MESSAGES/gnumed.mo
  install -Dm644 client/po/nb-gnumed.mo "$pkgdir"/usr/share/locale/nb/LC_MESSAGES/gnumed.mo
#  install -Dm644 client/po/nl-gnumed.mo "$pkgdir"/usr/share/po/nl/LC_MESSAGES/gnumed.mo
  install -Dm644 client/po/nl-gnumed.mo "$pkgdir"/usr/share/locale/nl/LC_MESSAGES/gnumed.mo
#  install -Dm644 client/po/pl-gnumed.mo "$pkgdir"/usr/share/po/pl/LC_MESSAGES/gnumed.mo
  install -Dm644 client/po/pl-gnumed.mo "$pkgdir"/usr/share/locale/pl/LC_MESSAGES/gnumed.mo
#  install -Dm644 client/po/pt_BR-gnumed.mo "$pkgdir"/usr/share/po/pt_BR/LC_MESSAGES/gnumed.mo
  install -Dm644 client/po/pt_BR-gnumed.mo "$pkgdir"/usr/share/locale/pt_BR/LC_MESSAGES/gnumed.mo
#  install -Dm644 client/po/ru-gnumed.mo "$pkgdir"/usr/share/po/ru/LC_MESSAGES/gnumed.mo
  install -Dm644 client/po/ru-gnumed.mo "$pkgdir"/usr/share/locale/ru/LC_MESSAGES/gnumed.mo

  # data
  install -dm755 "$pkgdir"/usr/lib/python2.7/site-packages/Gnumed/business
  cp -r client/business/* "$pkgdir"/usr/lib/python2.7/site-packages/Gnumed/business/
  install -dm755 "$pkgdir"/usr/lib/python2.7/site-packages/Gnumed/exporters
  cp -r client/exporters/* "$pkgdir"/usr/lib/python2.7/site-packages/Gnumed/exporters/
  install -dm755 "$pkgdir"/usr/lib/python2.7/site-packages/Gnumed/wxGladeWidgets
  cp -r client/wxGladeWidgets/*  "$pkgdir"/usr/lib/python2.7/site-packages/Gnumed/wxGladeWidgets/
  install -dm755 "$pkgdir"/usr/lib/python2.7/site-packages/Gnumed/wxpython/gui
  cp -r client/wxpython "$pkgdir"/usr/lib/python2.7/site-packages/Gnumed/
  install -m755 client/gnumed.py "$pkgdir"/usr/lib/python2.7/site-packages/Gnumed/gnumed.py

  # common
  install -dm755 "$pkgdir"/usr/lib/python2.7/site-packages/Gnumed/pycommon
  cp -r client/pycommon/* "$pkgdir"/usr/lib/python2.7/site-packages/Gnumed/pycommon/
  install -m644 client/__init__.py "$pkgdir"/usr/lib/python2.7/site-packages/Gnumed/__init__.py

  # docs
  install -dm755 "$pkgdir"/usr/share/doc/gnumed/user-manual
  cp -r client/doc/user-manual/* "$pkgdir"/usr/share/doc/gnumed/user-manual/
}
