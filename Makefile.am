# Copyright (C) 2003, 2007 International Business Machines and others.
# All Rights Reserved.
# This file is distributed under the Common Public License.

## $Id$

AUTOMAKE_OPTIONS = foreign

EXTRA_DIST = get.blas INSTALL.BLAS

thirdpartylibdir = $(libdir)/coin/ThirdParty
thirdpartylib_LTLIBRARIES = libcoinblas.la

libcoinblas_la_SOURCES = \
	dasum.f \
	daxpy.f \
	dcopy.f \
	ddot.f \
	dgbmv.f \
	dgemm.f \
	dgemv.f \
	dger.f \
	dnrm2.f \
	drot.f \
	drotg.f \
	drotm.f \
	drotmg.f \
	dsbmv.f \
	dscal.f \
	dsdot.f \
	dspmv.f \
	dspr2.f \
	dspr.f \
	dswap.f \
	dsymm.f \
	dsymv.f \
	dsyr2.f \
	dsyr2k.f \
	dsyr.f \
	dsyrk.f \
	dtbmv.f \
	dtbsv.f \
	dtpmv.f \
	dtpsv.f \
	dtrmm.f \
	dtrmv.f \
	dtrsm.f \
	dtrsv.f \
	idamax.f \
	lsame.f \
	xerbla.f

libcoinblas_la_LDFLAGS = $(LT_LDFLAGS)

pkgconfiglibdir = $(libdir)/pkgconfig
pkgconfiglib_DATA = coinblas.pc

if COIN_HAS_PKGCONFIG
addlibsdir = $(DESTDIR)$(datadir)/coin/doc/ThirdParty/Blas
	
install-data-hook:
	@$(mkdir_p) "$(addlibsdir)"
	PKG_CONFIG_PATH=@COIN_PKG_CONFIG_PATH@ \
	$(PKG_CONFIG) --libs coinblas > $(addlibsdir)/blas_addlibs.txt

uninstall-hook:
	rm -f $(addlibsdir)/blas_addlibs.txt
endif

test: $(libampl)
	@echo "No test available for Blas."

########################################################################
#                         Maintainer Stuff                             #
########################################################################

CLEANFILES =

# Files that are generated and should be cleaned with make distclean
DISTCLEANFILES = $(MAKEOKFILE)

include BuildTools/Makemain.inc
