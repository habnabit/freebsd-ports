# Created by: Alexey Dokuchaev <danfe@FreeBSD.org>
# $FreeBSD$

PORTNAME=	choqok
PORTVERSION=	1.5
CATEGORIES=	www kde
MASTER_SITES=	SF/${PORTNAME}/Choqok/

MAINTAINER=	kde@FreeBSD.org
COMMENT=	KDE micro-blogging client

LICENSE=	GPLv3
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS=	libqjson.so:${PORTSDIR}/devel/qjson \
		libqoauth.so:${PORTSDIR}/net/qoauth \
		libtelepathy-qt4.so:${PORTSDIR}/net-im/telepathy-qt4

USE_KDE4=	attica automoc4 kdelibs kdeprefix
USE_QT4=	gui imageformats_run network \
		moc_build qmake_build rcc_build uic_build
USES=		cmake gettext tar:xz
USE_LDCONFIG=	yes

.include <bsd.port.mk>
