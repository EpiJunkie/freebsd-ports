PORTNAME=	xgboost
DISTVERSIONPREFIX=	v
DISTVERSION=	1.7.1
CATEGORIES=	misc # machine-learning

MAINTAINER=	yuri@FreeBSD.org
COMMENT=	Scalable, Portable and Distributed Gradient Boosting (GBDT, GBRT, GBM)
WWW=		https://xgboost.ai/

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

BROKEN_armv7=	compilation fails: non-constant-expression cannot be narrowed from type 'unsigned long long' to 'size_t', see https://github.com/dmlc/xgboost/issues/8489
BROKEN_i386=	compilation fails: non-constant-expression cannot be narrowed from type 'unsigned long long' to 'size_t', see https://github.com/dmlc/xgboost/issues/8489

LIB_DEPENDS=	libdmlc.so:devel/dmlc-core

USES=		cmake:testing compiler:c++11-lang localbase:ldflags
USE_LDCONFIG=	yes

USE_GITHUB=	yes
GH_ACCOUNT=	dmlc
GH_TUPLE=	\
		NVlabs:cub:af39ee2:NVlabs_cub/cub \
		rapidsai:gputreeshap:acb5be3:rapidsai_gputreeshap/gputreeshap

LDFLAGS+=	${LOCALBASE}/lib/libdmlc.so -lexecinfo

CMAKE_TESTING_ON=	GOOGLE_TEST # 1 test fails, see https://github.com/dmlc/xgboost/issues/8425

OPTIONS_DEFINE=		OPENMP

OPENMP_CMAKE_BOOL=	USE_OPENMP

.include <bsd.port.mk>
