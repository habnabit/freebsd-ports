# Created by: mike@binghamton.edu
# $FreeBSD$

PORTNAME=	tf
PORTVERSION=	5.0b8
PORTREVISION=	2
CATEGORIES=	net games
MASTER_SITES=	SF/tinyfugue/tinyfugue/5.0%20beta%208
DISTNAME=	${PORTNAME}-${PORTVERSION:S/.//}

MAINTAINER=	johans@FreeBSD.org
COMMENT=	Popular programmable MUD client, with macro support and more

LIB_DEPENDS=	libpcre.so:${PORTSDIR}/devel/pcre

GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--enable-manpage --enable-version --enable-symlink \
		--datadir=${PREFIX}/lib --with-inclibpfx=${LOCALBASE}
USE_OPENSSL=	yes
LDFLAGS+=	-L${LOCALBASE}

PLIST_SUB=	DISTNAME=${DISTNAME}

post-patch:
	@${REINPLACE_CMD} 's:@.*dir@:$${DESTDIR}&:' ${WRKSRC}/unix/vars.mak.in
	@${REINPLACE_CMD} '/ln -s/s@(TF)@(TF:T)@' ${WRKSRC}/unix/unix.mak

post-build:
	@${STRIP_CMD} ${WRKSRC}/src/tf

.include <bsd.port.mk>
