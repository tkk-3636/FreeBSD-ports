# $FreeBSD$

PORTNAME=	qwt
PORTVERSION=	6.1.3
CATEGORIES=	x11-toolkits devel
MASTER_SITES=	SF
PKGNAMESUFFIX=	6-designerplugin

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Qt Designer plugin for Qwt

LIB_DEPENDS=	libqwt6.so:x11-toolkits/qwt6

USES=		gmake qmake tar:bzip2
USE_QT4=	designer moc_build rcc_build
QMAKE_ARGS+=	CONFIG+=QwtDesigner \
		PLUGINDIR=${PREFIX}/${QT_PLUGINDIR_REL}

PLIST_FILES=	${QT_PLUGINDIR_REL}/designer/libqwt6_designer_plugin.so

STRIP_FILES=	${QT_PLUGINDIR_REL}/designer/libqwt6_designer_plugin.so

CONFIGURE_WRKSRC=	${WRKSRC}/designer
BUILD_WRKSRC=	${CONFIGURE_WRKSRC}
INSTALL_WRKSRC=	${CONFIGURE_WRKSRC}

post-install:
	${STRIP_CMD} ${STRIP_FILES:S,^,${STAGEDIR}${PREFIX}/,}

.include <bsd.port.mk>
