# Contributor: Orson Teodoro <orsonteodoro@hotmail.com>
# Based on work by Nicola Squartini <tensor5@gmail.com> and Alpine contributors and maintainers of the community/chromium package and main/nodejs package
# Arch Linux Source: https://git.archlinux.org/svntogit/community.git/tree/trunk/PKGBUILD?h=packages/electron
# Maintainer: Orson Teodoro <orsonteodoro@hotmail.com>
pkgname=electron
pkgver=1.8.2
_pkgver=$pkgver
pkgrel=0
pkgdesc="Build cross platform desktop apps with JavaScript, HTML, and CSS"
url="https://electronjs.org/"
arch="x86_64"
license="MIT"

#DEBUG="1"

# Chromium is 18 million lines of code so I recommend using ccache for debugging if you are incrementally debugging the code or distcc if you have a lot of computers in your compile farm
# set to either distcc, ccache, or unset
_ccwrapper="ccache"

_nodejsmakedepends="
	libuv>=1.19.1-r1
	libuv-dev>=1.19.1-r1
	python2
	openssl-dev
	zlib-dev
	linux-headers
	paxmark
	binutils-gold
	http-parser-dev
	ca-certificates
	c-ares-dev
	"

#	libevent-dev 
#	re2-dev
_electronmakedepends="nodejs-dev
	nodejs-npm
	clang-dev
	python2-dev
	dbus-dev 
	gtk+3.0-dev 
	libnotify-dev 
	libgnome-keyring-dev 
	gconf-dev 
	cups-dev 
	libcap-dev 
	libxtst-dev 
	alsa-lib-dev 
	libxrandr-dev 
	nss-dev 
	gperf 
	bison 
	py-setuptools 
	ffmpeg-dev
	harfbuzz-dev 
	pulseaudio-dev
	llvm5-dev
	linux-headers
        libdrm-dev
        harfbuzz-dev
	"

_chromiumdepends="xdg-utils"
_chromiumdepends_dev=" "
_chromiummakedepends="$depends_dev
	alsa-lib-dev
	bash
	binutils-gold
	bison flex
	bsd-compat-headers
	bzip2-dev
	cairo-dev
	cups-dev
	dbus-glib-dev
	eudev-dev
	ffmpeg-dev
	findutils
	flac-dev
	freetype-dev
	gnutls-dev
	gperf
	gtk+3.0-dev 
	gzip
	harfbuzz-dev
	hunspell-dev
	hwdata-usb
	jpeg-dev
	jsoncpp-dev
	krb5-dev
	libbsd-dev
	libcap-dev
	libelf-dev
	libexif-dev
	libgcrypt-dev
	libgnome-keyring-dev
	libjpeg-turbo-dev
	libpng-dev
	libusb-dev
	libwebp-dev
	libxcomposite-dev
	libxcursor-dev
	libxinerama-dev
	libxrandr-dev
	libxscrnsaver-dev
	libxslt-dev
	libxtst-dev
	linux-headers
	mesa-dev
	mesa-dev
	minizip-dev
	ninja
	nodejs
	nss-dev
	paxmark
	pciutils-dev
	perl
	python2
	snappy-dev
	speex-dev
	sqlite-dev
	xdg-utils
	yasm
	zlib-dev
	"
#	libxml2-dev

depends="$_chromiumdepends"
makedepends="$_electronmakedepends $_chromiummakedepends $_nodejsmakedepends"

if [[ -n "$_ccwrapper" && "$_ccwrapper" == "ccache" ]] ; then
	makedepends="$makedepends ccache"
elif [[ -n "$_ccwrapper" && $_ccwrapper == "distcc" ]] ; then
	makedepends="$makedepends distcc"
fi

case "${CARCH}" in
        x86_64) target_arch=x64;;
        x86) target_arch=ia32;;
        arm) target_arch=arm;;
esac

subpackages="$pkgname-doc"
options="!check"

_botopkgname="boto"
_boto_gitrev="f7574aa6cc2c819430c1f05e9a1a1a666ef8169b"

_breakpadpkgname="chromium-breakpad"
_breakpad_gitrev="82f0452e6b687b3c1e14e08d172b2f3fb79ae91a"

_breakpadsrcpkgname="src"
_breakpadsrc_gitrev="2fcb8afbc807cf54c6de1b15fe71f027052045fd"
_breakpadsrcgiturl="https://chromium.googlesource.com/breakpad/breakpad/src"

_crashpadpkgname="crashpad"
_crashpad_gitrev="f7c320766756a8aaa45ccbcff2945053d9f7e109"

_depottoolspkgname="depot_tools"
_depottools_gitrev="4fa73b8ca6899bc69577932b80145a6bf07e4424"
_depottoolsgiturl="https://chromium.googlesource.com/chromium/tools/depot_tools"

_gyppkgname="gyp"
_gyppkg_gitrev="549e55a22765ccf99e46b419b2dff6338bcac64a"

_libchromiumcontentpkgname="libchromiumcontent"
_libchromiumcontent_gitrev="dbd83b6b953ae38c764f9cb3ca1a03bd741928fe"

_libchromiumcontent_botopkgname="boto"
_libchromiumcontent_boto_gitrev="c3b81eb115e469b9df1ff8c379d3208327da2c84"

_libchromiumcontent_depottoolspkgname="depot_tools"
_libchromiumcontent_depottools_gitrev="c55eecf76bdb96b904aaaee93fe4c67bbbb102d9"
_libchromiumcontentdepottoolsghurl="https://chromium.googlesource.com/chromium/tools/depot_tools"

_nativematepkgname="native-mate"
_nativemate_gitrev="bf92fa88b735b8c9ff951e6ef78a531bd10e8778"

_nodepkgname="node"
_node_gitrev="2586ef1eb5f5f53da2c1852efb47c20dc8888534"

_pdfviewerpkgname="pdf-viewer"
_pdfviewer_gitrev="beb36874a6b61d7a18b92bf7dcd1f0661e4c59cf"

#dependency of pdfviewer
_gritpkgname="grit"
_grit_gitrev="9536fb6429147d27ef1563088341825db0a893cd"
_gritghurl="https://chromium.googlesource.com/chromium/src/tools/grit.git"

_requestspkgname="requests"
_requests_gitrev="e4d59bedfd3c7f4f254f4f5d036587bcd8152458"

# reported by libchromiumcontent/VERSION
_chromiumpkgname="chromium"
_chromiumpkgver="59.0.3071.115"

_lsspkgname="lss"

