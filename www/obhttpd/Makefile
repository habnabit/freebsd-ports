# $FreeBSD$

PORTNAME=	obhttpd
PORTVERSION=	5.8.20151023
CATEGORIES=	www

MAINTAINER=	koue@chaosophia.net
COMMENT=	OpenBSD http server

LICENSE=	BSD3CLAUSE

WRKSRC=		${WRKDIR}/${GH_PROJECT}-${PORTVERSION}/src/usr.sbin/${GH_PROJECT}

USE_GITHUB=	yes
GH_ACCOUNT=	koue
GH_PROJECT=	httpd

USE_OPENSSL=	yes
USE_RC_SUBR=	obhttpd

WITH_OPENSSL_PORT=yes
OPENSSL_PORT=	security/libressl

CFLAGS+=	-Wall

MAKE_ARGS+=	BINDIR=${PREFIX}/sbin MANDIR=${PREFIX}/man/man

USERS=		www
GROUPS=		www

PLIST_FILES=	sbin/obhttpd \
		man/man5/obhttpd.conf.5.gz \
		man/man7/patterns.7.gz \
		man/man8/obhttpd.8.gz

post-patch:
	${REINPLACE_CMD} -e 's|httpd$$|obhttpd|g' \
			 -e 's|httpd.conf.5|obhttpd.conf.5|g' \
			 -e 's|httpd.8|obhttpd.8|g' ${WRKSRC}/Makefile
	${MV} ${WRKSRC}/httpd.conf.5 ${WRKSRC}/obhttpd.conf.5
	${MV} ${WRKSRC}/httpd.8 ${WRKSRC}/obhttpd.8
	${REINPLACE_CMD} -e 's|/etc/httpd.conf|${PREFIX}/etc/obhttpd.conf|g' \
		${WRKSRC}/httpd.h

.include <bsd.port.mk>
