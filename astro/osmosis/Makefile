# Created by: Gleb Smirnoff <glebius@FreeBSD.org>
# $FreeBSD$

PORTNAME=	osmosis
PORTVERSION=	0.46
CATEGORIES=	astro java
MASTER_SITES=	http://bretth.dev.openstreetmap.org/osmosis-build/ \
		http://mirror.amdmi3.ru/distfiles/

MAINTAINER=	amdmi3@FreeBSD.org
COMMENT=	Command line Java app for processing OpenStreetMap data

LICENSE=	PD
LICENSE_FILE=	${WRKSRC}/copying.txt

NO_WRKSUBDIR=	yes
USES=		tar:tgz
USE_JAVA=	yes
JAVA_VERSION=	1.6+
NO_BUILD=	yes
NO_ARCH=	yes

PLIST_FILES=	bin/${PORTNAME}
PORTDATA=	*
PORTDOCS=	*

OPTIONS_DEFINE=	DOCS

post-patch:
	@${REINPLACE_CMD} -e 's|^\(MYAPP_HOME=\).*|\1${DATADIR}|' ${WRKSRC}/bin/osmosis

do-install:
	@${MKDIR} ${STAGEDIR}${DATADIR}
	@cd ${WRKSRC} && ${COPYTREE_SHARE} "script config lib" ${STAGEDIR}${DATADIR}/
	${INSTALL_SCRIPT} ${WRKSRC}/bin/osmosis ${STAGEDIR}${PREFIX}/bin/

do-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/changes.txt ${WRKSRC}/readme.txt ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
