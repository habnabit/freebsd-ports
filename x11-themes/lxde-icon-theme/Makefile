# Created by: Kris Moore <kmoore@FreeBSD.org>
# $FreeBSD$

PORTNAME=	lxde-icon-theme
PORTVERSION=	0.5.1
CATEGORIES=	x11-themes
MASTER_SITES=	SF/lxde/LXDE%20Icon%20Theme/${DISTNAME}/

MAINTAINER=	horia@racoviceanu.com
COMMENT=	LXDE Icon Theme

LICENSE=	GPLv3
LICENSE_FILE=	${WRKSRC}/COPYING

USES=		gmake iconv tar:xz
GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--prefix=${PREFIX}
NO_ARCH=	yes

DATADIR=	${PREFIX}/share/lxde
INSTALLS_ICONS=	YES

PORTDOCS=	AUTHORS
OPTIONS_DEFINE=	DOCS

post-patch:
	@${REINPLACE_CMD} -e 's|cp -raf --no-preserve=ownership|cp -RpPf|' \
		${WRKSRC}/Makefile.in

post-install:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${PORTDOCS:S|^|${WRKSRC}/|} ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
