installdir = $(pkgdatadir)/display/skin_default

if HAVE_COLORLCD
dist_install_DATA = skin_display96.xml
else
if HAVE_COLORLCD220
SUBDIRS = display220
endif
if ET10000
dist_install_DATA = skin_display.xml
else
DISPLAYTYPE = display
endif
endif

# Use box-specific XML if it exists, otherwise get the default
# TEXTSKIN is either "default" or "7segment"
# TODO: Missing dependency on optional "skin_$(DISPLAYTYPE)_$(BOXTYPE).xml"
skin_display.xml:
	test -f $(srcdir)/skin_display_$(BOXTYPE).xml && cp $(srcdir)/skin_$(DISPLAYTYPE)_$(BOXTYPE).xml $@ 2>/dev/null || cp $(srcdir)/skin_$(DISPLAYTYPE)_default.xml $@
