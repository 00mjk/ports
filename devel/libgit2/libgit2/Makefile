COMMENT=		the Git library, take 2

GH_ACCOUNT =		libgit2
GH_PROJECT =		libgit2
GH_TAGNAME =		v1.4.3

SHARED_LIBS +=  git2                      14.0 # 0.28

MODULES=		devel/cmake \
			lang/python

MODPY_RUNDEP=		No

COMPILER=		base-clang ports-gcc base-gcc
COMPILER_LANGS=		c
# for atomic builtins
MODGCC4_ARCHS=		hppa

DEBUG_PACKAGES =	${BUILD_PACKAGES}

LIB_DEPENDS=		devel/http-parser \
			devel/pcre \
			security/libssh2

WANTLIB += crypto http_parser pcre pcreposix pthread ssh2 ssl
WANTLIB += z

CONFIGURE_ARGS=		-DUSE_SSH=ON \
			-DUSE_HTTP_PARSER=system

CFLAGS +=	-I${LOCALBASE}/include
MODCMAKE_LDFLAGS =	-L${LOCALBASE}/lib

.include <bsd.port.mk>
