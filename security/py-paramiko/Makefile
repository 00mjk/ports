COMMENT =	low-level pure Python implementation of SSHv2

MODPY_EGG_VERSION =	2.11.0
DISTNAME =		paramiko-${MODPY_EGG_VERSION}
PKGNAME =		py-${DISTNAME}
CATEGORIES =		security

HOMEPAGE =		https://www.paramiko.org/

# LGPL
PERMIT_PACKAGE =	Yes

MODPY_PI =		Yes

MODULES =		lang/python

MODPY_SETUPTOOLS =	Yes
MODPY_PYTEST =		Yes

RUN_DEPENDS =		devel/py-asn1${MODPY_FLAVOR} \
			security/py-bcrypt${MODPY_FLAVOR} \
			security/py-cryptography${MODPY_FLAVOR} \
			security/py-PyNaCl${MODPY_FLAVOR}
TEST_DEPENDS =		devel/py-mock${MODPY_FLAVOR} \
			devel/py-invoke${MODPY_FLAVOR}

FLAVORS =		python3
FLAVOR =		python3

MODPY_ADJ_FILES =	demos/*.py

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/${MODPY_PY_PREFIX}paramiko
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/${MODPY_PY_PREFIX}paramiko
	cp -R ${WRKSRC}/docs/* ${PREFIX}/share/doc/${MODPY_PY_PREFIX}paramiko
	chown -R ${SHAREOWN}:${SHAREGRP} ${PREFIX}/share/doc/${MODPY_PY_PREFIX}paramiko
	${INSTALL_DATA} ${WRKSRC}/demos/* \
	  ${PREFIX}/share/examples/${MODPY_PY_PREFIX}paramiko

.include <bsd.port.mk>
