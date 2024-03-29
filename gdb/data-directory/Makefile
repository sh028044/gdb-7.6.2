# Copyright (C) 2010-2013 Free Software Foundation, Inc.

# Makefile for building a staged copy of the data-directory.
# This file is part of GDB.

# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 3 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program.  If not, see <http://www.gnu.org/licenses/>.

srcdir = .
SYSCALLS_SRCDIR = $(srcdir)/../syscalls
PYTHON_SRCDIR = $(srcdir)/../python/lib
VPATH = $(SYSCALLS_SRCDIR):$(PYTHON_SRCDIR)

top_srcdir = ..
top_builddir = ..

prefix = /usr/local
exec_prefix = ${prefix}

datarootdir = ${prefix}/share
datadir = ${datarootdir}

SHELL = /bin/sh

LN_S = ln -s

INSTALL = /usr/bin/install -c
INSTALL_DATA = /usr/bin/install -c -m 644
INSTALL_DIR = $(SHELL) $(srcdir)/../../mkinstalldirs

GDB_DATADIR = ${datarootdir}/gdb

SYSCALLS_DIR = syscalls
SYSCALLS_INSTALL_DIR = $(DESTDIR)$(GDB_DATADIR)/$(SYSCALLS_DIR)
SYSCALLS_FILES = \
	gdb-syscalls.dtd \
	ppc-linux.xml ppc64-linux.xml \
	i386-linux.xml amd64-linux.xml \
	sparc-linux.xml sparc64-linux.xml \
	mips-o32-linux.xml mips-n32-linux.xml mips-n64-linux.xml

PYTHON_DIR = python
PYTHON_INSTALL_DIR = $(DESTDIR)$(GDB_DATADIR)/$(PYTHON_DIR)
PYTHON_FILES = \
	gdb/__init__.py \
	gdb/types.py \
	gdb/printing.py \
	gdb/prompt.py \
	gdb/command/__init__.py \
	gdb/command/type_printers.py \
	gdb/command/pretty_printers.py \
	gdb/command/prompt.py \
	gdb/command/explore.py \
	gdb/function/__init__.py \
	gdb/function/strfns.py

FLAGS_TO_PASS = \
	"prefix=$(prefix)" \
	"exec_prefix=$(exec_prefix)" \
	"infodir=$(infodir)" \
	"datarootdir=$(datarootdir)" \
	"docdir=$(docdir)" \
	"htmldir=$(htmldir)" \
	"pdfdir=$(pdfdir)" \
	"libdir=$(libdir)" \
	"mandir=$(mandir)" \
	"datadir=$(datadir)" \
	"includedir=$(includedir)" \
	"against=$(against)" \
	"DESTDIR=$(DESTDIR)" \
	"AR=$(AR)" \
	"AR_FLAGS=$(AR_FLAGS)" \
	"CC=$(CC)" \
	"CFLAGS=$(CFLAGS)" \
	"CXX=$(CXX)" \
	"CXXFLAGS=$(CXXFLAGS)" \
	"DLLTOOL=$(DLLTOOL)" \
	"LDFLAGS=$(LDFLAGS)" \
	"RANLIB=$(RANLIB)" \
	"MAKEINFO=$(MAKEINFO)" \
	"MAKEHTML=$(MAKEHTML)" \
	"MAKEHTMLFLAGS=$(MAKEHTMLFLAGS)" \
	"INSTALL=$(INSTALL)" \
	"INSTALL_PROGRAM=$(INSTALL_PROGRAM)" \
	"INSTALL_DATA=$(INSTALL_DATA)" \
	"RUNTEST=$(RUNTEST)" \
	"RUNTESTFLAGS=$(RUNTESTFLAGS)"

.PHONY: all
all: stamp-syscalls stamp-python

# For portability's sake, we need to handle systems that don't have
# symbolic links.
stamp-syscalls: Makefile $(SYSCALLS_FILES)
	rm -rf ./$(SYSCALLS_DIR)
	mkdir ./$(SYSCALLS_DIR)
	files='$(SYSCALLS_FILES)' ; \
	for file in $$files ; do \
	  f=$(SYSCALLS_SRCDIR)/$$file ; \
	  if test -f $$f ; then \
	    $(INSTALL_DATA) $$f ./$(SYSCALLS_DIR) ; \
	  fi ; \
	done
	touch $@

.PHONY: clean-syscalls
clean-syscalls:
	rm -rf $(SYSCALLS_DIR)
	rm -f stamp-syscalls

