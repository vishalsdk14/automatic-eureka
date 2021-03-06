#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL)". You may
# only use this file in accordance with the terms of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source. A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright (c) 2016 Alexander Pyhalov
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		gimp
COMPONENT_VERSION=	2.8.16
COMPONENT_REVISION=	1
COMPONENT_PROJECT_URL=	http://www.gimp.org/
COMPONENT_SUMMARY=	The Gimp image editor
COMPONENT_FMRI=		image/editor/gimp
COMPONENT_CLASSIFICATION=	Applications/Graphics and Imaging
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.bz2
COMPONENT_ARCHIVE_HASH=	\
    sha256:95e3857bd0b5162cf8d1eda8c78b741eef968c3e3ac6c1195aaac2a4e2574fb7
COMPONENT_ARCHIVE_URL=	http://download.gimp.org/pub/gimp/v2.8/$(COMPONENT_ARCHIVE)

include $(WS_TOP)/make-rules/prep.mk
include $(WS_TOP)/make-rules/configure.mk
include $(WS_TOP)/make-rules/ips.mk

PATH=/usr/gnu/bin:/usr/bin

CFLAGS += -I/usr/include/glib-2.0 -I/usr/lib/glib-2.0/include

COMPONENT_PREP_ACTION =	( cd $(@D)  && \
				libtoolize --force &&\
				intltoolize --force --copy --automake &&\
				aclocal -I. &&\
				automake -a -c -f &&\
				autoconf)

CONFIGURE_OPTIONS+=	--sysconfdir=/etc
CONFIGURE_OPTIONS+=	--libexecdir=/usr/lib
CONFIGURE_OPTIONS+=	--localstatedir=/var/lib
CONFIGURE_OPTIONS+=	--enable-mp
CONFIGURE_OPTIONS+=	--enable-default-binary
CONFIGURE_OPTIONS+=	--enable-mmx=no
CONFIGURE_OPTIONS+=	--with-lcms=2
#CONFIGURE_OPTIONS+=	--enable-glibtest=no

# common targets
build:		$(BUILD_32)

install:	$(INSTALL_32)

test:		$(TEST_32)

REQUIRED_PACKAGES += codec/jasper
REQUIRED_PACKAGES += compress/bzip2
REQUIRED_PACKAGES += image/library/babl
REQUIRED_PACKAGES += image/library/gegl
REQUIRED_PACKAGES += image/library/libexif
REQUIRED_PACKAGES += image/library/libjpeg6
REQUIRED_PACKAGES += image/library/libjpeg6-ijg
REQUIRED_PACKAGES += image/library/libpng
REQUIRED_PACKAGES += image/library/librsvg
REQUIRED_PACKAGES += image/library/libtiff
REQUIRED_PACKAGES += library/aalib
REQUIRED_PACKAGES += library/desktop/cairo
REQUIRED_PACKAGES += library/desktop/gdk-pixbuf
REQUIRED_PACKAGES += library/desktop/gtk2
REQUIRED_PACKAGES += library/desktop/pango
REQUIRED_PACKAGES += library/glib2
REQUIRED_PACKAGES += library/lcms2
REQUIRED_PACKAGES += library/libpoppler
REQUIRED_PACKAGES += library/python/pygobject-26
REQUIRED_PACKAGES += library/python/pygtk2
REQUIRED_PACKAGES += library/python/pygtk2-26
REQUIRED_PACKAGES += library/zlib
REQUIRED_PACKAGES += print/filter/ghostscript
REQUIRED_PACKAGES += runtime/python-26
REQUIRED_PACKAGES += system/library
REQUIRED_PACKAGES += system/library/fontconfig
REQUIRED_PACKAGES += system/library/freetype-2
REQUIRED_PACKAGES += system/library/libdbus
REQUIRED_PACKAGES += system/library/libdbus-glib
REQUIRED_PACKAGES += system/library/math
REQUIRED_PACKAGES += x11/library/libx11
REQUIRED_PACKAGES += x11/library/libxcursor
REQUIRED_PACKAGES += x11/library/libxext
REQUIRED_PACKAGES += x11/library/libxfixes
REQUIRED_PACKAGES += x11/library/libxmu
REQUIRED_PACKAGES += x11/library/libxpm
