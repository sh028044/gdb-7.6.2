
srcdir = .

EXECUTABLES   = enable function_call_history instruction_history

MISCELLANEOUS =

all info install-info dvi install uninstall installcheck check:
	@echo "Nothing to be done for $@..."

clean mostlyclean:
	rm -f *~ *.o *.x *.ci *.sl a.out core
	rm -f *.dwo *.dwp
	rm -f $(EXECUTABLES) $(MISCELLANEOUS)

distclean maintainer-clean realclean: clean
	rm -f Makefile config.status config.log site.* gdb.log gdb.sum
