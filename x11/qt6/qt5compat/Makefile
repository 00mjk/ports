QT6NAME =	Qt5Compat
COMMENT =	Qt6 module contains unsupported Qt 5 APIs

PKGSPEC =	qt6-qt5compat-${QT6_PKGSPEC}

SHARED_LIBS +=  Qt6Core5Compat      0.1 # 6.3

WANTLIB += ${COMPILER_LIBCXX} GL Qt6Core Qt6Gui Qt6Network Qt6OpenGL
WANTLIB += Qt6Qml Qt6QmlModels Qt6Quick c icudata icui18n icuuc
WANTLIB += m xkbcommon

LIB_DEPENDS =	x11/qt6/qtdeclarative \
		x11/xkbcommon

.include <bsd.port.mk>
