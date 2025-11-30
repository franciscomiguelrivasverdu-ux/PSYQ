Files in this ZIP:-

PSYLINK  EXE	Psy-Q Linker
PSYLIB   EXE	Psy-Q librarian
CCPSX    EXE	compile/assemble/link utility
ASMPSX   EXE	Assembler for Assembler programmers
ASPSX    EXE	Assembler for C compiler output
RESETPS  EXE	utility to reset DTL-H2000 PSX PC board
DBUGPSX  EXE	PSX debugger (standard release)
DBUGPSXX EXE	PSX debugger (extended release, more C support)
DEXBIOS  COM	Psy-Q bios extensions for DTL-H2000 dev hardware
PSYBIOS  COM	Psy-Q bios extensions for MW3.0 dev hardware
PQALOAD  COM	Utility to load a COFF file to target RAM
PQBLOAD  COM	Utility to load a raw bin file to target RAM
PQGOPSX  COM	Utility to execute from address
NEWDEX   CPE	Utility to update Psy-Q downloader on DTL-H2000
LIBSN    LIB	C start-up module + Psy-Q fileserver library
LIBSN    H  	include file declarations for above
SNMAIN   S	Assembler source for C startup module in LIBSN.LIB
DEBUGDOC TXT	short debugger overview
README   TXT	This file

DBUGPSXX.EXE REVISION HISTORY : Extended debugger
-------------------------------------------------

This is a major debugger update. This version runs in 32 bit 386
protected mode using a DOS extender. Unlike version 3.XX debugger it
can *ONLY* run in protected mode. Since we have occasionally
experienced DOS Extender compatability problems with certain strange
PC configurations we have supplied both this new version 4.XX
debugger an the old version 3.XX also. If you are completely unable
to run version 4.XX then you can still use version 3.XX.

If you do have problems with version 4.XX then please notify SN
Systems (preferably by email) so that we can examine the problem.

Be warned that the config files from the two debugger versions are not
compatible - they may cause strange screen colours if mixed.


4.10 27/09/94	1st proper BETA release.
		Alt-G in watch window enters all global variables.
		You can now scroll the text window left and right.

4.11 30/09/94	Embarassing bug fixed. (4.10 did not run on many PC's)
		Now has scsi error checking

4.12 03/10/94	Oops. fixed bug that prevented windows from being
		split vertically.
		Watch 'Add all globals' key does not add functions.

4.13 04/10/94	Watches add to end OK.
		Histories now work more like Brief.
		Dialogs are now moveable using shift-cursor keys

4.14 05/10/94	Var & Watch display fixed. (I broke them in 4.13)
		Can now use page-up and page-down in watch window.

4.15 07/10/94	bailout if messages arrive too fast for debugger
		 (so it can still respond to keyboard).
		search in file window fixed.
		fixed file window wierdness if file > 1024 lines.
		fixed watch window unstable memory alloc.

4.16 07/10/94	message window repos if window changes height
		message window forced redraw on zoom
		message window forced re-load on (alt-#) screen switch
		Alt-N cont search in disassembly window fixed
		set-tabs for file window moved to ctrl-T (was Alt-T)

4.17 17/10/94	unions in watch window fixed (can now be opened)

4.18 26/10/94	added line No lookup to cmd line options

4.20 28/10/94	fix to register window 'wrap' code.

4.21 01/11/94	moved PSYBIOS check to after eval/line No/sym load
		so you can use symbol fns without having Psy-Q card

4.22 03/11/94	unit No now set before window lock so lock
		 expressions evaluate correctly for all cpus.
		opened watch entries can now have display format changed
		 (didn't work before cos they typed as assembler labels)

4.23 06/11/94	added version No check to config load
		 (so no more bad screen attributes on upgrades)

4.24 08/11/94	fixed bug which stopped JALR from tracing correctly
		 (at C source level this was preventing C variable
		 function calls from tracing)

4.25 08/11/94	sizeof() added to C expression evaluator


Known problems/bugs (these will be fixed eventually)
----------------------------------------------------

Cannot shell to DOS from debugger.
Attempt to evaluate a typedef record crashes (these cannot be
evaluated anyway)


----------------------------------------------------

USING THE EXTENDED DEBUGGER:-
+++++++++++++++++++++++++++++

Copy your old DBUGPSX.EXE away somewhere safe first cos you may need
to switch back to it if you have problems.

Please delete any old debugger config files (from debuggers prior to
version 4.0) before running the extended debugger (or you will get
horrible screen colours and worse).

You should copy this new EXE file to DBUGPSX.EXE in your path
(wherever you normally keep DBUGPSX.EXE).

----------------------------------------------------

V4.25 up allows you to use the sizeof() function in a C expression.
This function will return the size of the result of the expression
within the brackets.

This debugger features the all new VARIABLE window and WATCH window.
In either window you can use the following keys:-

+	open up the info (e.g. structure or array etc) under cursor

-	close ditto

tab	change result display format of C expression under cursor

right arrow	increments array index under cursor
left arrow	decrements array index under cursor

Note: currently these last two only work if the array entry has not
been expanded by pressing '+'.

Also in a watch window you can use INSERT and DEL to add and remove
watch expressions. Pressing Alt-G will enter watch records for all
your global variables. Unlike VAR window, these are saved on exit.

Note that watch expressions, window lock expressions, and calculator
expressions can now be C or assembler syntax - just click on the
button on the dialog box before you enter the expression to select
which type.

If you have any questions then please email me.

-- 
Andy Beveridge       andy@snsystems.co.uk
