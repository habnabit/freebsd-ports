# Created by: Gyorgy Teubel <tgyurci@freemail.hu>
# $FreeBSD$

PORTNAME=	wdfs
PORTVERSION=	1.4.2
DISTVERSIONPREFIX=v
PORTREVISION=	6
CATEGORIES=	sysutils
PKGNAMEPREFIX=	fusefs-

MAINTAINER=	silverless@gmx.com
COMMENT=	Mount remote WedDAV directories with Fuse

LICENSE=	GPLv2

LIB_DEPENDS=	libneon.so:${PORTSDIR}/www/neon

GNU_CONFIGURE=	yes
USES=		fuse pkgconfig
USE_GITHUB=	yes
GH_ACCOUNT=	jmesmon
GH_TAGNAME=	3fa7035
USE_GNOME=	glib20

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/src/wdfs ${STAGEDIR}${PREFIX}/bin

.include <bsd.port.mk>
