COMMENT=	papirus icon theme

GH_ACCOUNT=	PapirusDevelopmentTeam
GH_PROJECT=	papirus-icon-theme
GH_TAGNAME=	20220302

CATEGORIES=	x11

MAINTAINER=	David Demelier <markand@malikania.fr>

# GPLv3
PERMIT_PACKAGE=	Yes
PKG_ARCH=	*

NO_BUILD=	yes
RUN_DEPENDS=	x11/gtk+3,-guic

USE_GMAKE=	yes

FAKE_FLAGS=	PREFIX="${TRUEPREFIX}"

.include <bsd.port.mk>
