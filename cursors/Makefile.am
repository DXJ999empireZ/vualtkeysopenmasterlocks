## Process this file with automake to produce Makefile.in

CURSOR_IMAGES = \
	cursor-bad.png				\
	cursor-bad-x2.png			\
	cursor-color-picker.png			\
	cursor-color-picker-x2.png		\
	cursor-corner-bottom-left.png		\
	cursor-corner-bottom-left-x2.png	\
	cursor-corner-bottom-right.png		\
	cursor-corner-bottom-right-x2.png	\
	cursor-corner-bottom.png		\
	cursor-corner-bottom-x2.png		\
	cursor-corner-left.png			\
	cursor-corner-left-x2.png		\
	cursor-corner-right.png			\
	cursor-corner-right-x2.png		\
	cursor-corner-top-left.png		\
	cursor-corner-top-left-x2.png		\
	cursor-corner-top-right.png		\
	cursor-corner-top-right-x2.png		\
	cursor-corner-top.png			\
	cursor-corner-top-x2.png		\
	cursor-crosshair-small.png		\
	cursor-crosshair-small-x2.png		\
	cursor-crosshair.png			\
	cursor-crosshair-x2.png			\
	cursor-mouse.png			\
	cursor-mouse-x2.png			\
	cursor-move.png				\
	cursor-move-x2.png			\
	cursor-none.png				\
	cursor-none-x2.png			\
	cursor-side-bottom-left.png		\
	cursor-side-bottom-left-x2.png		\
	cursor-side-bottom-right.png		\
	cursor-side-bottom-right-x2.png		\
	cursor-side-bottom.png			\
	cursor-side-bottom-x2.png		\
	cursor-side-left.png			\
	cursor-side-left-x2.png			\
	cursor-side-right.png			\
	cursor-side-right-x2.png		\
	cursor-side-top-left.png		\
	cursor-side-top-left-x2.png		\
	cursor-side-top-right.png		\
	cursor-side-top-right-x2.png		\
	cursor-side-top.png			\
	cursor-side-top-x2.png			\
	cursor-single-dot.png			\
	cursor-single-dot-x2.png		\
	cursor-zoom.png				\
	cursor-zoom-x2.png			\
	\
	modifier-anchor.png			\
	modifier-anchor-x2.png			\
	modifier-background.png			\
	modifier-background-x2.png		\
	modifier-bad.png			\
	modifier-bad-x2.png			\
	modifier-control.png			\
	modifier-control-x2.png			\
	modifier-foreground.png			\
	modifier-foreground-x2.png		\
	modifier-intersect.png			\
	modifier-intersect-x2.png		\
	modifier-join.png			\
	modifier-join-x2.png			\
	modifier-minus.png			\
	modifier-minus-x2.png			\
	modifier-move.png			\
	modifier-move-x2.png			\
	modifier-pattern.png			\
	modifier-pattern-x2.png			\
	modifier-plus.png			\
	modifier-plus-x2.png			\
	modifier-resize.png			\
	modifier-resize-x2.png			\
	modifier-rotate.png			\
	modifier-rotate-x2.png			\
	modifier-select.png			\
	modifier-select-x2.png			\
	modifier-zoom.png			\
	modifier-zoom-x2.png			\
	\
	tool-airbrush.png			\
	tool-airbrush-x2.png			\
	tool-blur.png				\
	tool-blur-x2.png			\
	tool-bucket-fill.png			\
	tool-bucket-fill-x2.png			\
	tool-burn.png				\
	tool-burn-x2.png			\
	tool-clone.png				\
	tool-clone-x2.png			\
	tool-color-picker.png			\
	tool-color-picker-x2.png		\
	tool-crop.png				\
	tool-crop-x2.png			\
	tool-dodge.png				\
	tool-dodge-x2.png			\
	tool-ellipse-select.png			\
	tool-ellipse-select-x2.png		\
	tool-eraser.png				\
	tool-eraser-x2.png			\
	tool-flip-horizontal.png		\
	tool-flip-horizontal-x2.png		\
	tool-flip-vertical.png			\
	tool-flip-vertical-x2.png		\
	tool-free-select.png			\
	tool-free-select-x2.png			\
	tool-fuzzy-select.png			\
	tool-fuzzy-select-x2.png		\
	tool-gradient.png			\
	tool-gradient-x2.png			\
	tool-hand.png				\
	tool-hand-x2.png			\
	tool-heal.png				\
	tool-heal-x2.png			\
	tool-ink.png				\
	tool-ink-x2.png				\
	tool-iscissors.png			\
	tool-iscissors-x2.png			\
	tool-measure.png			\
	tool-measure-x2.png			\
	tool-move.png				\
	tool-move-x2.png			\
	tool-paintbrush.png			\
	tool-paintbrush-x2.png			\
	tool-paths-anchor.png			\
	tool-paths-anchor-x2.png		\
	tool-paths-control.png			\
	tool-paths-control-x2.png		\
	tool-paths-segment.png			\
	tool-paths-segment-x2.png		\
	tool-paths.png				\
	tool-paths-x2.png			\
	tool-pencil.png				\
	tool-pencil-x2.png			\
	tool-perspective.png			\
	tool-perspective-x2.png			\
	tool-polygon-select.png			\
	tool-polygon-select-x2.png		\
	tool-rect-select.png			\
	tool-rect-select-x2.png			\
	tool-resize.png				\
	tool-resize-x2.png			\
	tool-rotate.png				\
	tool-rotate-x2.png			\
	tool-shear.png				\
	tool-shear-x2.png			\
	tool-smudge.png				\
	tool-smudge-x2.png			\
	tool-text.png				\
	tool-text-x2.png			\
	tool-transform-3d-camera.png		\
	tool-transform-3d-camera-x2.png		\
	tool-warp.png				\
	tool-warp-x2.png			\
	tool-zoom.png				\
	tool-zoom-x2.png

