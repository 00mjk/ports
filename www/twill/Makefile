COMMENT=		simple scripting language for web browsing

MODPY_VERSION=		${MODPY_DEFAULT_VERSION_2}

DISTNAME=		twill-0.9
REVISION=		8
CATEGORIES=		www

HOMEPAGE=		https://twill-tools.github.io/twill/
PORTROACH=		site:https://github.com/twill-tools/twill/releases/
MASTER_SITES=		http://darcs.idyll.org/~t/projects/

# MIT
# Includes patched versions of:
# 	py-clientform (BSD-like or ZPL)
# 	py-mechanize (BSD-like or ZPL)
# 	py-parsing (BSD-like)
# 	py-beautifulsoup (PSF)
PERMIT_PACKAGE=	Yes

MODULES=		lang/python
MODPY_SETUPTOOLS=	Yes
NO_TEST=		Yes

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/twill
	cd ${WRKSRC}/doc && \
		find . -type f -maxdepth 1 -name "*.txt" \
		\! \( -name "ANNOUNCE*" -o -name "ChangeLog" \) \
		-exec ${INSTALL_DATA} {} ${PREFIX}/share/doc/twill/{} \;
	rm -fr ${WRKSRC}/twill.egg-info

.include <bsd.port.mk>
