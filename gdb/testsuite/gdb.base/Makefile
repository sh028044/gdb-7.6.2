
srcdir = .

EXECUTABLES = a2-run advance all-types annota1 annota1-watch_thread_num \
	annota3 anon args arrayidx async attach attach-pie-misread \
	attach2 auxv bang\! bfp-test bigcore bitfields bitfields2 \
	break break-always break-entry break-interp-test breako2 \
	breakpoint-shadow break-on-linker-gcd-function \
	call-ar-st call-rt-st call-sc-t* call-signals \
	call-strs callexit callfuncs callfwmall charset checkpoint \
	chng-syms code_elim1 code_elim2 commands compiler complex \
	condbreak consecutive constvars coremaker cursal cvexpr \
	dbx-test del disasm-end-cu display dprintf-pending dump dup-sect \
	dup-sect.debug \
	dup-sect.stripped ending-run execd-prog expand-psymtabs exprs \
	fileio find finish fixsection float foll-exec foll-fork foll-vfork \
	frame-args freebpcmd fullname funcargs gcore \
	gcore-buffer-overflow-012* \
	gdb1090 gdb11530 gdb11531 gdb1250 gdb1555-main gdb1821 gdbvars \
	hashline1 hashline2 hashline3 hbreak hook-stop-continue \
	hook-stop-frame huge included infnan info-target int-type \
	interrupt jit-main jump label langs lineinc list longjmp long_long \
	macscp mips_pro miscexprs moribund-step multi-forks nodebug \
	nofield nostdlib opaque overlays pc-fp pending permission \
	pie-execl1 pie-execl2 pointers pointers2 pr11022 prelinkt \
	prelinkt.debug prelinkt.stripped printcmds prologue psymtab \
	ptr-typedef ptype randomize recurse relational relativedebug \
	reread reread1 restore return return-nodebug-* return2 run \
	savedregs scope section_command sep sepdebug sepdebug.stripped \
	sepdebug2 sepdebug2.debug sepdebug2.stripped sepsymtab \
	sepsymtab.debug sepsymtab.stripped setshow setvar shmain shreloc \
	sigall sigaltstack sigbpt sigchld siginfo siginfo-addr \
	siginfo-infcall siginfo-obj signals signull sigrepeat sigstep \
	sizeof skip skip-solib solib solib-corrupted solib-display-main \
	solib-nodir solib-overlap-main-0x40000000 solib-symbol-main solib-weak \
	solib-weak-lib2 solib_sl so-impl-ld so-indr-cl \
	stack-checking start step-break step-bt step-line step-resume-infcall \
	step-test store structs-t* structs2 structs3 \
	symbol-without-target_section term tui-layout twice-tmp \
	type-opaque-main ui-redirect unload until unwindonsignal \
	valgrind-db-attach value-double-free varargs vforked-prog \
	volatile watch-cond watch-cond-infcall watch-non-mem watch-read \
	watch-vfork watch_thread_num watchpoint watchpoint-cond-gone \
	watchpoint-hw watchpoint-hw-hit-once watchpoint-solib watchpoints \
	wchar whatis whatis-exp catch-syscall \
	pr10179 gnu_vector

MISCELLANEOUS = coremmap.data dprintf-pendshr.sl ../foobar.baz fixsectshr.sl \
	pendshr.sl shreloc1.sl shreloc2.sl twice-tmp.c \
	shr1.sl shr2.sl solib_sl.sl solib1.sl solib2.sl \
	unloadshr.sl unloadshr2.sl watchpoint-solib-shr.sl \
	weaklib1.sl weaklib2.sl hashline1.c hashline2.c hashline3.c \
	auxv.gcore bigcore.corefile *.core *.debug *.stripped \
	gcore-buffer-overflow.test gcore.test shreloc.txt tmp-fullname.c

all info install-info dvi install uninstall installcheck check:
	@echo "Nothing to be done for $@..."

clean mostlyclean:
	-rm -f *~ *.o a.out xgdb *.x *.ci *.tmp
	-rm -f *.dwo *.dwp
	-rm -f core core.coremaker coremaker.core corefile $(EXECUTABLES)
	-rm -f $(MISCELLANEOUS)

distclean maintainer-clean realclean: clean
	-rm -f *~ core
	-rm -f Makefile config.status config.log
	-rm -f *-init.exp gdb.log gdb.sum
	-rm -fr *.log summary detail *.plog *.sum *.psum site.*
