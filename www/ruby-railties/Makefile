# $OpenBSD: Makefile,v 1.5 2012/09/23 16:57:36 jeremy Exp $

COMMENT=	glues the Ruby on Rails framework together

VERSION=	3.2.13
DISTNAME=	railties-${VERSION}
CATEGORIES=	www

# MIT License
PERMIT_PACKAGE_CDROM=	Yes

MODULES=	lang/ruby

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	${MODRUBY_RAKE_DEPENDS} \
		devel/ruby-activesupport,${MODRUBY_FLAVOR}=${VERSION} \
		devel/ruby-actionpack,${MODRUBY_FLAVOR}=${VERSION} \
		devel/ruby-rdoc,${MODRUBY_FLAVOR}>=3.4,<4.0 \
		sysutils/ruby-thor,${MODRUBY_FLAVOR}>=0.14.6,<0.15 \
		www/ruby-rack-ssl,${MODRUBY_FLAVOR}>=1.3.2,<1.4

# XXX to be kept in sync with ruby.port.mk
FLAVOR ?=	ruby19

.if ${FLAVOR} != ruby19
# Ruby 1.9 ships with a gem version of rdoc, so you don't need
# to install the gem.
RUN_DEPENDS+=	devel/ruby-rdoc,${MODRUBY_FLAVOR}>=3.4,<4.0
.endif

CONFIGURE_STYLE=ruby gem

.include <bsd.port.mk>
