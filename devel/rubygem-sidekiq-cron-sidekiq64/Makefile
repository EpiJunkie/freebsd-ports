PORTNAME=	sidekiq-cron
PORTVERSION=	1.8.0
CATEGORIES=	devel rubygems
MASTER_SITES=	RG
PKGNAMESUFFIX=	-sidekiq64

MAINTAINER=	mfechner@FreeBSD.org
COMMENT=	Enables to set jobs to be run in specified time (using CRON notation)
WWW=		https://github.com/ondrejbartas/sidekiq-cron

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

RUN_DEPENDS=	rubygem-fugit>=1<2:devel/rubygem-fugit \
		rubygem-sidekiq64>=4.2.1:devel/rubygem-sidekiq64

USES=		gem
USE_RUBY=	yes

NO_ARCH=	yes

.include <bsd.port.mk>
