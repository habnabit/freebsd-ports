# Created by: Antoine Brodin <antoine@FreeBSD.org>
# $FreeBSD$

PORTNAME=	libvhdi
PORTVERSION=	20151205
DISTVERSIONPREFIX=	alpha-
CATEGORIES=	devel
MASTER_SITES=	https://github.com/libyal/libvhdi/releases/download/${PORTVERSION}/ \
		LOCAL/antoine

MAINTAINER=	antoine@FreeBSD.org
COMMENT=	Library and tools to access the Virtual Hard Disk image format

LICENSE=	LGPL3

GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--enable-python --with-libintl-prefix=${LOCALBASE}
USES=		fuse gettext libtool pathfix pkgconfig python
USE_LDCONFIG=	yes
INSTALL_TARGET=	install-strip
WRKSRC=		${WRKDIR}/${PORTNAME}-${PORTVERSION}

PORTDOCS=	AUTHORS ChangeLog

OPTIONS_DEFINE=	DOCS

post-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${PORTDOCS:S,^,${WRKSRC}/,} ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