#from community/chromium
_chromiumpatches="
        chromium-widevine.patch
        default-pthread-stacksize.patch
        gcc6.patch
        gn_bootstrap.patch
        last-commit-position.patch
        musl-fixes.patch
        musl-hacks.patch
        musl-sandbox.patch
        no-execinfo.patch
        no-getcontext.patch
        no-mallinfo.patch
        resolver.patch
        unset-madv_free.patch
        swiftshader.patch
        secure_getenv.patch
        chromium-48.0.2564.116-libusb_interrupt_event_handler.patch
        chromium-59.0.3071.115-gn-system.patch
        chromium-60.0.3112.78-jpeg-nomangle.patch
        chromium-60.0.3112.78-no-libpng-prefix.patch
        chromium-60.0.3112.78-no-zlib-mangle.patch

	Dl_info.patch
	chromium-use-system-ffmpeg.patch
	paxmark-mksnapshot-chromium.patch
	breakpad-wordsize.patch
	"

# top set is from alpine linux
# bottom set is from arch linux

_libchromiumcontentpatches="
	libchromiumcontent-static-library-only.patch
	libchromiumcontent-use-system-tools.patch
	libchromiumcontent-no-depot_tools.patch
	libchromiumcontent-chdir.patch

	libchromiumcontent-settings.patch

	libchromiumcontent-is_electron_build-1.patch
	libchromiumcontent-musl-fixes-2.patch

	libchromiumcontent-is_electron_build-3.patch
	libchromiumcontent-is_electron_build-4.patch
	libchromiumcontent-BUILDCONFIG.patch
	libchromiumcontent-static-v8.patch

	libchromiumcontent-TCP_SOCKET-dupe.patch
	libchromiumcontent-no-mas-build.patch
	libchromiumcontent-component_electron-dedupe.patch
	libchromiumcontent-dedupe-gtk3.patch
	libchromiumcontent-no-copy-libchromiumcontent.patch
	libchromiumcontent-boringssl-SSL_is_server.patch

	libchromiumcontent-chromiumcontent-gtk3.patch
	libchromiumcontent-update-gtk3.patch
	"

#top set is from arch linux, bottom set is from Orson Teodoro and Alpine Linux team, middle is mix of both

_electronpatches="
	use-system-libraries-in-node.patch
	dont-use-sysroot.patch
	dont-bootstrap-libchromiumcontent.patch
	dont-update-submodules.patch
	use-system-ffmpeg.patch
	no-whole-archive.patch

	node-http2_debug.patch
	musl-fixes-lss-only.patch
	node-header-fixes.patch
	paxmark-mksnapshot-node.patch
	node-settings.patch

	node-settings-2.patch

	breakpad-stab-include.patch
	breakpad-stab-fix.patch
	atom-3.patch
	atom-6.patch
	atom-7.patch
	atom-10.patch
	node-system-libuv.patch
	node-shared-1.patch
	node-shared-2.patch

	gtk3-menu-bar.patch
	gtk3-message-box.patch
	"

# top set from from arch linux
# middle set from from alpine linux

source="$pkgname-$pkgver.tar.gz::https://github.com/electron/$pkgname/archive/v$_pkgver.tar.gz
	$pkgname-$pkgver-$_botopkgname.zip::https://github.com/boto/$_botopkgname/archive/$_boto_gitrev.zip
	$pkgname-$pkgver-$_breakpadpkgname.zip::https://github.com/electron/$_breakpadpkgname/archive/$_breakpad_gitrev.zip
	$pkgname-$pkgver-$_crashpadpkgname.zip::https://github.com/electron/$_crashpadpkgname/archive/$_crashpad_gitrev.zip
	$pkgname-$pkgver-$_gyppkgname.zip::https://github.com/electron/$_gyppkgname/archive/$_gyppkg_gitrev.zip
	$pkgname-$pkgver-$_libchromiumcontentpkgname.zip::https://github.com/electron/$_libchromiumcontentpkgname/archive/$_libchromiumcontent_gitrev.zip
	$pkgname-$pkgver-$_nativematepkgname.zip::https://github.com/electron/$_nativematepkgname/archive/$_nativemate_gitrev.zip
	$pkgname-$pkgver-$_nodepkgname.zip::https://github.com/electron/$_nodepkgname/archive/$_node_gitrev.zip
	$pkgname-$pkgver-$_pdfviewerpkgname.zip::https://github.com/electron/$_pdfviewerpkgname/archive/$_pdfviewer_gitrev.zip
	$pkgname-$pkgver-$_requestspkgname.zip::https://github.com/requests/$_requestspkgname/archive/$_requests_gitrev.zip
	$pkgname-$pkgver-libchromiumcontent-$_libchromiumcontent_botopkgname.zip::https://github.com/piotrbulinski/$_libchromiumcontent_botopkgname/archive/$_libchromiumcontent_boto_gitrev.zip
	$pkgname-$pkgver-chromium.tar.xz::https://commondatastorage.googleapis.com/$_chromiumpkgname-browser-official/$_chromiumpkgname-$_chromiumpkgver.tar.xz
	pstables-2.8.h::http://git.savannah.gnu.org/cgit/freetype/freetype2.git/plain/src/psnames/pstables.h?h=VER-2-8
	$pkgname-$pkgver-linux_syscall_support.h::https://raw.githubusercontent.com/electron/electron/v$_pkgver/vendor/third_party/lss/linux_syscall_support.h

	$_chromiumpatches
	$_libchromiumcontentpatches
	$_electronpatches

	google-api.keys

	$pkgname-$pkgver$_suffix-$_breakpadsrcpkgname.tar.gz
	$pkgname-$pkgver$_suffix-$_depottoolspkgname.tar.gz
	$pkgname-$pkgver$_suffix-$_depottoolspkgname-libchromiumcontentdepottools.tar.gz
	$pkgname-$pkgver$_suffix-$_gritpkgname.tar.gz

	musl-fixes-breakpad-only.patch
	dont-run-gyp-files-for-bundled-deps.patch
"

snapshot() {
	abuild clean
        mkdir -p "$srcdir"

        cd "$srcdir"
        if ! [ -d $_breakpadsrcpkgname ]; then
		git clone $_breakpadsrcgiturl
		cd $_breakpadsrcpkgname
		git checkout $_breakpadsrc_gitrev
	else
		cd $_breakpadsrcpkgname
		git checkout $_breakpadsrc_gitrev
	fi
	cd ..
	tar -cvzf "$SRCDEST"/$pkgname-$pkgver$_suffix-$_breakpadsrcpkgname.tar.gz $_breakpadsrcpkgname

        cd "$srcdir"
        if ! [ -d $_depottoolspkgname ]; then
		git clone $_depottoolsgiturl
		cd $_depottoolspkgname
		git checkout $_depottools_gitrev
	else
		cd $_depottoolspkgname
		git checkout $_depottools_gitrev
	fi
	cd ..
	tar -cvzf "$SRCDEST"/$pkgname-$pkgver$_suffix-$_depottoolspkgname.tar.gz $_depottoolspkgname

        cd "$srcdir"
        if ! [ -d $_depottoolspkgname ]; then
		git clone $_depottoolsgiturl
		cd $_depottoolspkgname
		git checkout $_libchromiumcontent_depottools_gitrev
	else
		cd $_depottoolspkgname
		git checkout $_libchromiumcontent_depottools_gitrev
	fi
	cd ..
	mv $_depottoolspkgname $_depottoolspkgname-libchromiumcontentdepottools
	tar -cvzf "$SRCDEST"/$pkgname-$pkgver$_suffix-$_depottoolspkgname-libchromiumcontentdepottools.tar.gz $_depottoolspkgname-libchromiumcontentdepottools

        cd "$srcdir"
        if ! [ -d $_gritpkgname ]; then
		git clone $_gritghurl
		cd $_gritpkgname
		git checkout $_grit_gitrev
	else
		cd $_gritpkgname
		git checkout $_grit_gitrev
	fi
	cd ..
	tar -cvzf "$SRCDEST"/$pkgname-$pkgver$_suffix-$_gritpkgname.tar.gz $_gritpkgname
}

