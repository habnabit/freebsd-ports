# Created by: Sergey Kozlov <kozlov.sergey.404@gmail.com>
# $FreeBSD$

PORTNAME=	kibana
PORTVERSION?=	4.2.1
DISTVERSIONSUFFIX=	-linux-x86
CATEGORIES=	textproc www
MASTER_SITES=	https://download.elastic.co/kibana/kibana/ \
		http://download.elastic.co/kibana/kibana/
PKGNAMESUFFIX?=	42

MAINTAINER=	kozlov.sergey.404@gmail.com
COMMENT=	Browser based analytics and search interface to ElasticSearch

LICENSE=	APACHE20

RUN_DEPENDS=	node012>=0:${PORTSDIR}/www/node012

NO_BUILD=	yes
NO_ARCH=	yes
WWWDIR=		${PREFIX}/www/${PORTNAME}${PKGNAMESUFFIX}
USE_RC_SUBR=	${PORTNAME}

do-install:
	${CP} ${WRKSRC}/config/kibana.yml ${STAGEDIR}${PREFIX}/etc/kibana.yml.sample
	${MKDIR} ${STAGEDIR}${WWWDIR}
	cd ${WRKSRC} && \
		${RM} -r bin config node && \
		${COPYTREE_SHARE} . ${STAGEDIR}${WWWDIR}

.include <bsd.port.mk>
