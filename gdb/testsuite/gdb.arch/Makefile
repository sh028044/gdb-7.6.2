
srcdir = .

EXECUTABLES = altivec-abi altivec-regs amd64-byte amd64-disp-step amd64-dword \
	amd64-entry-value amd64-i386-address amd64-word i386-bp_permanent \
	i386-permbkpt i386-avx i386-signal i386-sse

all info install-info dvi install uninstall installcheck check:
	@echo "Nothing to be done for $@..."

clean mostlyclean:
	-rm -f *~ *.o a.out *.x *.ci *.tmp gcore.test system-gcore
	-rm -f core core.coremaker coremaker.core corefile $(EXECUTABLES)
	-rm -f *.dwo *.dwp

distclean maintainer-clean realclean: clean
	-rm -f *~ core
	-rm -f Makefile config.status config.log
	-rm -f *-init.exp gdb.log gdb.sum
	-rm -fr *.log summary detail *.plog *.sum *.psum site.*
