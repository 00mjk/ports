COMMENT=	virus scanner
DISTNAME=	clamav-0.105.0

CATEGORIES=	security

SHARED_LIBS +=	clamav               25.1
SHARED_LIBS +=	clamunrar            5.0
SHARED_LIBS +=	clamunrar_iface      5.0
SHARED_LIBS +=  freshclam            1.0

HOMEPAGE=	https://www.clamav.net/

MAINTAINER=	Stuart Henderson <stu.ports@spacehopper.org>

# GPLv2/LGPL, with OpenSSL exemption
PERMIT_PACKAGE=	Yes

WANTLIB += ${COMPILER_LIBCXX}
WANTLIB += bz2 c crypto curl curses execinfo iconv json-c m milter
WANTLIB += mspack pcre2-8 ssl util xml2 z

COMPILER=		base-clang ports-gcc

BUILD_DEPENDS=		lang/rust
LIB_DEPENDS=		archivers/bzip2 \
			archivers/libmspack \
			devel/json-c \
			devel/pcre2 \
			mail/sendmail,-libmilter \
			net/curl \
			textproc/libxml
TEST_DEPENDS=		security/clamav

MASTER_SITES=		https://www.clamav.net/downloads/production/

MODULES=		devel/cmake
CONFIGURE_ARGS+=	-DCLAMAV_USER=_clamav \
			-DCLAMAV_GROUP=_clamav \
			-DENABLE_EXTERNAL_MSPACK=ON \
			-DDATABASE_DIRECTORY=/var/db/clamav \
			-DAPP_CONFIG_DIRECTORY=${SYSCONFDIR} \
			-DCMAKE_INSTALL_DOCDIR=${PREFIX}/share/doc/clamav

# the LLVM bytecode runtime uses W+X-maps (and often doesn't support
# current LLVM versions anyway)
CONFIGURE_ARGS+=	-DBYTECODE_RUNTIME=interpreter

# for tests
MODULES+=		lang/python
MODPY_RUNDEP=		No
BUILD_DEPENDS+=		devel/check
CONFIGURE_ARGS+=	-DENABLE_TESTS=on

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/clamav
	mv ${WRKINST}/etc/*sample ${PREFIX}/share/examples/clamav

.include <bsd.port.mk>
