srcdir = .


all info install-info dvi install uninstall installcheck check:
	@echo "Nothing to be done for $@..."

.SUFFIXES: .java .class .o .exe .exp .check

# Do 'make javamisc.check' to run just the javamisc.exp test.

.exp.check:
	rootme=`pwd`/; export rootme; \
	cd .. ; \
	$(MAKE) just-check RUNTESTFLAGS="${RUNTESTFLAGS} $*.exp" \
	  EXPECT=${EXPECT}

clean mostlyclean:
	-rm -f *.o ${OBJS}  *.class *.exe *~ core jmain jmisc jnpe jprint
	-rm -f *.dwo *.dwp

distclean maintainer-clean realclean: clean
	-rm -f Makefile config.status config.log gdb.log gdb.sum
