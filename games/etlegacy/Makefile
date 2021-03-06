# $OpenBSD$

ONLY_FOR_ARCHS=	i386 amd64
CATEGORIES=	games x11
COMMENT=	Wolfenstein Enemy Territory (ET Legacy)

HOMEPAGE=	http://www.etlegacy.com/
MAINTAINER=	Jonathan Gray <jsg@openbsd.org>

GITREV=		17f8c5c1c79461f3c6c86cea0e834de9f57cd5de
DISTNAME=	etlegacy-etlegacy-17f8c5c
PKGNAME=	etlegacy-20130714
MASTER_SITES=	https://github.com/etlegacy/etlegacy/tarball/${GITREV}/

LIB_DEPENDS=	devel/sdl \
		graphics/jpeg \
		net/curl \
		audio/libvorbis
BUILD_DEPENDS=	archivers/zip
RUN_DEPENDS=	games/enemy-territory-data

WANTLIB=	GL GLU ICE SDL SM X11 Xext c curl jpeg m ogg pthread \
		vorbis vorbisfile

MODULES=	devel/cmake \
		lang/lua

CONFIGURE_ARGS =	-DINSTALL_DEFAULT_MODDIR:String=share/enemy-territory \
			-DINSTALL_DEFAULT_BINDIR:String=share/enemy-territory \
			-DBUILD_PAK3_PK3:Bool=True \
			-DBUILD_MOD_PK3:Bool=True

# GPLv3+additions
PERMIT_PACKAGE_CDROM=		Yes

post-install:
	cp ${FILESDIR}/etlegacy.sh ${WRKSRC}/
	@perl -pi -e s,%%LOCALBASE%%,${LOCALBASE}, ${WRKSRC}/etlegacy.sh
	${INSTALL_SCRIPT} ${WRKSRC}/etlegacy.sh ${PREFIX}/bin/etlegacy

.include <bsd.port.mk>
