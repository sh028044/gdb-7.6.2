
srcdir = .

EXECUTABLES = hello/hello 

MISCELLANEOUS =

all info install-info dvi install uninstall installcheck check:
	@echo "Nothing to be done for $@..."

clean mostlyclean:
	-find . -name '*.o' -print | xargs rm -f
	-find . -name '*.ali' -print | xargs rm -f
	-find . -name 'b~*.ad[sb]' -print | xargs rm -f
	-rm -f *~ a.out xgdb *.x *.ci *.tmp
	-rm -f *~ *.o a.out xgdb *.x *.ci *.tmp
	-rm -f *.dwo *.dwp
	-rm -f core core.coremaker coremaker.core corefile $(EXECUTABLES)
	-rm -f $(MISCELLANEOUS) twice-tmp.c

distclean maintainer-clean realclean: clean
	-rm -f *~ core
	-rm -f Makefile config.status config.log
	-rm -f *-init.exp gdb.log gdb.sum
	-rm -fr *.log summary detail *.plog *.sum *.psum site.*
