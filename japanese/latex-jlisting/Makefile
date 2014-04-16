# $FreeBSD$

PORTNAME=	latex-jlisting
PORTVERSION=	0.2
CATEGORIES=	japanese print
MASTER_SITES=	SFJP/mytexpert/26068
DISTNAME=	jlisting.sty
EXTRACT_SUFX=	.bz2

MAINTAINER=	hiroto.kagotani@gmail.com
COMMENT=	Enhancement of lstlisting environment for handling Japanese text

USE_TEX=	texhash
PLIST_SUB=	TEXMFLOCALDIR=${TEXMFLOCALDIR} MKTEXLSR=${MKTEXLSR}

MKTEXLSR=	${LOCALBASE}/bin/mktexlsr
WRKSRC=		${WRKDIR}/${PORTNAME:S/^latex-//}

do-extract:
	${MKDIR} ${WRKSRC}
	cd ${DISTDIR}/${DIST_SUBDIR} && ${BZCAT} ${DISTFILES} >${WRKSRC}/${DISTNAME}

do-build:

do-install:
	${MKDIR} ${STAGEDIR}${PREFIX}/${TEXMFLOCALDIR}/jlisting
	${INSTALL_DATA} ${WRKSRC}/${DISTNAME} ${STAGEDIR}${PREFIX}/${TEXMFLOCALDIR}/jlisting

post-install:
	@${MKTEXLSR}

.include <bsd.port.mk>
