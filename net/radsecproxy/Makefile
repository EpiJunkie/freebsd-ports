PORTNAME=	radsecproxy
DISTVERSION=	1.9.1
CATEGORIES=	net
MASTER_SITES=	https://github.com/${PORTNAME}/${PORTNAME}/releases/download/${DISTVERSION}/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Generic RADIUS proxy
WWW=		https://radsecproxy.github.io

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

LIB_DEPENDS=	libnettle.so:security/nettle

USES=		compiler:c11 cpe localbase:ldflags ssl
USE_RC_SUBR=	${PORTNAME}
CPE_VENDOR=	uninett

GNU_CONFIGURE=	yes

CONFIGURE_ARGS=	--with-ssl=${OPENSSLBASE}

post-install:
	${MAKE} install-man -C ${WRKSRC} ${MAKE_ARGS}
	${INSTALL_DATA} ${WRKSRC}/radsecproxy.conf-example \
		${STAGEDIR}${PREFIX}/etc

.include <bsd.port.mk>
