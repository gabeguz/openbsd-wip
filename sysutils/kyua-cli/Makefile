# $OpenBSD $

COMMENT =		testing framework
DISTNAME =		kyua-cli-0.5

SHARED_LIBS += ct                   5.0      # .4.0
CATEGORIES =		devel sysutils
HOMEPAGE =		https://code.google.com/p/kyua/

MAINTAINER =	Sergey Bronnikov <estetus@gmail.com>

PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += c m stdc++

BUILD_DEPENDS =		sysutils/atf \
			devel/lutok

MASTER_SITES =		https://kyua.googlecode.com/files/

CONFIGURE_STYLE =	gnu

.include <bsd.port.mk>
