# XXX before upgrade to a newer release, make sure these are fixed:
# https://sourceforge.net/p/netatalk/bugs/670/
# https://sourceforge.net/p/netatalk/bugs/669/
# https://github.com/Netatalk/Netatalk/issues/175
# configure: WARNING: unrecognized options: --with-libevent-header, --with-libevent-lib
# Initial update to 3.1.13:
#     https://github.com/openbsd/ports/commit/76cd8557b7ca4dfd2d0fd5470bfdd63636cb962d

COMMENT=		AFP file and print services for IP networks

V=			3.1.12
DISTNAME=		netatalk-${V}
EXTRACT_SUFX=		.tar.bz2
PKGSPEC=		netatalk->=3,<4
EPOCH=			0

REVISION=		0

SHARED_LIBS +=  atalk                16.0     # 18.0

CATEGORIES=		net

HOMEPAGE=		http://netatalk.sourceforge.net/

MAINTAINER=		Antoine Jacoutot <ajacoutot@openbsd.org>

# GPLv2+
PERMIT_PACKAGE=	Yes

WANTLIB += avahi-client avahi-common c crypto db dbus-1 dbus-glib-1
WANTLIB += event_core event_extra ffi gcrypt gio-2.0 glib-2.0
WANTLIB += gobject-2.0 gpg-error gthread-2.0 iconv intl pcre pthread
WANTLIB += tdb execinfo

MASTER_SITES=		${MASTER_SITE_SOURCEFORGE:=netatalk/}

MODULES=		lang/python

MODPY_ADJ_FILES=	contrib/shell_utils/afpstats
MODPY_BUILDDEP=		No

LIB_DEPENDS=		databases/db/v4 \
			databases/tdb \
			devel/libevent2 \
			net/avahi,-libs \
			security/libgcrypt \
			x11/dbus-glib

RUN_DEPENDS=		net/avahi

# afpstats(1)
RUN_DEPENDS +=		x11/dbus-python${MODPY_FLAVOR}

LIBTOOL_FLAGS=		--tag=disable-static

CONFIGURE_STYLE=	gnu

CONFIGURE_ENV=		CPPFLAGS="-I${LOCALBASE}/include" \
			LDFLAGS="-L${LOCALBASE}/lib" \
			ac_cv_path_MYSQL_CONFIG=

CONFIGURE_ARGS=		--with-pkgconfdir=${SYSCONFDIR}/netatalk \
			--with-ssl-dir=/usr \
			--with-tdb=${LOCALBASE} \
			--with-libevent-header=${LOCALBASE}/include \
			--with-libevent-lib=${LOCALBASE}/lib \
			--without-ldap \
			--without-pam

# XXX does not build
CONFIGURE_ARGS +=	--disable-quota

# don't pickup z11/gnome/tracker3
CONFIGURE_ARGS +=	--with-tracker-pkgconfig-version=0

DEBUG_PACKAGES=		${BUILD_PACKAGES}

FAKE_FLAGS=		sysconfdir=${PREFIX}/share/examples/netatalk \
			pkgconfdir=${PREFIX}/share/examples/netatalk/netatalk \
			localstatedir=${PREFIX}/share/examples/netatalk/var

post-install:
	rm ${PREFIX}/lib/netatalk/*.la

.include <bsd.port.mk>
