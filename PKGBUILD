# Maintainer: Kevin Cox <kevincox.ca@gmail.com>
pkgname='kate-themes'
pkgver='1'
pkgrel=1
pkgdesc='A collection of themes for the kate text editor.'
url='http://example.org/'
arch=('any')
license=('varied')
depends=()
makedepends=()
install='kate-themes.install'

source=('kate-update-themes.sh'
        'kateschemarc.oblivion'
        'http://kde-look.org/CONTENT/content-files/53388-darK.tar.gz'
        'https://github.com/hayalci/kde-colors-solarized/tarball/5dfa323f3565af7c1a9263965da2b714226e9287'
        'http://kde-look.org/CONTENT/content-files/66209-zenburn-kate.tar.gz'
        'http://kde-look.org/CONTENT/content-files/140718-DarkOxygen.zip'
        'https://opendesktop.org/CONTENT/content-files/127797-kate-dcrBlackGold.txt'
        'http://kde-look.org/CONTENT/content-files/126671-darklum.tar.gz'
        'http://kde-look.org/CONTENT/content-files/34243-Coolate.tar.gz'
        'https://github.com/kevincox/kate-themes/archive/v2.tar.gz'
       ) 
sha1sums=('b9584647be1cc3063a00ceeba6cef82b9459126f'
          '57aa2d803f6b7549621ef97718a1f9d958335dc0'
          '2d7c0c3d4b8cf066604059293b80fa4be010e044'
          'bdbc4c82afe0bb808f6af41ae0d55644a693b271'
          '861cc96b3301f342f42c942c944a877394a735fe'
          '94b3ca7f15c32a22c6a53ec7ae51996cb4492b0d'
          'bd391ee704ad77a4a33f00b61bd4d280cd3b047f'
          '4ce0492a09c806ded5c4b207b44fda07f88910c5'
          '48369c87e63c9ba162522bbd869a8f004489e08b'
          '37b278f6c941eb85656a015e06097bf0b12e99d3')

_installtheme() {
	mkdir -pv "$pkgdir/usr/share/config/kateschemarc.d/"
	install -vm 664 "$1" "$pkgdir/usr/share/config/kateschemarc.d/"
}
_installhighlighting() {
	mkdir -pv "$pkgdir/usr/share/config/katesyntaxhighlightingrc.d/"
	install -vm 664 "$1" "$pkgdir/usr/share/config/katesyntaxhighlightingrc.d/"
}

build() {
	_installtheme        'kateschemarc.oblivion'

	_installtheme        'darK/kateschemarc.darK'
	_installhighlighting 'darK/katesyntaxhighlightingrc.darK'

	cd 'hayalci-kde-colors-solarized-'*
	_installtheme        'Solarized Dark.kateschema'
	_installhighlighting 'Solarized Dark.katesyntax'
	_installtheme        'Solarized Light.kateschema'
	_installhighlighting 'Solarized Light.katesyntax'
	cd ..

	_installtheme        'zenburn/kateschemarc.zenburn'
	_installhighlighting 'zenburn/katesyntaxhighlightingrc.zenburn'

	_installtheme        'DarkOxygen/kateschemarc.darkoxygen'
	_installhighlighting 'DarkOxygen/katesyntaxhighlightingrc.darkoxygen'

	_installtheme        '127797-kate-dcrBlackGold.txt'

	_installtheme        'darklum/kateschemarc'
	_installhighlighting 'darklum/katesyntaxhighlightingrc'

	_installtheme        'Coolate/kateschemarc.coolate'
	_installhighlighting 'Coolate/katesyntaxhighlightingrc.coolate'

	cd 'kate-themes-'*
	_installtheme        'kateschemarc.chalk'
	_installhighlighting 'katesyntaxhighlightingrc.chalk'
	cd ..
	
	install -Dm 775 'kate-update-themes.sh' "$pkgdir/usr/bin/kate-update-themes"
}

