# Copyright (C) 2015-2016 Mellanox Technologies Ltd. All rights reserved.
#
# Redistribution and use in source and binary forms, with or without
# modification, are permitted provided that the following conditions
# are met:
#
# 1. Redistributions of source code must retain the above copyright
# notice, this list of conditions and the following disclaimer.
# 2. Redistributions in binary form must reproduce the above copyright
# notice, this list of conditions and the following disclaimer in the
# documentation and/or other materials provided with the distribution.
# 3. Neither the name of the copyright holder nor the names of its
# contributors may be used to endorse or promote products derived from
# this software without specific prior written permission.
#
# THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
# "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
# LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
# A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
# HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
# SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED
# TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR
# PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF
# LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING
# NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
# SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

AM_CPPFLAGS = -I$(top_srcdir)/include
ACLOCAL_AMFLAGS = -I config
AM_CFLAGS = -g -Wall -Werror -I.

bin_PROGRAMS = ibv_test

ibv_test_CXXFLAGS = -g -Wall -O3 -fno-strict-aliasing

ibv_test_CPPFLAGS = \
	-I$(top_srcdir)/src \
	-I$(top_srcdir)/include

ibv_test_SOURCES = \
			 include/common.h \
			 include/verbs_test.h \
			 include/gtest.h \
			 src/main.cc \
			 src/sys.cc
# Add tests HERE
ibv_test_SOURCES += \
			 tests/general/init.cc \
			 tests/cross-channel/query_device.cc \
			 tests/cross-channel/create_cq.cc \
			 tests/cross-channel/post_send_en.cc \
			 tests/cross-channel/post_recv_en.cc \
			 tests/cross-channel/post_send_wait.cc \
			 tests/cross-channel/post_task.cc

ibv_test_SOURCES +=      tests/basic/smoke.cc

if PEER_DIRECT
ibv_test_SOURCES +=      tests/peer-direct/smoke.cc
endif

if TAG_MATCHING
ibv_test_SOURCES +=	 tests/tag-matching/smoke.cc
endif

ibv_test_SOURCES +=      tests/odp/smoke.cc

EXTRA_DIST = src/gtest-all.cc
EXTRA_DIST += autogen.sh
