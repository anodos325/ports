# Created by: Kris Kennaway <kris@FreeBSD.org>
# $FreeBSD$

PORTNAME=	source-highlight
DISTVERSION=	3.1.8
PORTREVISION=	2
CATEGORIES=	textproc
MASTER_SITES=	GNU/src-highlite

MAINTAINER=	ports@FreeBSD.org
COMMENT=	C/C++ and Java sources to HTML converter

LICENSE=	GPLv3
LICENSE_FILE=	${WRKSRC}/COPYING

BROKEN_powerpc64=	fails to configure: checking for exit in -lboost_regex... (cached) no
BROKEN_sparc64=		fails to compile with GCC 4.2

BUILD_DEPENDS=	exctags:devel/ctags
LIB_DEPENDS=	libboost_regex.so:devel/boost-libs

USES=		gmake pathfix libtool localbase
GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--with-bash-completion
INSTALL_TARGET=	install-strip
USE_LDCONFIG=	yes

INFO=		source-highlight source-highlight-lib

OPTIONS_DEFINE=	DOCS EXAMPLES

PORTDOCS=	*
PORTEXAMPLES=	*

do-test:
	@cd ${WRKSRC} && ${SETENV} ${MAKE_ENV} ${MAKE_CMD} ${_MAKE_JOBS} ${MAKE_ARGS} check

.include <bsd.port.mk>
