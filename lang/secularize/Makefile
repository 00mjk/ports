COMMENT =	HolyC transcompiler

MODPY_EGG_VERSION =	0.0.1.post7
DISTNAME =	secularize-${MODPY_EGG_VERSION}
PKGNAME =	${DISTNAME:S/post//}
EPOCH =		0
REVISION =	2

CATEGORIES =	lang

HOMEPAGE =	https://www.github.com/jamesalbert/HolyC-for-Linux

MAINTAINER =	Mike Larkin <mlarkin@openbsd.org>

# MIT
PERMIT_PACKAGE =	Yes

MODULES =		lang/python

MODPY_PI =		Yes

MODPY_SETUPTOOLS =	Yes

TEST_DEPENDS =		devel/py-docopt${MODPY_FLAVOR}

pre-configure:
	${SUBST_CMD} ${WRKSRC}/secularize/utils.py

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/secularize/config/
	${INSTALL_DATA} ${WRKSRC}/config/* ${PREFIX}/share/secularize/config/

.include <bsd.port.mk>
