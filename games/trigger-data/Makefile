# $FreeBSD$

PORTNAME=	trigger-data
PORTVERSION=	0.6.1
CATEGORIES=	games
MASTER_SITES=	SF/trigger-rally/trigger-rally/trigger-${PORTVERSION}
DISTNAME=	trigger-rally-${PORTVERSION}-data

MAINTAINER=	makc@FreeBSD.org
COMMENT=	Data files for trigger-rally

BROKEN=		unfetchable
USES=		tar:bzip2

DATADIR=	${PREFIX}/share/trigger-rally

NO_ARCH=	yes
NO_BUILD=	yes

do-install:
	cd ${WRKSRC} && ${COPYTREE_SHARE} . ${STAGEDIR}${DATADIR}
.for i in 16 22 24 32 36 48 64 72 96 128 192 256
	${MKDIR} ${STAGEDIR}${PREFIX}/share/icons/hicolor/${i}x${i}/apps/ && \
	${MV} ${STAGEDIR}${DATADIR}/icon/trigger-${i}.png \
		${STAGEDIR}${PREFIX}/share/icons/hicolor/${i}x${i}/apps/trigger.png
.endfor
# Avoid conflict with trigger-rally
	@${RM} -f ${STAGEDIR}${DATADIR}/COPYING* \
		${STAGEDIR}${DATADIR}/README*

.include <bsd.port.mk>
