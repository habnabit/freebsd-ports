# Created by: Mikhail Teterin
# $FreeBSD$

PORTNAME=	libgpc
PORTVERSION=	2.32
CATEGORIES=	devel math graphics
MASTER_SITES=	ftp://ftp.cs.man.ac.uk/pub/toby/gpc/
DISTNAME=	gpc${PORTVERSION:S/.//}

MAINTAINER=	mi@aldan.algebra.com
COMMENT=	Generic Polygon Clipper

BROKEN=		unfetchable
USES=		dos2unix uidfix zip
PLIST_FILES=	lib/libgpc.so.2	\
		lib/libgpc.so	lib/libgpc.a	\
		include/gpc.h
USE_LDCONFIG=	yes
NO_CDROM=	Can't be used for profit without permission

MAKEFILE=	${FILESDIR}/BSDmakefile

.include <bsd.port.mk>
