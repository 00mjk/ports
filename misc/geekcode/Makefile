COMMENT=	geek code generator

DISTNAME=	geekcode-1.7.3
CATEGORIES=	misc
REVISION=	2

MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=geekcode/}

# GPLv2+
PERMIT_PACKAGE=	Yes

WANTLIB=		c

MAKE_FLAGS=	CC="${CC}" CFLAGS="${CFLAGS}"

NO_TEST=	Yes

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/geekcode ${PREFIX}/bin
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/geekcode
	${INSTALL_DATA} ${WRKSRC}/geekcode.txt ${PREFIX}/share/doc/geekcode

.include <bsd.port.mk> 
