## Process this file with automake to produce Makefile.in

libgimpui = $(top_builddir)/libgimp/libgimpui-$(GIMP_API_VERSION).la
libgimpconfig = $(top_builddir)/libgimpconfig/libgimpconfig-$(GIMP_API_VERSION).la
libgimpwidgets = $(top_builddir)/libgimpwidgets/libgimpwidgets-$(GIMP_API_VERSION).la
libgimp = $(top_builddir)/libgimp/libgimp-$(GIMP_API_VERSION).la
libgimpcolor = $(top_builddir)/libgimpcolor/libgimpcolor-$(GIMP_API_VERSION).la
libgimpmath = $(top_builddir)/libgimpmath/libgimpmath-$(GIMP_API_VERSION).la
libgimpbase = $(top_builddir)/libgimpbase/libgimpbase-$(GIMP_API_VERSION).la

if OS_WIN32
mwindows = -mwindows
endif

if HAVE_WINDRES
include $(top_srcdir)/build/windows/gimprc-plug-ins.rule
file_icns_RC = file-icns.rc.o
endif

AM_LDFLAGS = $(mwindows)

libexecdir = $(gimpplugindir)/plug-ins/file-icns

libexec_PROGRAMS = file-icns

file_icns_CFLAGS = $(PNG_CFLAGS)

file_icns_SOURCES = \
	file-icns-data.c	\
	file-icns-data.h	\
	file-icns-load.c	\
	file-icns-load.h	\
	file-icns-save.c	\
	file-icns-save.h	\
	file-icns.c	\
	file-icns.h

AM_CPPFLAGS = \
	-I$(top_srcdir)	\
	$(GTK_CFLAGS)	\
	$(GEGL_CFLAGS) \
	-I$(includedir)

LDADD = \
	$(libgimpui)		\
	$(libgimpwidgets)	\
	$(libgimpconfig)	\
	$(libgimp)		\
	$(libgimpcolor)		\
	$(libgimpmath)		\
	$(libgimpbase)		\
	$(GTK_LIBS)             \
	$(GEGL_LIBS)		\
	$(PNG_LIBS)		\
	$(RT_LIBS)		\
	$(INTLLIBS)		\
	$(file_icns_RC)
