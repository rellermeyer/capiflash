# IBM_PROLOG_BEGIN_TAG
# This is an automatically generated prolog.
#
# $Source: src/test/ffdc/makefile $
#
# IBM Data Engine for NoSQL - Power Systems Edition User Library Project
#
# Contributors Listed Below - COPYRIGHT 2014,2015
# [+] International Business Machines Corp.
#
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or
# implied. See the License for the specific language governing
# permissions and limitations under the License.
#
# IBM_PROLOG_END_TAG
UNAME=$(shell uname)

# Where to find user code.(Relative path(from the makefile) preferred for portability)
ROOTPATH = ../../..

#test code != production code, so allow warnings here.
ALLOW_WARNINGS = yes

include ${ROOTPATH}/config.mk

#this application originates in surelock-afu/bringup/src and must be shipped for FFDC gathering
ifeq ($(UNAME),AIX) # need to have a valid ffdc mechanism for AIX...
else #Linux only

test: ${TESTDIR}/mmio ${TESTDIR}/flashgt_vpd_access

${TESTDIR}/mmio:
	mkdir -p ${TESTDIR}
	gcc -I . -lpthread -o ${TESTDIR}/mmio -O0 mmio.c

${TESTDIR}/flashgt_vpd_access:
	mkdir -p ${TESTDIR}
	gcc -I . -o ${TESTDIR}/flashgt_vpd_access -std=c99 flashgt_vpd_access.c
endif
