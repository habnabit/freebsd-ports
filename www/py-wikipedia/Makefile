# Created by: Olivier Duchateau
# $FreeBSD$

PORTNAME=	wikipedia
PORTVERSION=	1.4.0
CATEGORIES=	www python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	python@FreeBSD.org
COMMENT=	Wikipedia API for Python

LICENSE=	MIT

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}beautifulsoup>=4.3.2:${PORTSDIR}/www/py-beautifulsoup \
	${PYTHON_PKGNAMEPREFIX}requests>=2.7:${PORTSDIR}/www/py-requests

USES=	python
USE_PYTHON=	distutils autoplist

.include <bsd.port.mk>
