
srcdir = .

EXECUTABLES = abstract-origin ambiguous annota2 annota3 anon-union \
	arg-reference bool breakpoint bs15503 call-c casts class2 \
	classes converts cpexprs cplusfuncs cttiadd derivation \
	exception expand-sals extern-c formatted-ref fpointer gdb1355 \
	gdb2384 hang infcall-dlopen inherit koenig local m-data m-static \
	mb-ctor mb-inline mb-templates member-ptr method misc namespace \
	namespace-enum namespace-nested-import nextoverthrow noparam nsdecl \
	nsimport nsnested nsnoimports nsrecurs nsstress nsusing operator \
	oranking overload overload-const ovldbreak pass-by-ref pr-1023 pr-1210 \
	pr-574 pr10728 pr12028 pr9631 printmethod psmang ptype-cv-cp \
	re-set-overloaded ref-typ ref-typ2 rtti shadow smartp temargs \
	templates try_catch typedef-operator userdef virtbase virtfunc \
	ref-types ref-params method2 pr9594 gdb2495 virtfunc2 pr9067 \
	pr1072 pr10687 pr9167

all info install-info dvi install uninstall installcheck check:
	@echo "Nothing to be done for $@..."

clean mostlyclean:
	-rm -f *~ *.o *.ci
	-rm -f *.dwo *.dwp
	-rm -f core ${EXECUTABLES}

distclean maintainer-clean realclean: clean
	-rm -f Makefile config.status config.log gdb.log gdb.sum
