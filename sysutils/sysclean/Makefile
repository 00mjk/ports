COMMENT =	list obsolete files between OpenBSD upgrades

V =		3.2
DISTNAME =	sysclean-${V}

CATEGORIES =	sysutils
HOMEPAGE =	https://github.com/semarie/sysclean/

MAINTAINER =	Sebastien Marie <semarie@online.fr>

MASTER_SITES =	https://github.com/semarie/sysclean/releases/download/${V}/

# ISC
PERMIT_PACKAGE =	Yes

MAKE_ENV =		BINDIR=${LOCALBASE}/sbin \
			MANDIR=${LOCALBASE}/man/man

NO_BUILD =		Yes
PKG_ARCH =		*

TEST_TARGET =		regress

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/sysclean
	${INSTALL_DATA} ${WRKSRC}/sysclean.ignore ${PREFIX}/share/examples/sysclean

.include <bsd.port.mk>
