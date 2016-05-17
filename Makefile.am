## Process this file with automake to produce Makefile.in

NULL =

CFLAGS += -Wall -Werror

ACLOCAL_AMFLAGS = -I m4

sbin_PROGRAMS = nodm

dist_noinst_HEADERS = common.h 		\
                      dm.h		\
                      log.h		\
                      test.h		\
                      vt.h		\
                      xserver.h		\
                      xsession.h	\
                      xsession-child.h	\
                      $(NULL)

libsources = common.c 			\
             log.c			\
             vt.c			\
             xsession-child.c		\
             xserver.c			\
             xsession.c dm.c		\
             $(NULL)

testlibsources = $(libsources)		\
                 test.c			\
                 $(NULL)

AM_CPPFLAGS = $(X11_CFLAGS)
LIBS = $(PAM_LIBS) $(X11_LIBS)

nodm_SOURCES = $(libsources)		\
               nodm.c			\
               $(NULL)

nodm_CFLAGS = -DNODM_SESSION='"$(sbindir)/nodm"'

TESTS = test-internals test-xstart test-xsession
check_PROGRAMS = test-internals test-xstart test-xsession

test_xstart_SOURCES = $(testlibsources)		\
                      test-xstart.c		\
                      $(NULL)

test_xsession_SOURCES = $(testlibsources) 	\
                        test-xsession.c		\
                        $(NULL)

test_internals_SOURCES = $(testlibsources)	\
                         test-internals.c	\
                         $(NULL)

EXTRA_DIST = test_nodm		\
             autogen.sh		\
             $(NULL)

CLEANFILES = nodm.8

DISTCLEANFILES = Makefile.in   \
                 aclocal.m4    \
                 config.h.in   \
                 config/*      \
                 configure     \
                 $(NULL)
