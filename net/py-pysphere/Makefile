# Created by: olli hauer <ohauer@FreeBSD.org>
# $FreeBSD$

PORTNAME=	pysphere
PORTVERSION=	0.1.8
PORTREVISION=	3
CATEGORIES=	net python
MASTER_SITES=	GOOGLE_CODE
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	ohauer@FreeBSD.org
COMMENT=	Python API for interaction with the vSphere Web Services SDK

LICENSE=	BSD3CLAUSE

DEPRECATED=	No longer maintained, please use net/py-pyvmomi by VMware
EXPIRATION_DATE=2015-12-12

USES=		dos2unix zip shebangfix python:2.7
USE_PYTHON=	distutils autoplist

SHEBANG_FILES=	*.py \
		pysphere/ZSI/*.py \
		pysphere/ZSI/generate/*.py \
		pysphere/ZSI/wstools/*.py

.include <bsd.port.mk>
