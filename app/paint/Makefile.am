## Process this file with automake to produce Makefile.in

AM_CPPFLAGS = \
	-DG_LOG_DOMAIN=\"Gimp-Paint\"		\
	-I$(top_builddir)			\
	-I$(top_srcdir)				\
	-I$(top_builddir)/app			\
	-I$(top_srcdir)/app			\
	$(CAIRO_CFLAGS)				\
	$(GEGL_CFLAGS)				\
	$(GDK_PIXBUF_CFLAGS)			\
	$(LIBMYPAINT_CFLAGS)		\
	-I$(includedir)

noinst_LIBRARIES = libapppaint.a

libapppaint_a_sources = \
	paint-enums.h			\
	paint-types.h			\
	gimp-paint.c			\
	gimp-paint.h			\
	gimpairbrush.c			\
	gimpairbrush.h			\
	gimpairbrushoptions.c		\
	gimpairbrushoptions.h		\
	gimpbrushcore.c			\
	gimpbrushcore.h			\
	gimpbrushcore-loops.cc		\
	gimpbrushcore-loops.h		\
	gimpbrushcore-kernels.h		\
	gimpclone.c			\
	gimpclone.h			\
	gimpcloneoptions.c		\
	gimpcloneoptions.h		\
	gimpconvolve.c			\
	gimpconvolve.h			\
	gimpconvolveoptions.c		\
	gimpconvolveoptions.h		\
	gimpdodgeburn.c			\
	gimpdodgeburn.h			\
	gimpdodgeburnoptions.c		\
	gimpdodgeburnoptions.h		\
	gimperaser.c			\
	gimperaser.h			\
	gimperaseroptions.c		\
	gimperaseroptions.h		\
	gimpheal.c			\
	gimpheal.h			\
	gimpink.c			\
	gimpink.h			\
	gimpink-blob.c			\
	gimpink-blob.h			\
	gimpinkoptions.c		\
	gimpinkoptions.h		\
	gimpinkundo.c			\
	gimpinkundo.h			\
	gimpmybrushcore.c		\
	gimpmybrushcore.h		\
	gimpmybrushoptions.c		\
	gimpmybrushoptions.h		\
	gimpmybrushsurface.c		\
	gimpmybrushsurface.h		\
	gimppaintcore.c			\
	gimppaintcore.h			\
	gimppaintcore-loops.cc		\
	gimppaintcore-loops.h		\
	gimppaintcore-stroke.c		\
	gimppaintcore-stroke.h		\
	gimppaintcoreundo.c		\
	gimppaintcoreundo.h		\
	gimppaintoptions.c		\
	gimppaintoptions.h		\
	gimppencil.c			\
	gimppencil.h			\
	gimppenciloptions.c		\
	gimppenciloptions.h		\
	gimppaintbrush.c		\
	gimppaintbrush.h		\
	gimpperspectiveclone.c		\
	gimpperspectiveclone.h		\
	gimpperspectivecloneoptions.c	\
	gimpperspectivecloneoptions.h	\
	gimpsmudge.c			\
	gimpsmudge.h			\
	gimpsmudgeoptions.c		\
	gimpsmudgeoptions.h		\
	gimpsourcecore.c		\
	gimpsourcecore.h		\
	gimpsourceoptions.c		\
	gimpsourceoptions.h

libapppaint_a_built_sources = paint-enums.c

libapppaint_a_SOURCES = $(libapppaint_a_built_sources) $(libapppaint_a_sources)

#
# rules to generate built sources
#
# setup autogeneration dependencies
gen_sources = stamp-paint-enums.h xgen-pec
CLEANFILES = $(gen_sources)

xgen-pec: $(srcdir)/paint-enums.h $(GIMP_MKENUMS) Makefile.am
	$(AM_V_GEN) $(GIMP_MKENUMS) \
		--fhead "#include \"stamp-paint-enums.h\"\n#include \"config.h\"\n#include <gio/gio.h>\n#include \"libgimpbase/gimpbase.h\"\n#include \"paint-enums.h\"\n#include \"gimp-intl.h\"" \
		--fprod "\n/* enumerations from \"@basename@\" */" \
		--vhead "GType\n@enum_name@_get_type (void)\n{\n  static const G@Type@Value values[] =\n  {" \
		--vprod "    { @VALUENAME@, \"@VALUENAME@\", \"@valuenick@\" }," \
		--vtail "    { 0, NULL, NULL }\n  };\n" \
		--dhead "  static const Gimp@Type@Desc descs[] =\n  {" \
		--dprod "    { @VALUENAME@, @valuedesc@, @valuehelp@ },@if ('@valueabbrev@' ne 'NULL')@\n    /* Translators: this is an abbreviated version of @valueudesc@.\n       Keep it short. */\n    { @VALUENAME@, @valueabbrev@, NULL },@endif@" \
		--dtail "    { 0, NULL, NULL }\n  };\n\n  static GType type = 0;\n\n  if (G_UNLIKELY (! type))\n    {\n      type = g_@type@_register_static (\"@EnumName@\", values);\n      gimp_type_set_translation_context (type, \"@enumnick@\");\n      gimp_@type@_set_value_descriptions (type, descs);\n    }\n\n  return type;\n}\n" \
		$< > $@

stamp-paint-enums.h: xgen-pec
	echo "/* Generated on `date`. */" > $@

# copy the generated enum file back to the source directory only if it's
# changed; otherwise, only update its timestamp, so that the recipe isn't
# executed again on the next build, however, allow this to (harmlessly) fail,
# to support building from a read-only source tree.
$(srcdir)/paint-enums.c: xgen-pec stamp-paint-enums.h
	$(AM_V_GEN) if ! cmp -s $< $@; then \
		cp $< $@; \
	else \
		touch $@ 2> /dev/null \
		|| true; \
	fi
