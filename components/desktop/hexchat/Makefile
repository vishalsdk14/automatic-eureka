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
# Copyright 2016 Marcel Telka <marcel@telka.sk>
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		hexchat
COMPONENT_VERSION=	2.12.1
COMPONENT_REVISION=	1
COMPONENT_PROJECT_URL=	https://hexchat.github.io/
COMPONENT_SUMMARY=	HexChat IRC client
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.xz
COMPONENT_ARCHIVE_HASH=	\
    sha256:5201b0c6d17dcb8c2cb79e9c39681f8e052999ba8f7b5986d5c1e7dc68fa7c6b
COMPONENT_ARCHIVE_URL=	https://dl.hexchat.net/hexchat/$(COMPONENT_ARCHIVE)
# We need to use non-default User-Agent for the fetch, otherwise we are denied
# to download the source file.
COMPONENT_FETCH_USER_AGENT= fetch

include $(WS_TOP)/make-rules/prep.mk
include $(WS_TOP)/make-rules/configure.mk
include $(WS_TOP)/make-rules/ips.mk

PATH=/usr/gnu/bin:/usr/bin

CONFIGURE_OPTIONS += --enable-python=python2.7

CONFIGURE_ENV += PERL=$(PERL)
CONFIGURE_ENV += INTLTOOL_PERL=$(PERL)

build:          $(BUILD_32)

install:        $(INSTALL_32)

test:           $(NO_TESTS)

BUILD_PKG_DEPENDENCIES =	$(BUILD_TOOLS)

include $(WS_TOP)/make-rules/depend.mk
