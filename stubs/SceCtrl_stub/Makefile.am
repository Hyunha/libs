# Copyright (C) 2015 PSP2SDK Project
#
# This Source Code Form is subject to the terms of the Mozilla Public
# License, v. 2.0. If a copy of the MPL was not distributed with this
# file, You can obtain one at http://mozilla.org/MPL/2.0/.

include $(top_srcdir)/stubs/common.mk

PREFIX = _SceCtrl-0001_
ENTRIES_PREFIX = $(PREFIX)F00_

NIDS = 0x104ed1a7 0x15f96fb0 0x67e7ab83 0xa497b150 	\
	0xa9c3ced6 0xd8294c9c 0xe9cb69c8 0xec752aaf

ENTRIES = $(call GET_ENTRIES,$(ENTRIES_PREFIX),$(NIDS))

lib_LIBRARIES = libSceCtrl_stub.a
libSceCtrl_stub_a_SOURCES = SceCtrl_stub.S
am_libSceCtrl_stub_a_OBJECTS = $(call GET_OBJECTS,$(PREFIX),$(ENTRIES))

$(PREFIX)head.o: $(libSceCtrl_stub_a_SOURCES)
	$(COMPILE_HEAD)

$(PREFIX)NIDS.o: $(libSceCtrl_stub_a_SOURCES)
	$(COMPILE_NIDS)

$(ENTRIES): $(libSceCtrl_stub_a_SOURCES)
	$(call COMPILE_ENTRIES,$(ENTRIES_PREFIX))
