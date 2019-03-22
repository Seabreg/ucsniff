
# $Id: Makefile.am,v 1.22 2004/09/02 13:17:35 alor Exp $

include $(top_srcdir)/Makefile.am.common

AUTOMAKE_OPTIONS = subdir-objects

ACLOCAL_AMFLAGS = -I libltdl/m4

SUBDIRS = man share include include src

if PLUGINS
   SUBDIRS += plug-ins
endif


EXTRA_DIST = AUTHORS \
             CHANGELOG \
             LICENSE \
             README \
             README.BINARIES \
             README.BUGS \
             README.CVS \
             README.PLATFORMS \
             THANKS \
             TODO \
             TODO.TESTING \
             Makefile.am.common \
             Makefile.mingw.in \
             shtool \
             contrib/* \
             doc/*

CLEANFILES = -R auto4te.cache *~ *.log *.out *.cache *.so ucsniff

dist-hook:
	rm -rf `find $(distdir)/doc -name CVS`
	rm -rf `find $(distdir)/contrib -name CVS`
	cat $(distdir)/Makefile.am.common | sed s/#no/no/g > $(distdir)/Makefile.am.common

test: all
	rm -f ucsniff *.so
	ln -fs ./src/ucsniff ./
	ln -fs ./utils/etterlog/etterlog ./
	ln -fs ./utils/etterfilter/etterfilter ./
	find ./plug-ins -name '*.so' -exec ln -fs {} ./ \;
	./shtool fixperm ./

# vim:ts=4:noexpandtab

