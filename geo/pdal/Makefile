COMMENT =	translator library for point cloud formats

DISTNAME =	PDAL-2.4.1-src
PKGNAME =	${DISTNAME:L:C/-src//}

SHARED_LIBS =	pdal_base 4.0 # 13.0
SHARED_LIBS +=  pdal_util 1.0 # 13.0

CATEGORIES =	geo devel textproc

HOMEPAGE =	https://pdal.io/
MASTER_SITES =	https://github.com/PDAL/PDAL/releases/download/2.4.1/

MAINTAINER =	Landry Breuil <landry@openbsd.org>

# BSD
PERMIT_PACKAGE =	Yes

MODULES =	devel/cmake

# uses std=c++0x
COMPILER =	base-clang ports-gcc

LIB_DEPENDS =	${MODPY_LIB_DEPENDS} \
		geo/gdal \
		databases/postgresql \
		net/curl

WANTLIB +=	c crypto curl gdal geotiff m pq pthread
WANTLIB +=	ssl xml2 z zstd
WANTLIB += ${COMPILER_LIBCXX}

CONFIGURE_ARGS =	\
	-DPDAL_PLUGIN_INSTALL_PATH=${LOCALBASE}/share/pdal/plugins \
	-DWITH_TESTS=FALSE

.include <bsd.port.mk>
