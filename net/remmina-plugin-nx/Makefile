# Created by: Koichiro IWAO <meta+ports@vmeta.jp>
# $FreeBSD$

PKGNAMESUFFIX=	-nx

COMMENT=	Remmina plugin for NX

USE_XORG+=	xkbfile

MASTERDIR=	${.CURDIR}/../remmina-plugins

LIB_DEPENDS+=	libssh_threads.so:${PORTSDIR}/security/libssh

PLIST_SUB+=	ICONS="" SSH="@comment "

.include "${MASTERDIR}/Makefile"
