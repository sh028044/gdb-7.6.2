
srcdir = .

EXECUTABLES   = break-reverse consecutive-reverse finish-reverse \
	i386-precsave i386-reverse i386-sse-reverse \
	machinestate solib-reverse step-reverse until-reverse \
	watch-reverse sigall-reverse sigall-precsave

MISCELLANEOUS = 

all info install-info dvi install uninstall installcheck check:
	@echo "Nothing to be done for $@..."

clean mostlyclean:
	rm -f *~ *.o *.x *.ci *.sl a.out core
	rm -f *.dwo *.dwp
	rm -f $(EXECUTABLES) $(MISCELLANEOUS)

distclean maintainer-clean realclean: clean
	rm -f Makefile config.status config.log site.* gdb.log gdb.sum

