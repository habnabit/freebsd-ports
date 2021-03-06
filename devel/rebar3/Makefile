# $FreeBSD$

PORTNAME=	rebar3
PORTVERSION=	20151120
CATEGORIES=	devel
MASTER_SITES+=	LOCAL/olgeni:deps \
		http://olgeni.olgeni.com/~olgeni/distfiles/:deps \
		https://s3.amazonaws.com/s3.hex.pm/tarballs/:hex
DISTFILES=	${DISTNAME}${EXTRACT_SUFX} \
		rebar3-cache-3${EXTRACT_SUFX}:deps
EXTRACT_ONLY=	${DISTNAME}${EXTRACT_SUFX} \
		rebar3-cache-3${EXTRACT_SUFX}

MAINTAINER=	olgeni@FreeBSD.org
COMMENT=	Build tool for Erlang

LICENSE=	APACHE20

BUILD_DEPENDS=	${LOCALBASE}/bin/erl:${PORTSDIR}/lang/erlang \
		${LOCALBASE}/bin/git:${PORTSDIR}/devel/git
RUN_DEPENDS=	${LOCALBASE}/bin/erl:${PORTSDIR}/lang/erlang

OPTIONS_DEFINE=	BASH ZSH

USE_GITHUB=	yes
GH_ACCOUNT=	rebar
GH_TAGNAME=	356ac50

PLIST_FILES=	bin/${PORTNAME}
PORTEXAMPLES=	rebar.config.sample

BASH_PLIST_FILES=	share/bash-completion/completions/rebar3
ZSH_PLIST_FILES=	share/zsh/site-functions/_rebar3

# from rebar.config
REBAR_DEPS=	bbmustache-1.0.4 \
		certifi-0.1.1 \
		cf-0.2.1 \
		cth_readable-1.0.1 \
		erlware_commons-0.16.0 \
		eunit_formatters-0.2.0 \
		getopt-0.8.2 \
		providers-1.5.0 \
		relx-3.8.0 \
		ssl_verify_hostname-1.0.5

REBAR_PLUGINS=	rebar3_hex-1.9.0

.for _dep in ${REBAR_DEPS} ${REBAR_PLUGINS}
DISTFILES+=	${_dep}.tar:hex
.endfor

.include <bsd.port.options.mk>

post-extract:
	@${REINPLACE_CMD} -e 's/{vsn, "git"}/{vsn, "${GH_TAGNAME}"}/' ${WRKSRC}/src/rebar.app.src
.for _dep in ${REBAR_DEPS}
	${MKDIR} ${WRKSRC}/_build/default/lib/${_dep:C/-.*//}
	${TAR} xOf ${DISTDIR}/${_dep}.tar contents.tar.gz |\
		${TAR} xfz - -C ${WRKSRC}/_build/default/lib/${_dep:C/-.*//}
.endfor
.for _dep in ${REBAR_PLUGINS}
	${MKDIR} ${WRKSRC}/_build/default/plugins/${_dep:C/-.*//}
	${TAR} xOf ${DISTDIR}/${_dep}.tar contents.tar.gz |\
		${TAR} xfz - -C ${WRKSRC}/_build/default/plugins/${_dep:C/-.*//}
.endfor

	@${MKDIR} ${WRKSRC}/_build/bootstrap/lib
	@${MKDIR} ${WRKSRC}/_build/bootstrap/plugins
.for _dep in ${REBAR_DEPS}
	${LN} -sf ${WRKSRC}/_build/default/lib/${_dep:C/-.*//} ${WRKSRC}/_build/bootstrap/lib/
.endfor
.for _dep in ${REBAR_PLUGINS}
	${LN} -sf ${WRKSRC}/_build/default/plugins/${_dep:C/-.*//} ${WRKSRC}/_build/bootstrap/plugins/
.endfor

do-build:
	@${RM} ${WRKSRC}/rebar.lock
	@cd ${WRKSRC} && HOME=${WRKDIR} ./bootstrap

do-install:
	${INSTALL_SCRIPT} ${WRKSRC}/${PORTNAME} ${STAGEDIR}${PREFIX}/bin/
.if ${PORT_OPTIONS:MBASH}
	@${MKDIR} ${STAGEDIR}${PREFIX}/share/bash-completion/completions
	${INSTALL_DATA} ${WRKSRC}/priv/shell-completion/bash/rebar3 \
		${STAGEDIR}${PREFIX}/share/bash-completion/completions/rebar3
.endif
.if ${PORT_OPTIONS:MZSH}
	@${MKDIR} ${STAGEDIR}${PREFIX}/share/zsh/site-functions/
	${INSTALL_DATA} ${WRKSRC}/priv/shell-completion/zsh/_rebar3 \
		${STAGEDIR}${PREFIX}/share/zsh/site-functions/
.endif
	@${MKDIR} ${STAGEDIR}${EXAMPLESDIR}
	${INSTALL_DATA} ${WRKSRC}/rebar.config.sample ${STAGEDIR}${EXAMPLESDIR}

.include <bsd.port.mk>
