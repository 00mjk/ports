COMMENT=	PHP support for chroot(2)

DISTNAME=	pecl-chroot-1.0
REVISION=	18

MASTER_SITES=	${MASTER_SITE_BACKUP}

# PHP
PERMIT_PACKAGE=	Yes

WANTLIB=	c

# not really PECL but close enough
MODULES=	lang/php/pecl
FLAVORS=	php74
FLAVOR=		php74
CONFIGURE_STYLE= gnu

.include <bsd.port.mk>
