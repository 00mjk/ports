COMMENT =		CLAT configuration daemon for OpenBSD
V =			1.3
DISTNAME =		gelatod-${V}
CATEGORIES =		net
REVISION =		0

# BSD 2-clause
PERMIT_PACKAGE =	Yes

MASTER_SITES =		https://github.com/fobser/gelatod/releases/download/v${V}/

MAINTAINER =		Klemens Nanni <kn@openbsd.org>

DEBUG_PACKAGES =	${BUILD_PACKAGES}

# uses pledge()
WANTLIB =		c event util

NO_TEST =		Yes

.include <bsd.port.mk>