COLOR_PICKER_IMAGES = \
	cursor-color-picker.png			\
	cursor-color-picker-x2.png

EXTRA_DIST = \
	$(CURSOR_IMAGES)			\
	gimp-tool-cursors.xcf			\
	gimp-tool-cursors-x2.xcf

noinst_DATA = \
	gimp-tool-cursors.gresource.xml		\
	gimp-color-picker-cursors.gresource.xml

CLEANFILES = $(noinst_DATA)


gimp-tool-cursors.gresource.xml: $(CURSOR_IMAGES) Makefile.am
	$(AM_V_GEN) ( rm -f $@; \
	  echo '<?xml version="1.0" encoding="UTF-8"?>' > $@; \
	  echo '<gresources>' >> $@; \
	  echo '  <gresource prefix="/org/gimp/tool-cursors">' >> $@; \
	  for image in $(CURSOR_IMAGES); do \
	    echo "    <file preprocess=\"to-pixdata\">$$image</file>" >> $@; \
	  done; \
	  echo '  </gresource>' >> $@; \
	  echo '</gresources>' >> $@ )

gimp-color-picker-cursors.gresource.xml: $(CURSOR_IMAGES) Makefile.am
	$(AM_V_GEN) ( rm -f $@; \
	  echo '<?xml version="1.0" encoding="UTF-8"?>' > $@; \
	  echo '<gresources>' >> $@; \
	  echo '  <gresource prefix="/org/gimp/color-picker-cursors">' >> $@; \
	  for image in $(COLOR_PICKER_IMAGES); do \
	    echo "    <file preprocess=\"to-pixdata\">$$image</file>" >> $@; \
	  done; \
	  echo '  </gresource>' >> $@; \
	  echo '  <gresource prefix="/org/gimp/color-picker-cursors-raw">' >> $@; \
	  for image in $(COLOR_PICKER_IMAGES); do \
	    echo "    <file>$$image</file>" >> $@; \
	  done; \
	  echo '  </gresource>' >> $@; \
	  echo '</gresources>' >> $@ )
