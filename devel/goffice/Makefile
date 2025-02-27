COMMENT=	document centric objects and utilities

GNOME_PROJECT=	goffice
GNOME_VERSION=	0.10.52
REVISION=	0

# NOTE: when GNOME_VERSION changes, increment GOFFICE_VERSION and
# GOFFICE_API_VERSION accordingly and bump:
# math/gnumeric
GOFFICE_API_VERSION=	${GNOME_VERSION:R}
SUBST_VARS=		GNOME_VERSION GOFFICE_API_VERSION

SHARED_LIBS +=  goffice-0.10         0.3      # 10.52

CATEGORIES=	devel

MAINTAINER=	Antoine Jacoutot <ajacoutot@openbsd.org>

# GPLv2+
PERMIT_PACKAGE=		Yes

WANTLIB += ${COMPILER_LIBCXX} ICE SM X11 Xau Xcomposite Xcursor
WANTLIB += Xdamage Xdmcp Xext Xfixes Xi Xinerama Xrandr Xrender
WANTLIB += atk-1.0 atk-bridge-2.0 avahi-common bz2 cairo cairo-gobject
WANTLIB += dbus-1 epoxy execinfo expat ffi fontconfig freetype
WANTLIB += fribidi gdk-3 gdk_pixbuf-2.0 gio-2.0 glib-2.0 gmodule-2.0
WANTLIB += gobject-2.0 graphite2 gs gsf-1 gtk-3 harfbuzz iconv
WANTLIB += intl jpeg lzma m pango-1.0 pangocairo-1.0 pangoft2-1.0
WANTLIB += pcre pixman-1 png rsvg-2 spectre xcb xcb-render xcb-shm
WANTLIB += xml2 xslt z zstd

MODULES=		x11/gnome

LIB_DEPENDS=		devel/libgsf \
			print/libspectre \
			textproc/libxslt \
			x11/gnome/librsvg \
			x11/gtk+3

MODGNOME_TOOLS=		gobject-introspection
MODGNOME_LDFLAGS=	-L${X11BASE}/lib

CONFIGURE_STYLE=	gnu

DEBUG_PACKAGES=		${BUILD_PACKAGES}

post-install:
	rm ${PREFIX}/lib/goffice/${GNOME_VERSION}/plugins/*/*.{a,la}

.include <bsd.port.mk>