builddir="$srcdir/"$pkgname-$_pkgver

unpack() {
	default_unpack
	cd "$builddir"

	#remove all so we can do simple mv and avoid extra commands
	rm -rf "$builddir"/vendor/*

	msg "moving $_botopkgname"	
	mv "$srcdir"/$_botopkgname-$_boto_gitrev "$builddir"/vendor/$_botopkgname

	msg "moving $_breakpadpkgname"
	mv "$srcdir"/$_breakpadpkgname-$_breakpad_gitrev "$builddir"/vendor/breakpad

	msg "moving $_breakpadsrcpkgname (breakpad's src)"
	cd "$builddir"
	rm -rf "$builddir"/vendor/breakpad/src
	mv "$srcdir"/$_breakpadsrcpkgname "$builddir"/vendor/breakpad/

	msg "moving $_crashpadpkgname"	
	mv "$srcdir"/$_crashpadpkgname-$_crashpad_gitrev "$builddir"/vendor/$_crashpadpkgname

	msg "moving $_depottoolspkgname"
	cd "$builddir"
	rm -rf "$builddir"/vendor/$_depottoolspkgname/
	mv "$srcdir"/$_depottoolspkgname "$builddir"/vendor/

	msg "moving $_gyppkgname"	
	mv "$srcdir"/$_gyppkgname-$_gyppkg_gitrev "$builddir"/vendor/$_gyppkgname

	msg "moving $_libchromiumcontentpkgname"	
	mv "$srcdir"/$_libchromiumcontentpkgname-$_libchromiumcontent_gitrev "$builddir"/vendor/$_libchromiumcontentpkgname

	msg "moving $_libchromiumcontent_depottoolspkgname"
	rm -rf "$builddir"/vendor/$_libchromiumcontentpkgname/vendor/depot_tools
	mv "$srcdir"/$_depottoolspkgname-libchromiumcontentdepottools "$srcdir"/$_depottoolspkgname
	mv "$srcdir"/$_depottoolspkgname "$builddir"/vendor/$_libchromiumcontentpkgname/vendor/

	msg "moving $_libchromiumcontent_botopkgname-libchromiumcontent"	
	rm -rf "$builddir"/vendor/$_libchromiumcontentpkgname/vendor/$_libchromiumcontent_botopkgname/
	mv "$srcdir"/$_libchromiumcontent_botopkgname-$_libchromiumcontent_boto_gitrev "$builddir"/vendor/$_libchromiumcontentpkgname/vendor/$_libchromiumcontent_botopkgname

	msg "moving $_nativematepkgname"	
	mv "$srcdir"/$_nativematepkgname-$_nativemate_gitrev "$builddir"/vendor/native_mate
	msg "moving $_nativematepkgname done"	

	msg "moving $_nodepkgname"	
	mv "$srcdir"/$_nodepkgname-$_node_gitrev "$builddir"/vendor/$_nodepkgname

	msg "moving $_pdfviewerpkgname"	
	mv "$srcdir"/$_pdfviewerpkgname-$_pdfviewer_gitrev "$builddir"/vendor/pdf_viewer

	#msg "moving $_gritpkgname"
	rm -rf "$builddir"/vendor/$_pdfviewerpkgname/vendor/$_gritpkgname
	mv "$srcdir"/$_gritpkgname "$builddir"/vendor/pdf_viewer/vendor/

	msg "moving $_requestspkgname"	
	mv "$srcdir"/$_requestspkgname-$_requests_gitrev "$builddir"/vendor/$_requestspkgname

	msg "moving $_chromiumpkgname"
	mv "$srcdir"/$_chromiumpkgname-$_chromiumpkgver "$builddir"/vendor/$_libchromiumcontentpkgname/src

	msg "moving linux_syscall_support.h"
	mkdir -p "$builddir"/vendor/third_party/lss
	cp "$srcdir"/$pkgname-$pkgver-linux_syscall_support.h "$builddir"/vendor/third_party/lss/linux_syscall_support.h
}

prepare_chromium() {
	cd "$builddir"/vendor/$_libchromiumcontentpkgname/src

	local i

	for i in $_chromiumpatches; do
		case $i in
		*.patch) msg $i; patch -p0 -i "$srcdir"/$i;;
		esac
	done

	# https://groups.google.com/a/chromium.org/d/topic/chromium-packagers/9JX1N2nf4PU/discussion
	touch chrome/test/data/webui/i18n_process_css_test.html
	# Use the file at run time instead of effectively compiling it in
	sed 's|//third_party/usb_ids/usb.ids|/usr/share/hwdata/usb.ids|g' \
		-i device/usb/BUILD.gn
}

prepare_libchromiumcontentpatches() {
	cd "$builddir"/vendor/$_libchromiumcontentpkgname

	local i

	#from Arch Linux
	rm "$builddir"/vendor/$_libchromiumcontentpkgname/patches/third_party/ffmpeg/001-build_gn.patch  # Use system ffmpeg

	msg "Applying libchromiumcontent patches from libchromiumcontent project"
	local patches=$(find patches -name *.patch | sort)
	local root=$(pwd)
	for p in $patches; do
		msg "$p"

		# exclude patch for shared libs or for msvc
		# -e "v8/002-build_gn.patch"
		# -e "patches/010-build_gn.patch"
		#if [[ $(echo "$p" | grep -e 'icu/001-build_gn.patch') ]]; then
		#	msg "-- excluding $p"
		#	continue
		#fi

	        local _p=$(echo $p | sed -e "s|patches/||g")

	        d=$(dirname $_p)

	        cd $root/src/$d

		msg "Applying $(basename $p) to $root/src/$d"
	        patch -p1 -i $root/$p
	done

	cd "$builddir"/vendor/$_libchromiumcontentpkgname

	cd src
	ln -s ../chromiumcontent chromiumcontent
	cd ..
	mkdir -p src/v8/gni
	touch src/v8/gni/v8.gni
	mkdir -p src/build/toolchain/
	touch src/build/toolchain/linux:x64

	for i in $_libchromiumcontentpatches; do
		case $i in
		*.patch) msg $i; patch -p0 -i "$srcdir"/$i;;
		esac
	done

	if [[ -n "$_ccwrapper" ]] ; then
		msg "enabling $_ccwrapper"
		export CCACHE_CPP2=yes
		export CCACHE_SLOPPINESS=time_macros
		export PATH="/usr/lib/ccache/bin:$PATH"
		sed -i -r -e "s|use_allocator = \"none\"|use_allocator = \"none\"\ncc_wrapper = \"$_ccwrapper\"\n|g" chromiumcontent/args/static_library.gn
	fi

	rm vendor/depot_tools/ninja
	ln -s /usr/bin/ninja vendor/depot_tools/ninja

	sed -i -r -e "s|llvm-ar|llvm-ar|g" src/tools/clang/scripts/package.py
	sed -i -r -e "s|llvm-ar|llvm-ar|g" src/build/toolchain/gcc_toolchain.gni
	sed -i -r -e "s|-fno-delete-null-pointer-checks||g" src/build/config/linux/BUILD.gn

	cd "$builddir"/vendor/$_libchromiumcontentpkgname/src
}

regen_node_config_gypi() {
	msg "generating a config.gyp for node"
	cd "$builddir"/vendor/node

	# most of the settings come from main/nodejs
	# we need to produce a config.gyp for install.py
	./configure \
                --shared-zlib \
                --shared-openssl \
                --shared-libuv \
                --shared-http-parser \
                --shared-cares \
                --openssl-use-def-ca-store

}


prepare_nodejs() {
	cd "$builddir"/vendor/$_libchromiumcontentpkgname

	mkdir -p src/third_party/node/linux/node-linux-x64/bin

	ln -s /usr/bin/node src/third_party/node/linux/node-linux-x64/bin/node
	cd src/third_party/node
	npm install

	cd "$builddir"/vendor/node
	patch -p0 -i "$srcdir"/dont-run-gyp-files-for-bundled-deps.patch

	#recommended by main/nodejs
	rm -rf deps/http_parser deps/openssl deps/uv deps/zlib

	regen_node_config_gypi
}

prepare_electron() {
	cd "$builddir"

	for i in $_electronpatches; do
		case $i in
		*.patch) msg $i; patch -p0 -i "$srcdir"/$i;;
		esac
	done

	rm vendor/depot_tools/ninja
	ln -s /usr/bin/ninja vendor/depot_tools/ninja

	#from Arch Linux
	mkdir -p $srcdir/python2-path
	ln -sf /usr/bin/python2 "$srcdir/python2-path/python"


	cd vendor
	patch -p0 -i "$srcdir"/no-getcontext.patch
	patch -p0 -i "$srcdir"/musl-fixes-breakpad-only.patch
	patch -p0 -i "$srcdir"/breakpad-wordsize.patch

	ln -s /usr/include/linux/a.out.h breakpad/src/a.out.h

	cd "$builddir"
	#patch -p1 -R -i "$srcdir"/atom-ResourceRequestBodyImpl.patch

	msg "Injecting system libraries into brightray"
	# From Arch Linux
	# Add extra libraries for unbundling
	#removed libxml-2.0 harfbuzz-icu
	#'-lre2'
	sed -e "s/'-lexpat',/'-lexpat', '<\!@(pkg-config --libs-only-l libavcodec libavformat libavutil flac jsoncpp minizip libpng libpulse libuv libwebpdemux libxslt libdrm)', '-ljpeg', \
	      '-lsnappy', '-latomic',/" \
	      -e 's/gtk+-2\.0/gtk+-3.0/' \
	      -i brightray/brightray.gyp


}

if [ -n "$DEBUG" ]; then
        _buildtype=Debug
        _is_debug=true
else
        _buildtype=Release
        _is_debug=false
fi

prepare() {
	cd "$builddir"

	prepare_chromium
	prepare_nodejs
	prepare_libchromiumcontentpatches
	prepare_electron
}

_gn_flags() {
	echo $*
}

bootstrap_chromium() {
	_srcdir="$builddir"/vendor/$_libchromiumcontentpkgname/src
	cd $_srcdir

	msg "Running bootstrap_chromium"

	# reusable system library settings
	local use_system="flac libdrm libjpeg libpng libwebp libxslt snappy yasm zlib"
	#removed libxml libevent re2
	use_system="$use_system ffmpeg" #add arch linux set
	for _lib in ${use_system} libjpeg_turbo; do
		msg "Removing buildscripts for system provided $_lib"
		#arch linux set !icu !libevent
#	          	\! -path "*base/third_party/icu/*" \
		find -type f -path "*third_party/$_lib/*" \
			\! -path "*third_party/$_lib/chromium/*" \
			\! -path "*third_party/$_lib/google/*" \
			\! -regex '.*\.\(gn\|gni\|isolate\|py\)' \
			-delete
	done
#	          	\! -path "*base/third_party/libevent/*" \

	# pdfium uses internal headers in freetype
	# we copy from freetype sources
	# https://bugs.chromium.org/p/pdfium/issues/detail?id=733
	# should be fixed in freetype:
	# https://savannah.nongnu.org/bugs/index.php?51156
	mkdir -p "third_party/freetype/src/src/psnames/"
	cp "$srcdir"/pstables-2.8.h third_party/freetype/src/src/psnames/pstables.h

	# Work around bug in v8 in which GCC 6 optimizes away null pointer checks
	# https://bugs.chromium.org/p/v8/issues/detail?id=3782
	# https://gcc.gnu.org/bugzilla/show_bug.cgi?id=69234
	#CFLAGS="$CFLAGS -fno-delete-null-pointer-checks"

	msg "Replacing gyp files"
	msg "executing: python build/linux/unbundle/replace_gn_files.py --system-libraries ${use_system}"
	python build/linux/unbundle/replace_gn_files.py --system-libraries \
		${use_system}
	third_party/libaddressinput/chromium/tools/update-strings.py

	##############################################################
	# Please dont use these keys outside of Alpine Linux project #
	# You can create your own at:                                #
	# http://www.chromium.org/developers/how-tos/api-keys        #
	##############################################################
	eval "$(base64 -d < $srcdir/google-api.keys)"

	msg "Bootstrapping GN"
	local _c=$(_gn_flags is_clang=false \
		use_sysroot=false \
		treat_warnings_as_errors=false \
		fatal_linker_warnings=false \
		binutils_path=\"/usr/bin\" \
		use_gconf=false \
		use_gold=true \
		use_allocator=\"none\" \
		use_experimental_allocator_shim=false \
		enable_hotwording=false \
		enable_nacl=false \
		enable_nacl_nonsfi=false \
		enable_precompiled_headers=false \
		ffmpeg_branding=\"Chrome\" \
		fieldtrial_testing_like_official_build=true \
		google_api_key=\"$_google_api_key\" \
		google_default_client_id=\"$_google_default_client_id\" \
		google_default_client_secret=\"$_google_default_client_secret\" \
		is_debug=$_is_debug \
		linux_use_bundled_binutils=false \
		proprietary_codecs=true \
		symbol_level=0 \
		treat_warnings_as_errors=false \
		use_gconf=false \
		use_gnome_keyring=false \
		use_pulseaudio=false \
	)

	msg "executing: python tools/gn/bootstrap/bootstrap.py --gn-gen-args \"$_c\""
	python tools/gn/bootstrap/bootstrap.py --gn-gen-args "$_c"

	# arch linux
	# libevent not needed anymore
	#find -type f -path "*base/third_party/libevent/*" \
	#	\! -regex '.*\.\(gn\|gni\|isolate\|py\)' \
	#	-delete

	# move see (1)

#	out/Release/gn gen out/$_buildtype --args="$_c"

#	msg "Ninja turtles GO!"
	# workaround parallel build
#	ninja -C out/Release gen/ui/accessibility/ax_enums.h \
#		gen/ui/accessibility/ax_enums.cc

	# build mksnapshot and paxmark it
#	ninja -C out/$_buildtype mksnapshot
#	paxmark -m out/$_buildtype/mksnapshot
#	ninja -C out/$_buildtype v8_context_snapshot_generator
#	paxmark -m out/Release/v8_context_snapshot_generator \
#		out/Release/obj/tools/v8_context_snapshot/v8_context_snapshot_generator

	# finish rest of the build
#	ninja -C out/$_buildtype chrome chrome_sandbox chromedriver
}



build_electron() {
	msg "Building $pkgname"

	cd "$builddir"

	git init .
	git add .

	msg "Add & remove vendor/breakpad/src submodule"
	git rm -f --cached vendor/breakpad/src
	git submodule add https://chromium.googlesource.com/breakpad/breakpad/src vendor/breakpad/src

	msg "Add & remove vendor/libchromiumcontent/vendor/depot_tools submodule"
	git rm -f --cached vendor/libchromiumcontent/vendor/depot_tools
	git submodule add https://chromium.googlesource.com/chromium/tools/depot_tools.git vendor/libchromiumcontent/vendor/depot_tools

	msg "Add & remove vendor/pdf_viewer/vendor/grit submodule"
	git rm -f --cached vendor/pdf_viewer/vendor/grit
	git submodule add https://chromium.googlesource.com/chromium/src/tools/grit.git vendor/pdf_viewer/vendor/grit

	bootstrap_chromium

	local _D=$(_gn_flags \
		use_allocator=\"none\" \
		use_experimental_allocator_shim=false \
		is_debug=$_is_debug \
	)

	cd "$builddir"
	msg "bootstrapping electron"
	msg "executing: ./script/bootstrap.py --verbose --clang_dir=/usr --build_release_libcc"
	lib_buildtype=
	if [ -n "$DEBUG" ]; then
		lib_buildtype="--build_debug_libcc"
	else
		lib_buildtype="--build_release_libcc"
	fi
	./script/bootstrap.py --verbose --clang_dir=/usr $lib_buildtype --defines $d

	#msg "PaXmarking mksnapshot"
	#paxmark -m vendor/libchromiumcontent/src/out-x64/static_library/mksnapshot
	#paxmark -m vendor/libchromiumcontent/src/out-x64/static_library/obj/v8/mksnapshot

	msg "building"

	msg "executing: ./script/build.py -c $_buildtype"
	./script/build.py -c $_buildtype
	msg "done building electron"
}

build() {
	build_electron
}

package() {
	cd "$builddir"
	return 1

        mkdir -p "$pkgdir"/usr/lib/electron

	cd "out/${_buildtype:0:1}"
        mv *.pak "$pkgdir"/usr/lib/electron
        mv *.bin "$pkgdir"/usr/lib/electron
        mv *.dat "$pkgdir"/usr/lib/electron
        mv electron "$pkgdir"/usr/lib/electron
        mv libnode.so "$pkgdir"/usr/lib/electron
        mv locales "$pkgdir"/usr/lib/electron
        mv resources "$pkgdir"/usr/lib/electron

	#chmod +x "$pkgdir"/usr/lib/electron/libv8.so
	chmod +x "$pkgdir"/usr/lib/electron/libnode.so

	regen_node_config_gypi

	cd "$builddir"
	msg "Running command: HEADERS_ONLY=1 vendor/node/tools/install.py install \"$pkgdir\" \"/usr/lib/electron\""
        HEADERS_ONLY=1 vendor/node/tools/install.py install "$pkgdir" "/usr"

	mkdir -p "$pkgdir"/usr/lib/electron/node/include/node/v8
	mkdir -p "$pkgdir"/usr/lib/electron/node/include/node/uv
	#ln -s . /usr/include/node/src

	paxctl -c "$pkgdir"/usr/lib/electron/electron
	paxctl -m "$pkgdir"/usr/lib/electron/electron

	mkdir -p "$pkgdir"/usr/include/node/deps/uv/include
	mkdir -p "$pkgdir"/usr/include/node/deps/v8/include

	mkdir -p "$pkgdir"/usr/bin
	cd "$pkgdir"
	ln -s /usr/lib/electron/electron electron
}

doc() {
	cd "$builddir"

	default_doc

	mkdir -p "$subpkgdir"/usr/share/doc/$pkgname/
	cp -a README.md		"$subpkgdir"/usr/share/doc/$pkgname/
	cp -a SECURITY.md	"$subpkgdir"/usr/share/doc/$pkgname/
}
sha512sums="a1d319b7e851fbce3831230ce158c7233ffb9e6decfe1b9863bb0bfd0b05e4868ee100caea35b5b85bbc33acd69b9fd0a0881a1b943f5f95d89f79dad4be8287  electron-1.8.2.tar.gz
9db057abd8bf48bbffa0471d493795cf2781976750126777b79115d02b78da95f2d560f6c923b719c4da9d72930c305c66d473ad0a4ff84e95e37e2f76b6301e  electron-1.8.2-boto.zip
c88365ba05a33c05ef08fc784a3278711c0f4eab587c07588318c68a9a7abdbb10942f00c9bf9a6851fe968d01f08bee3c66c4e0bfc3135b2483133ad0931e80  electron-1.8.2-chromium-breakpad.zip
23865e77ced5f07a9c4bd7993097b9e00912f3a2079380b7cdb19f52a08630bc1c8345b61e202d0402754b42a41a32bd098288e62de57fbc4c227da48e424b0f  electron-1.8.2-crashpad.zip
a0d8af65d066e4d600ca6369269834b04661292f3374736492320c76a35d0dc4d55c27b1e0daaeb8566c85b546aac5a3b39e9203a8be67cdbb36673db093db81  electron-1.8.2-gyp.zip
68a851b7dd042087c6638ab0f91902ccb870d3d3fcf5560a2f4eb7047fd478e5156e6e82442ceb56b28efc50b65dfb48086140b8590103eb6be3124b88de0b52  electron-1.8.2-libchromiumcontent.zip
352a9dd06773e300a3d197dfedfc5f6a4fe49ccb0af29b958074edebe6d3d59d51fb0a8b05faec1b80972c5d5ff3b20e1b391b376318cb5dc97166fdd2036273  electron-1.8.2-native-mate.zip
b00829858804d8e70864404b36a95cced59b6df5ac02c0b9e2308587b6f1d1ee6e3cf5b6cb23d5ab4036600638c5165e9a414a92420cb3426b8740018eb97e53  electron-1.8.2-node.zip
1a1a472227e243d1e8724318a8ef78e60ee18a249ddc4e8554cb0500b77ffacc46801b94b3bfb59c3e90dfc3733ffdc76a7196b4df6ba94132f63fe2ac557806  electron-1.8.2-pdf-viewer.zip
a7571f829f9dbb45f886c2cd657ea05f11ac56d58416a36c92fb15e920cbce96b923e87a57629bc49c89002c6d9e76802dee8120be7a15bddcf2704462f81a02  electron-1.8.2-requests.zip
80b0ed5b447dcd50a9840e5d594613b33e60a9c8e5fe42dff27942c1bff2e609cecb8d2af270a0bc654a01525239029efd13efa1713a5af338717fc6c6009637  electron-1.8.2-libchromiumcontent-boto.zip
f30d54dedd43ba11321db1bcd443bb44a550ffca24ebb579727b98a15b6a3f6f598f20f0ef0889eab6820e6faacba0aa567927fd36d5ed0e61d7bd4f760e9993  electron-1.8.2-chromium.tar.xz
a3bb959c65944ae2fb765725cedcffd743a58bc0c2cd1f1999d15fe79801d00f3474b08b4ed7b48859ed921eb57093d0ad09d90f201d729ed9b8a419a591ed29  pstables-2.8.h
40f288028f813f92249bb4b093227f4b9b7da1fc71626a626feeab351fd2f563f539e92178f19ecf8c19fe93242380daa22736f7fce27bcd89cefaeff39c1e85  electron-1.8.2-linux_syscall_support.h
55921cc33d623e0751e94d4fef2ddd69afb57381da6115995b1f318e2398978b9173e80f6ffbc6e6c0c0c55a04e934e0e34a46c32e03947cc31f0f5a226e7725  chromium-widevine.patch
05fb6d9434565a7a73f5c18d470ae600bf4afbe15d0e4a7c2770bf2596a0bd2788cdfeb37e0b566fc3d26ff2d0791b70488b2c184e3286cff5a1fa25e17582cd  default-pthread-stacksize.patch
88928afcc33843e17daa082435a4b88c2106b0252a202ad19f684021c027859366a0c12970700c0d1b010211eef95d295362dc6afdea1b00199dd8d2efbdcfe7  gcc6.patch
165b143bc104068390d26eff3cdd31ef888c23a6e310533d5f487f74bc90788e174dd863da03b28afa460c52735eab15833daa3dda9ef7503f2ed564644e223f  gn_bootstrap.patch
8fbfd67a0b6bbdf08364e810bd85b4a80dda9af73fefe3aba8010d9b33022d458a785c628515bbda9c743b8a0293d57cfe18fcc5aa2313c845c6fb948c2335f9  last-commit-position.patch
853528ea8104ced45f41b42448f808afdaa748b119efecb1a8436c2ddc9a854eb4b3c2a438a627e147ee0720546a19aba9bc98cbf99ffb7637a61d18ded70ac4  musl-fixes.patch
92563cec6be54f025c6a374162df00f4e386bb55ddef36dc74e50b5165b46eec84a77617145a42391c72537100d530360b901a11a3f78f41ee8859dc874b65b5  musl-hacks.patch
9b75d6ac720d1b8ddc597f0f472bc400ff866a733f12b3a4cd3e7e18e724549c5f8e056c7e0d0462ef083bff5e677f8cef6b89b22f4740a40ad6398978269373  musl-sandbox.patch
2d0d2acb6b7d6bd10701f49b82302819eab8956cee2fd5dd3394f23c00ce369a7b398f9a76ee7f07143852b91323bb39b364dc7fda2c63313ba2a240f4a92528  no-execinfo.patch
a57858e45cfbb7e97f77b3b308502e377543d61d3d0085798ed73bc53da456828f5e010308d0de05fee4fe52071362d074f5af205f98f41d67222d997857d626  no-getcontext.patch
87b405dff00cac68e5e083e3a3e9828e8bde3f3ee3db38860c6f9114037740f53715c31faba17bd88fd4a4a41a4152878caa8383cd45f68ec9bf39b83238f3e9  no-mallinfo.patch
6e3b9c17ee7b9199ee660e467490cfbdd47e178b2755a8a539591a7ec3c6aaf9ed71f8335d4e89778f4f7648d2d00d7bfb246fb7fe2733a928f7b1b875e33979  resolver.patch
27dd7916be3324294a0a913c43c856e9c00be767a2aec4f3da2455fb84e74ebb0017d1aa586b40dd9d989ada6b60fc531522f503d57e04324726a2171bf3a85e  unset-madv_free.patch
6b0812725a0fc562527f3556dc4979fec72d1ba92f26a5e78ff2016c39bb2c155a0ff95fc22101f9c097d14b84182d6615276f4247f60ae7833ab45da8366e6d  swiftshader.patch
c26b4e664cf0052172e3c48617b981b98b0f7ca05fadfc676d370911fcede9c8f8935f45e1b55394fdd379cf71ca2161f19985c76890df21a8d0d036ef41334b  secure_getenv.patch
2e9496aa9ccd6fed2d0df4b659d55e87abb67b1be4e3cc7cb0483ccb458b9071bed9939132a2345bf15192b4dcfe5da9474d7f653ae2f4b4d46d2f3c032b3a3f  chromium-48.0.2564.116-libusb_interrupt_event_handler.patch
3f45affe3b40fdf4a01c45a7793c3ce66836836d8ab829e4e20e45cd1babecaf740caa7493b4d2e596e78b4868c8de426042fd98f6b6b51437cf4bc9bc17dfad  chromium-59.0.3071.115-gn-system.patch
e9fcc976d2ac1b2e73d310790e76dae15111e78cd8e3efa5febd702fd9492d7d68b1b57d95bca88d5e16c0627594a00ebdeaf570df52be6e9b23a4212906c141  chromium-60.0.3112.78-jpeg-nomangle.patch
9b08e895826fdd14fd6334662b8d07807beabab7368f3fcff3fcebe76baba4c7714c55042b379da6dab1ea0b1c4e5d657bf972b644089f00b418b7c2f5b6ef1b  chromium-60.0.3112.78-no-libpng-prefix.patch
87a0c6ff4906f0c4b6f6b471ec9bf0b2e2d28431122e99a68f957474cf27ec6b073ebca14660c8858817219521d74a184b8444cf2885db21d28fa4599fcaa66f  chromium-60.0.3112.78-no-zlib-mangle.patch
11141253d6ebcc2af45904f5a2560dbfa7b7b7235304574da6e7d41e5cf11a43725ae15dcec14d598e0194b9db355a6de4421c191b692bc00957198d98a99a1a  Dl_info.patch
72bdd0d9e3123ac22460740ffdef9ce1ae39dc6945e1a3ec9e46604eeb964681acd7244ba3063f4675320d3e899ebb7b611d4acff8fc86242031ec855bf6ff56  chromium-use-system-ffmpeg.patch
72891e29c679f5fa50da8ca7be84894aa140ccc939ec0c6890f7b661ad3f63174f94a07cd4eb12fc4a02aad14736957f86f1bc78f003c065395c7b8919b03f2f  paxmark-mksnapshot-chromium.patch
6dceef007cb6873cb8b6396a05c5a014f45ed69dc1cb1c1673a65f119a3b43af609ddfccc7c773d582b2cacd65b51a837c8b35a2383fb818c49a0cf5ef525f24  breakpad-wordsize.patch
e67c6e3abaad31a352c9cca28e776eb7b261c3a39c2902e1c61c298bf3f617b50f9b68d6321ce002d6986be8b2134dc242049d74c5d15ef3f2d49cfe085112e4  libchromiumcontent-static-library-only.patch
7e298378108d36caefb955e080214df1fe1091b40ea93201e4ec82f914497bb0fed05454ba1ea3721cc3c8285b136b1dbf428d7b3b580a91bdeb2f3625edfe63  libchromiumcontent-use-system-tools.patch
9bb6a6449ce3bd2992fd197df15c2a2f88c2fad1cae7759a3ed9152c9f9dd8303df54e6d5babac7ffe11fb3a701722d65a61a3ca5920b71309476e8583b990b6  libchromiumcontent-no-depot_tools.patch
8e19b45ae4f316edf29c1d91f34d30843548aea908ba0b8fd1ddf456382c07212b6e0d6208cd862663fe99836a7e3be2240b01ad11adc22379c10fc6dcc86bc4  libchromiumcontent-chdir.patch
00a697dc2b82065872373b6ff278e178abe8de2932f4604f627506d43eb2b1a5f76c1968f9060aa92412ab85f5145782bf2ef9f6149a1f2815acb4c5ec03fb4c  libchromiumcontent-settings.patch
dd7d9e3f30d8ee0a2ec2ec87018c930094308307f7754f6897aeb1683bc6863f99ecc2f11e28e3fc012a589f6195c1d57cc4c4253ce906b4d0bf0889da447c54  libchromiumcontent-is_electron_build-1.patch
767d7826896a78aabb08b856965eab03b5a9156b65f4ea0a01c6ce15463d13bd4bf3e130962d288b890a8f1e20f4b3b6a3c23171b766942c5f9d19de60b46ed9  libchromiumcontent-musl-fixes-2.patch
e7a9bd618f954e269c7553f1370a2b70f9c521d55b22085935f1bf6b51f9adf03737760ac4efcf06d92d73ddfc99bd6028dc8dd2ddad8762866786d850f87850  libchromiumcontent-is_electron_build-3.patch
e41304868409ab53168b52b76d537c7786193894e7966e41eeeac9bed9559369ad761c1bb0e47793da3c1f444b40e53fefac179408bec878678243aa3c0d72b1  libchromiumcontent-is_electron_build-4.patch
1818b885ed357e03a9ca60a91f8a795e1b75e032d67ed8790aa5029dea773fd71ef67d7054124353f9de149afa594721bebbb8309ec24c580585f9da1fd0f23a  libchromiumcontent-BUILDCONFIG.patch
94f73264fcd47c8e6c4061300db7880bb94a5ce198e56529952b8a0bc94ab4ce5394e03150636fd0450e578759a89230b5ea5b588f800b57a6cf9e5a8f4efcd7  libchromiumcontent-static-v8.patch
f74d0071b48966a1362d7bbc46c88b236ffdbf15f8bbe802796a9e2a7bf801ea1b2b003bcfcfe6d6737ca875130fe9e061f862a7dd56bcc3e6b453de739eba79  libchromiumcontent-TCP_SOCKET-dupe.patch
24db56db2b1790b5df16eaece3186f59bb2da7f366cf84d326a75ce468c5d9d30ba885928d8863aeb4f21808af480106ee157d7da783782b3f4279686d4201db  libchromiumcontent-no-mas-build.patch
86ebf2e1bd7861f3952c0145be9f88ec90393b1421536db21d8dbb8c99d14a3718002f682ee4c4a7dc4957696e517b607a9fee595f3393b84b30ab7ebf3e77b6  libchromiumcontent-component_electron-dedupe.patch
0ebc1ac6b0643b62906bb2c162c1841358e947c7251e215822825c904235e76db3b084999c1586c71edc7c03c621d7face7f3d16a1e993ac7c36c93311be5f3a  libchromiumcontent-dedupe-gtk3.patch
5c58a314c84099c2fea282787af51bfc0f19bcfe57949806658282d71594a02f706db721ff0dda20276622cc220f7c270bf6bd33de1d68eec261b57a6c252e58  libchromiumcontent-no-copy-libchromiumcontent.patch
3630f479b27ea4030251c7593701da5e0a6730d29910505bbfd78afab6397f23b1c900cd20abeb36f1f49039349953b34ac82abe702182ca96953fc1d7f39917  libchromiumcontent-boringssl-SSL_is_server.patch
a6e72a95e41894e7881af13ff0b878cc53d54449c64a3090676a645e5d07fc7bac3f3095eefb9e03edd07e81db58e18de06b343713add78fe89c418153c51506  libchromiumcontent-chromiumcontent-gtk3.patch
868fc965d800cc225bcc2313d873591d1e7417331216b4c5560d4e573141a38695c076abba32e96c5875438f98bcf2f5ce546e75e6f2d212a4b78f2ba0ccbca8  libchromiumcontent-update-gtk3.patch
bacc86279c36478e757df300bbab004e4269f9488740e45544c2823bbbdac5db686cb60d7cb86bf787e7f29cb84d910c7f6fbc4a5e95332ff66e9bf70619ed39  use-system-libraries-in-node.patch
d91d433f2fe967aeb93aa6f7c827f87863a09f4c19a3c8ffc4d32135b278fa1a703d5ccd3a4353d2e70c34c2e46135d894bb19ad2b29305e9d16804208353272  dont-use-sysroot.patch
f7f71d99d1cea980f43ea120f9cc1bff99f0f991c02468f573bcd254ef61cb0f0d11e3c514ddbc89c80162be3f8751c9437321326f6fb4511a319c3a8e429b0c  dont-bootstrap-libchromiumcontent.patch
6764862ae0fcf8f01ae7c61779451d8c93a6c7ae673f5a9754fbc159ffad4722165eb194625de31cd8fa65a1030d38e807f1e42820f64c773c995e10809f11b3  dont-update-submodules.patch
021ff3e0e2fea53ffd73757ddb9eee1230f4e9eb1847f1d2479d53554759a10b37913fbba10212c5da614ab1b42d8e780278e9775b2d9c2001cf271d2528655f  use-system-ffmpeg.patch
2c8ed72c4328eb2738aab3150d3848b993e612db2835f97f542bdfd5b20939dcbdaad0c4986a7676fe4a7fc3f3077a86f0ff2bd9d2191b2d65b71a06709e8796  no-whole-archive.patch
07ce07742a75ec7956a53164d6d6109bb75b04e99ef4600888d732e703cacefd90872fbf75c493a10c5106e3228856a0dc7050f1b8d26e5c8922fc7b0f963bc4  node-http2_debug.patch
122aab394b0560547cc28383c8ee4bd20a28d126991d0ff8409b507397694b2f362cffb6190349477319b8749abd30161520bbc5e26a943151d38b042c7975f3  musl-fixes-lss-only.patch
d27ad40f89d675ca8df69f085356a4a608568357d32acf285a34c94e2c3bcd1aa31d02363dac488613b5fd37cf8a785e71af17832c89f05c8c0718b4205e7a8c  node-header-fixes.patch
ea23487b4e7cedc556c6925b4f163eebed76da0d0fb6247347968954d3c539945663cf3a9f1ad0d3db693c275eb64c3ccec101d38e14353443b89d99e6edd968  paxmark-mksnapshot-node.patch
2d1741ac1e6d4dbeb15a3bee426c031dada86cec1e814a65590f0c92fad8b579e12abf6ff4450bd03b5840faacbe2ef323fa8e1a273f5e9d87bef4e1b15689bd  node-settings.patch
81352c97ec12d55914aa883d8d113c1639f3527b7ec0136b2282df8b9b8b22ce392fb77ef24fe8f2d166eba075f6665fd97b2260266f516fe2fd76a2f7578af6  node-settings-2.patch
e501497569044a38cec42752314072ab9686786597c5f1caf5cb6fe7598d24394c3578fab6fdda440532890267658d77a8ff034eb5ebc876c2a4e0f3eabba9ab  breakpad-stab-include.patch
960315e6f2ba3b5bcef883f431bb374fdc1ddcbdb1f79013b077b8d09ed3a2d0232d91f9f69f4a7c311f1afee775cff49fc29e5d2c2454ce153961ed3166cbd6  breakpad-stab-fix.patch
926e1595ffbeb349b9c5c2c0360d47cba721b61dbf87c800c89fb9b98c01059491cc3126fd018b758e7bee03539eeeba81701646f703b354dcad6c6fdcd437d1  atom-3.patch
68a0c8c7ec9564727beb3e7ffea56c57028f28b5ef085f488386bd93cf347b8b139ea1a91a82035cee1ba911f9f73ff21bc788ae215974a20274498d322a4b0e  atom-6.patch
64c8f84bd70d7ce5a00a0ace841fba0d6d0c8d989ec2dc9d07d05fe15b058e14048913e4029bbc296425830857c3a2cbab39541d165f4d60103ec9afe1ddae0b  atom-7.patch
05e723dd359e96baad25835f71d4d75650a52ecd296f1cf7393a56eaf075b013a176048ba51b7f89de0b030e9d3e9dc2233068cebef74014a48bba8a3e2e91b4  atom-10.patch
f7f350fd83af4e3efc4cdd2255c47e3883c9a5e63fb7f0b4f41a4d1c0c455a7fb03df81097af4d26210c999ef6bd05a550ecc45608dd96cf1edd53ece3b69c7a  node-system-libuv.patch
545b246e43fbaef69d1d07e9c1fac57130a08a8da01b634c9f77c79ee225fcb57723a38fb355d656fe43c509ff41a86a3dba899b10c52d2263be12c9ebbc0b2c  node-shared-1.patch
23930728a7af97348f7f1de0bdb53e7c7507538b51c92fd1524a8a06d7d7c47ec04927d8aecd81eb755b7beca763a1594a330e73fc39b615f087687c42d668ec  node-shared-2.patch
21c16184cf681b4073bd09381a8168e4ce4e27f35946bf265385e7f68398c81fb98eba195369e2e42781f3c705c8aeb7e09fafbfe592d3e86441067823783040  gtk3-menu-bar.patch
14fa2ce8bb34258ca3df1af7f232f59017215bc5bd2e41255d5fb8f96b630c363c1aaf2db0b0e0ea8dcc10b7b5f91b4450dc3f35145e2cce401a83be2ab54ffc  gtk3-message-box.patch
2d8237a940ea691bd10b08315429677a587f7ef9692a0cca53bfd066eae82998a6c71f402a8669e9de39f94d7f3280745d1628ea6eac5d76ca7116844d4e0dac  google-api.keys
75a00142efcbd26e4c5701af1849f65140e9275e61014ac23124f3f61ecd607c0b49a988dff9a4d965d06f4b34ae02a1fa548ce530be4824e86c873af7220663  electron-1.8.2-src.tar.gz
be363852c93a7ccfa50ddbc400eaa0d266222e5f337d2b73708883e234426e00cb222b0d2a87365878e6b67e2ec2e797e05bfe85ad48da97d1ebe2a3339ebdcd  electron-1.8.2-depot_tools.tar.gz
65baa06225aa475c47dc1b5049cac98246f64f47e911c1de3f6cc836df1b4245d0b520167dd69c6e38172597dabae9933eac0dae36511b7a57696457e1d3c51f  electron-1.8.2-depot_tools-libchromiumcontentdepottools.tar.gz
2bbcbbbc4cd096b348ff4f85ade36b292d6490f3de4a912e5c54c9b7bc4fff1ac6a069790a91de9dba2ee2718ab70716e32e3ea9786b9eadac8df03d91009570  electron-1.8.2-grit.tar.gz
2ba3cf1be1fd055380d7472c77fc37b7707397b265dd757d8fa19c5728e9e3c215c5f039cf7b24d44419f9bd82b6a29ccc343ade151f246f5889de14ae18ed8d  musl-fixes-breakpad-only.patch
5839800f8fa2864a78f0e1c5035fd1b321da9779edb505bdb86f94c6e372505ed665f5f85d1bc7b16437dbef2cd4e3a5e1dbea1ac90398cd9235f8d24b30d69a  dont-run-gyp-files-for-bundled-deps.patch"
