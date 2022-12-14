## Process this file with automake to produce Makefile.in

AM_CPPFLAGS = \
	-DG_LOG_DOMAIN=\"Gimp-Plug-In\"	\
	-I$(top_builddir)		\
	-I$(top_srcdir)			\
	-I$(top_builddir)/app		\
	-I$(top_srcdir)/app		\
	$(CAIRO_CFLAGS)			\
	$(GEGL_CFLAGS)			\
	$(GDK_PIXBUF_CFLAGS)		\
	-I$(includedir)

noinst_LIBRARIES = libappplug-in.a

libappplug_in_a_SOURCES = \
	plug-in-enums.c 			\
	plug-in-enums.h 			\
	plug-in-types.h 			\
	\
	gimpenvirontable.c			\
	gimpenvirontable.h			\
	gimpgpparams.c				\
	gimpinterpreterdb.c			\
	gimpinterpreterdb.h			\
	gimpplugindebug.c			\
	gimpplugindebug.h			\
	gimpplugin.c				\
	gimpplugin.h				\
	gimpplugin-cleanup.c			\
	gimpplugin-cleanup.h			\
	gimpplugin-context.c			\
	gimpplugin-context.h			\
	gimpplugin-message.c			\
	gimpplugin-message.h			\
	gimpplugin-proc.c			\
	gimpplugin-proc.h			\
	gimpplugin-progress.c			\
	gimpplugin-progress.h			\
	gimpplugindef.c				\
	gimpplugindef.h				\
	gimppluginerror.c 			\
	gimppluginerror.h 			\
	gimppluginmanager.c			\
	gimppluginmanager.h			\
	gimppluginmanager-call.c		\
	gimppluginmanager-call.h		\
	gimppluginmanager-data.c		\
	gimppluginmanager-data.h		\
	gimppluginmanager-file.c		\
	gimppluginmanager-file.h		\
	gimppluginmanager-help-domain.c		\
	gimppluginmanager-help-domain.h		\
	gimppluginmanager-menu-branch.c		\
	gimppluginmanager-menu-branch.h		\
	gimppluginmanager-query.c		\
	gimppluginmanager-query.h		\
	gimppluginmanager-restore.c		\
	gimppluginmanager-restore.h		\
	gimppluginprocedure.c			\
	gimppluginprocedure.h			\
	gimppluginprocframe.c			\
	gimppluginprocframe.h			\
	gimppluginshm.c				\
	gimppluginshm.h				\
	gimptemporaryprocedure.c		\
	gimptemporaryprocedure.h		\
	\
	plug-in-menu-path.c			\
	plug-in-menu-path.h			\
	plug-in-rc.c				\
	plug-in-rc.h

#
# rules to generate built sources
#
# setup autogeneration dependencies
gen_sources = stamp-plug-in-enums.h xgen-pec
CLEANFILES = $(EXTRA_PROGRAMS) $(gen_sources)

xgen-pec: $(srcdir)/plug-in-enums.h $(GIMP_MKENUMS) Makefile.am
	$(AM_V_GEN) $(GIMP_MKENUMS) \
		--fhead "#include \"stamp-plug-in-enums.h\"\n#include \"config.h\"\n#include <gio/gio.h>\n#include \"libgimpbase/gimpbase.h\"\n#include \"plug-in-enums.h\"\n#include \"gimp-intl.h\"" \
		--fprod "\n/* enumerations from \"@basename@\" */" \
		--vhead "GType\n@enum_name@_get_type (void)\n{\n  static const G@Type@Value values[] =\n  {" \
		--vprod "    { @VALUENAME@, \"@VALUENAME@\", \"@valuenick@\" }," \
		--vtail "    { 0, NULL, NULL }\n  };\n" \
		--dhead "  static const Gimp@Type@Desc descs[] =\n  {" \
		--dprod "    { @VALUENAME@, @valuedesc@, @valuehelp@ },@if ('@valueabbrev@' ne 'NULL')@\n    /* Translators: this is an abbreviated version of @valueudesc@.\n       Keep it short. */\n    { @VALUENAME@, @valueabbrev@, NULL },@endif@" \
		--dtail "    { 0, NULL, NULL }\n  };\n\n  static GType type = 0;\n\n  if (G_UNLIKELY (! type))\n    {\n      type = g_@type@_register_static (\"@EnumName@\", values);\n      gimp_type_set_translation_context (type, \"@enumnick@\");\n      gimp_@type@_set_value_descriptions (type, descs);\n    }\n\n  return type;\n}\n" \
		$< > $@

stamp-plug-in-enums.h: xgen-pec
	echo "/* Generated on `date`. */" > $@

# copy the generated enum file back to the source directory only if it's
# changed; otherwise, only update its timestamp, so that the recipe isn't
# executed again on the next build, however, allow this to (harmlessly) fail,
# to support building from a read-only source tree.
$(srcdir)/plug-in-enums.c: xgen-pec stamp-plug-in-enums.h
	$(AM_V_GEN) if ! cmp -s $< $@; then \
		cp $< $@; \
	else \
		touch $@ 2> /dev/null \
		|| true; \
	fi
