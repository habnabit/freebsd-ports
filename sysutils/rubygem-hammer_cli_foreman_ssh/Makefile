# Created by: Michael Moll <kvedulv@kvedulv.de>
# $FreeBSD$

PORTNAME=	hammer_cli_foreman_ssh
PORTVERSION=	0.0.3
CATEGORIES=	sysutils ruby
MASTER_SITES=	RG

MAINTAINER=	mmoll@FreeBSD.org
COMMENT=	SSH host commands for Hammer CLI

LICENSE=	GPLv3

RUN_DEPENDS=	rubygem-hammer_cli_foreman>=0.1.2:${PORTSDIR}/sysutils/rubygem-hammer_cli_foreman \
		rubygem-net-ssh-multi>=1.2.1:${PORTSDIR}/security/rubygem-net-ssh-multi

USE_RUBY=	yes
USE_RUBYGEMS=	yes
RUBYGEM_AUTOPLIST=	yes
PLIST_FILES=	"@sample etc/hammer/cli.modules.d/foreman_ssh.yml.sample"

post-install:
		${MKDIR} ${STAGEDIR}${PREFIX}/etc/hammer/cli.modules.d
		${INSTALL_DATA} ${WRKSRC}/config/foreman_ssh.yml ${STAGEDIR}${PREFIX}/etc/hammer/cli.modules.d/foreman_ssh.yml.sample

.include <bsd.port.mk>
