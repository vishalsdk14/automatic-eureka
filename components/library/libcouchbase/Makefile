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
# Copyright (c) 2016 Sergey Avseyev
#
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		libcouchbase
COMPONENT_VERSION=	2.6.1
COMPONENT_PROJECT_URL=	http://developer.couchbase.com/documentation/server/4.0/sdks/c-2.4/c-intro.html
COMPONENT_SUMMARY=	An library implementing Couchbase protocol
COMPONENT_FMRI=         library/libcouchbase
COMPONENT_CLASSIFICATION=       System/Libraries
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH=	sha256:c4d4914355a18067fb18f4a1c3249a4a3c639aadbb7e0279fa87421b17b89700
COMPONENT_ARCHIVE_URL=	http://packages.couchbase.com/clients/c/$(COMPONENT_ARCHIVE)
COMPONENT_LICENSE=	ASL-2
COMPONENT_LICENSE_FILE=	LICENSE

include $(WS_MAKE_RULES)/prep.mk
include $(WS_MAKE_RULES)/cmake.mk
include $(WS_MAKE_RULES)/ips.mk

PATH=/usr/bin:/usr/gnu/bin:/usr/sbin

CMAKE_OPTIONS+=	-DCMAKE_BUILD_TYPE=Release
CMAKE_OPTIONS+=	-DLCB_NO_TESTS=1

# common targets
build:		$(BUILD_32_and_64)

install:	$(INSTALL_32_and_64)

test:		$(TEST_32_and_64)

REQUIRED_PACKAGES += library/libev
REQUIRED_PACKAGES += library/libevent
REQUIRED_PACKAGES += library/security/openssl
REQUIRED_PACKAGES += system/library
REQUIRED_PACKAGES += system/library/g++-4-runtime
REQUIRED_PACKAGES += system/library/gcc-4-runtime
REQUIRED_PACKAGES += system/library/math
