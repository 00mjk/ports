COMMENT =	simple gemini server
V =		1.8.3
DISTNAME =	gmid-${V}
REVISION =	1

CATEGORIES =	net

HOMEPAGE =	https://gmid.omarpolo.com/

MAINTAINER =	Omar Polo <op@openbsd.org>

# ISC
PERMIT_PACKAGE = Yes

# uses pledge()
# uses unveil()
WANTLIB += c crypto event ssl tls util

MASTER_SITES = https://github.com/omar-polo/gmid/releases/download/$V/

CONFIGURE_STYLE = simple

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/gmid
	${INSTALL_DATA} ${FILESDIR}/gmid.conf ${PREFIX}/share/examples/gmid

.include <bsd.port.mk>