# This target is responsible for properly installing the syscalls'
# XML files in the system.
.PHONY: install-syscalls
install-syscalls:
	$(INSTALL_DIR) $(SYSCALLS_INSTALL_DIR)
	files='$(SYSCALLS_FILES)' ; \
	for file in $$files; do \
	  f=$(SYSCALLS_SRCDIR)/$$file ; \
	  if test -f $$f ; then \
	    $(INSTALL_DATA) $$f $(SYSCALLS_INSTALL_DIR) ; \
	  fi ; \
	done

.PHONY: uninstall-syscalls
uninstall-syscalls:
	files='$(SYSCALLS_FILES)' ; \
	for file in $$files ; do \
	  slashdir=`echo "/$$file" | sed 's,/[^/]*$$,,'` ; \
	  rm -f $(SYSCALLS_INSTALL_DIR)/$$file ; \
	  while test "x$$file" != "x$$slashdir" ; do \
	    rmdir 2>/dev/null "$(SYSCALLS_INSTALL_DIR)$$slashdir" ; \
	    file="$$slashdir" ; \
	    slashdir=`echo "$$file" | sed 's,/[^/]*$$,,'` ; \
	  done \
	done

stamp-python: Makefile $(PYTHON_FILES)
	rm -rf ./$(PYTHON_DIR)
	files='$(PYTHON_FILES)' ; \
	for file in $$files ; do \
	  dir=`echo "$$file" | sed 's,/[^/]*$$,,'` ; \
	  $(INSTALL_DIR) ./$(PYTHON_DIR)/$$dir ; \
	  $(INSTALL_DATA) $(PYTHON_SRCDIR)/$$file ./$(PYTHON_DIR)/$$dir ; \
	done
	touch $@

.PHONY: clean-python
clean-python:
	rm -rf $(PYTHON_DIR)
	rm -f stamp-python

.PHONY: install-python
install-python:
	files='$(PYTHON_FILES)' ; \
	for file in $$files ; do \
	  dir=`echo "$$file" | sed 's,/[^/]*$$,,'` ; \
	  $(INSTALL_DIR) $(PYTHON_INSTALL_DIR)/$$dir ; \
	  $(INSTALL_DATA) ./$(PYTHON_DIR)/$$file $(PYTHON_INSTALL_DIR)/$$dir ; \
	done

.PHONY: uninstall-python
uninstall-python:
	files='$(PYTHON_FILES)' ; \
	for file in $$files ; do \
	  slashdir=`echo "/$$file" | sed 's,/[^/]*$$,,'` ; \
	  rm -f $(PYTHON_INSTALL_DIR)/$$file ; \
	  while test "x$$file" != "x$$slashdir" ; do \
	    rmdir 2>/dev/null "$(PYTHON_INSTALL_DIR)$$slashdir" ; \
	    file="$$slashdir" ; \
	    slashdir=`echo "$$file" | sed 's,/[^/]*$$,,'` ; \
	  done \
	done

# Traditionally "install" depends on "all".  But it may be useful
# not to; for example, if the user has made some trivial change to a
# source file and doesn't care about rebuilding or just wants to save the
# time it takes for make to check that all is up to date.
# install-only is intended to address that need.
.PHONY: install
install: all
	@$(MAKE) $(FLAGS_TO_PASS) install-only

.PHONY: install-only
install-only: install-syscalls install-python

.PHONY: uninstall
uninstall: uninstall-syscalls uninstall-python

.PHONY: clean
clean: clean-syscalls clean-python

.PHONY: maintainer-clean realclean distclean
maintainer-clean realclean distclean: clean
	rm -f Makefile

.PHONY: check installcheck info dvi pdf html
.PHONY: install-info install-pdf install-html clean-info
check installcheck:
info dvi pdf html:
install-info install-pdf install-html:
clean-info:

# GNU Make has an annoying habit of putting *all* the Makefile variables
# into the environment, unless you include this target as a circumvention.
# Rumor is that this will be fixed (and this target can be removed)
# in GNU Make 4.0.
.NOEXPORT:

# GNU Make 3.63 has a different problem: it keeps tacking command line
# overrides onto the definition of $(MAKE).  This variable setting
# will remove them.
MAKEOVERRIDES=

Makefile: $(srcdir)/Makefile.in $(top_builddir)/config.status
	cd $(top_builddir) && $(MAKE) data-directory/Makefile
