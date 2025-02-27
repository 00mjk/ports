COMMENT =	pythonic interface to the HDF5 binary data format

MODPY_EGG_VERSION =	3.6.0
DISTNAME =		h5py-${MODPY_EGG_VERSION}
PKGNAME =		py-${DISTNAME}
CATEGORIES =		math

HOMEPAGE =		https://www.h5py.org/
MAINTAINER =		Martin Reindl <martin@catai.org>

# BSD
PERMIT_PACKAGE =	Yes

COMPILER =		base-clang ports-gcc
COMPILER_LANGS =	c

MODULES =		lang/python
MODPY_SETUPTOOLS =	Yes
MODPY_PI =		Yes
MODPY_PYTEST =		Yes

FLAVORS =	python3
FLAVOR =	python3

WANTLIB =	pthread hdf5 hdf5_hl

MAKE_ENV =	HDF5_DIR=${PREFIX}

BUILD_DEPENDS = lang/cython${MODPY_FLAVOR} \
                math/py-numpy${MODPY_FLAVOR} \
		devel/py-pkgconfig${MODPY_FLAVOR}

LIB_DEPENDS =	math/hdf5

TEST_DEPENDS =	devel/py-coveralls${MODPY_FLAVOR} \
		devel/py-test-cov${MODPY_FLAVOR}

do-test: fake
	cd ${WRKDIR} && ${MAKE_ENV} PYTHONPATH=${WRKINST}${MODPY_SITEPKG} \
		${MODPY_BIN} -c 'import h5py; h5py.run_tests()'

.include <bsd.port.mk>
