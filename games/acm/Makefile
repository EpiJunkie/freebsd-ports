PORTNAME=	acm
PORTVERSION=	5.0
PORTREVISION=	3
CATEGORIES=	games
MASTER_SITES=	# none known

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Aerial combat simulator for X11

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/COPYING

BROKEN=		unfetchable
DEPRECATED=	Abandoned upstream. Does not work.
EXPIRATION_DATE=	2023-03-31

USES=		perl5 xorg
USE_PERL5=	build
USE_XORG=	x11 xext
HAS_CONFIGURE=	yes
CONFIGURE_ARGS=	--prefix=${PREFIX} --x-includes=${LOCALBASE}/include \
		--x-libraries=${LOCALBASE}/lib
CONFIGURE_ENV=	ac_cv_lib_Xm_XmCreateBulletinBoard=no \
		ac_cv_lib_gdbm_dbm_fetch=no
MAKE_ARGS=	prefix=${STAGEDIR}${PREFIX}/ OBVDIR=${STAGEDIR}${DATADIR}/

# Fix build with clang11
CFLAGS+=	-fcommon

OPTIONS_DEFINE=	SOUND

SOUND_LIB_DEPENDS=	libaudio.so:audio/nas
SOUND_CONFIGURE_ENV_OFF=	ac_cv_lib_audio_AuCloseServer=no

.include <bsd.port.mk>
