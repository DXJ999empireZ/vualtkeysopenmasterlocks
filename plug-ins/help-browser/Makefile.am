## Process this file with automake to produce Makefile.in

libgimp = $(top_builddir)/libgimp/libgimp-$(GIMP_API_VERSION).la
libgimpbase = $(top_builddir)/libgimpbase/libgimpbase-$(GIMP_API_VERSION).la
libgimpcolor = $(top_builddir)/libgimpcolor/libgimpcolor-$(GIMP_API_VERSION).la
libgimpconfig = $(top_builddir)/libgimpconfig/libgimpconfig-$(GIMP_API_VERSION).la
libgimpmath = $(top_builddir)/libgimpmath/libgimpmath-$(GIMP_API_VERSION).la
libgimpui = $(top_builddir)/libgimp/libgimpui-$(GIMP_API_VERSION).la
libgimpwidgets = $(top_builddir)/libgimpwidgets/libgimpwidgets-$(GIMP_API_VERSION).la

libgimphelp = $(top_builddir)/plug-ins/help/libgimphelp.a

if OS_WIN32
mwindows = -mwindows
endif

if HAVE_WINDRES
include $(top_srcdir)/build/windows/gimprc-plug-ins.rule
help_browser_RC = help-browser.rc.o
endif

AM_LDFLAGS = $(mwindows)

libexecdir = $(gimpplugindir)/plug-ins/help-browser

libexec_PROGRAMS = help-browser

AM_CPPFLAGS = \
	-I$(top_srcdir)		\
	$(WEBKIT_CFLAGS)	\
	$(GEGL_CFLAGS) \
	-I$(includedir)

LDADD = \
	$(libgimphelp)		\
	$(libgimpui)		\
	$(libgimpwidgets)	\
	$(libgimpconfig)	\
	$(libgimp)		\
	$(libgimpcolor)		\
	$(libgimpmath)		\
	$(libgimpbase)		\
	$(WEBKIT_LIBS)		\
	$(GIO_LIBS)		\
	$(GLIB_LIBS)		\
	$(RT_LIBS)		\
	$(INTLLIBS)		\
	$(help_browser_RC)

help_browser_SOURCES = \
	help-browser.c		\
	dialog.c		\
	dialog.h		\
	uri.c			\
	uri.h
