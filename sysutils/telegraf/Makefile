COMMENT =	plugin-driven server agent for collecting metrics

BROKEN-arm =	build fails, no error message

MODGO_VERSION=	v1.22.4
MODGO_MODNAME=	github.com/influxdata/telegraf
GH_ACCOUNT =	influxdata
GH_PROJECT =	telegraf
GH_TAGNAME =	${MODGO_VERSION}
HOMEPAGE =	https://www.influxdata.com/time-series-platform/telegraf/

MAINTAINER =	Lucas Raab <tuftedocelot@fastmail.fm>

CATEGORIES =		sysutils

# MIT
PERMIT_PACKAGE =	Yes

MODULES =	lang/go

WANTLIB +=	c pthread
WRKDIST=	${WRKSRC}

.include "modules.inc"

do-install:
	${MODGO_INSTALL_TARGET}
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/telegraf/
	${INSTALL_DATA} ${WRKSRC}/etc/telegraf.conf \
		${PREFIX}/share/examples/telegraf/

.include <bsd.port.mk>
