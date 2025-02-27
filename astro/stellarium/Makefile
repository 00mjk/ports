USE_WXNEEDED=		Yes

COMMENT=		free open source planetarium

GH_TAGNAME=		v0.22.1
GH_ACCOUNT=		Stellarium
GH_PROJECT=		stellarium

CATEGORIES=		astro x11

HOMEPAGE=		http://www.stellarium.org/

MAINTAINER=		Antoine Jacoutot <ajacoutot@openbsd.org>

# GPLv2
PERMIT_PACKAGE=		Yes

WANTLIB += ${COMPILER_LIBCXX} Qt5Charts Qt5Concurrent Qt5Core
WANTLIB += Qt5Gui Qt5Multimedia Qt5MultimediaWidgets Qt5Network
WANTLIB += Qt5Positioning Qt5PrintSupport Qt5Qml Qt5QmlModels
WANTLIB += Qt5Quick Qt5Script Qt5SerialPort Qt5WebChannel Qt5WebEngine
WANTLIB += Qt5WebEngineCore Qt5WebEngineWidgets Qt5Widgets c m
WANTLIB += z

MODULES=		devel/cmake \
			lang/python \
			x11/qt5

MODPY_RUNDEP=		No

LIB_DEPENDS=		x11/qt5/qtcharts \
			x11/qt5/qtlocation \
			x11/qt5/qtmultimedia \
			x11/qt5/qtscript \
			x11/qt5/qtserialport \
			x11/qt5/qtwebengine

# used to download more stars definitions
RUN_DEPENDS=		net/curl \
			devel/desktop-file-utils \
			misc/shared-mime-info \
			x11/gtk+3,-guic

CONFIGURE_ENV=		HOME=${WRKDIR}

CONFIGURE_ARGS=		-DCMAKE_DISABLE_FIND_PACKAGE_Doxygen=ON \
			-DENABLE_LIBGPS=0 \
			-DSTELLARIUM_RELEASE_BUILD=1

CFLAGS +=	-I${LOCALBASE}/include -I${X11BASE}/include
CXXFLAGS +=	-I${LOCALBASE}/include -I${X11BASE}/include

PORTHOME=		${WRKDIR}

NO_TEST=		Yes

pre-configure:
	sed -i 's,/usr/local,${LOCALBASE},g' ${WRKSRC}/CMakeLists.txt

.include <bsd.port.mk>
