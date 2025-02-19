v0.6.0 (in development)
-----------------------
- Improved: Instruction semantics definition format.

v0.5.1 (in development)
-----------------------
- Fixed: Non-deterministic decompilation of functions containing removable return values.
- Technical: Updated minimum required version of dependencies.

v0.5.0 (2019-7-11)
------------------
- Fixed: Crashes when reading malformed SSL specification files.
- Fixed: Crashes when specifying malformed command line arguments for boomerang-cli.
- Fixed: Crashes when decoding unrecognized floating point branches on SPARC.
- Fixed: Crashes when loading ELF files with malformed relocation entries.
- Fixed: Crash when decoding instructions with multiple instruction prefixes in some cases.
- Fixed: Crash when decompiling x86 binaries that contain specific variants of the JP or JNP instructions.
- Fixed: Crash when decompiling x86 binaries that contain functions where the first instruction is BSF or BSR.
- Fixed: Crash when decompiling x86 binaries that contain functions where the first instruction is a string instruction.
- Fixed: Crash when decompiling x86 binaries that contain instructions accessing FS or GS segment registers.
- Fixed: Crash when decompiling SPARC binaries containing calls to helper functions.
- Fixed: Crash when decompiling tail-recursive functions.
- Fixed: Crash when decompiling functions containing dangling phi arguments in some cases.
- Fixed: Crash when decompiling branches that have the same destination for both branch edges.
- Fixed: Crash when decompiling binaries containing noreturn calls in some cases.
- Fixed: Crash when decompiling code that temporarily stores the address of an imported function before a call.
- Fixed: Crash when generating code for Basic Bocks containing a single jump.
- Fixed: Crash when removing an empty jump in a delay slot on SPARC.
- Fixed: Crash when analyzing data-flow for functions consisting of a single Basic Block.
- Fixed: Crash when analyzing data-flow for functions where the entry BB is not the BB with the lowest address.
- Fixed: Crash when analyzing data-flow for recursive functions after removing Basic Blocks from the same function.
- Fixed: Crash when accessing deleted call statement via callee function.
- Fixed: Potential crash when loading ELF files with a large number of sections.
- Fixed: Potential crash when decompiling non-constant register expressions.
- Fixed: Potential crash when analyzing delayed branches on SPARC where the branch and the delay slot cannot be swapped.
- Fixed: Potential crash when analyzing dataflow for functions where the entry Basic Block is not at index 0.
- Fixed: Potential crash when simplifying expressions that divide by zero.
- Fixed: Memory leak when analyzing switch statements.
- Fixed: Failure to load and disassemble 16-bit DOS MZ and LE executables.
- Fixed: Failure to load DOS4GW LX or LE executables.
- Fixed: Missing guard expressions when processing overlapped registers for assignments with guards.
- Fixed: Unsigned integral types mistaken for signed integral types when parsing signature or symbol information.
- Fixed: Signature promotion ignored '-nP' switch.
- Fixed: Wrong decompilation of "Pass by pointer/reference" values (e.g. `foo(&local0)` was emitted as `foo(esp-32)`).
- Fixed: Wrong decompilation of parameter types in function signatures in some cases.
- Fixed: Wrong decompilation of x86 binaries containing a `cmovCC`-type instruction.
- Fixed: Wrong decompilation of x86 binaries containing jumps that do not depend on flag registers.
- Fixed: Wrong decompilation of x86 binaries using the `sahf` instruction in floating point comparisons.
- Fixed: Wrong decompilation of x86 binaries containing multiple string instructions in a single Basic Block.
- Fixed: Wrong decompilation of ppc binaries using the LR or CTR register in calls or switch statements.
- Fixed: Wrong decompilation of SPARC branches where the branch and the delay slot cannot be swapped.
- Fixed: Wrong decompilation of loops containing break or return statements in some cases.
- Fixed: Unnecessary union types in high level code due to non-symmetric type meet operator.
- Fixed: Missing rotation amount for left and right rotates in high level code.
- Fixed: High level code output for bit extraction operator on right hand side of assignments.
- Fixed: Functions used as members in global function pointer arrays before they were declared.
- Fixed: Memory leaks in parsers.
- Fixed: Missing high-level code when decompiling via boomerang-gui.
- Feature: The x86 decoder now recognizes a larger subset of the x86 instruction set.
- Feature: Added support for Code Generator plugins.
- Feature: Added support for Type Recovery plugins.
- Feature: Added support for Symbol Provider plugins.
- Feature: Added support for Decoder plugins.
- Feature: Added support for FrontEnd plugins.
- Feature: Added support for compiling on macOS (10.13+).
- Feature: Added experimental support for loading ST20 .bin executable images.
- Improved: Performance of decoding x86 instructions.
- Improved: General processing of overlapped registers (not just hard-coded ones).
- Improved: Better high level code output quality for x86 binaries due to more instructions being recognized.
- Improved: Better high level code output quality for PPC binaries due to more accurate instruction semantics.
- Improved: Type Analysis of code containing ternary ?: operator.
- Improved: Analysis of calls via function pointers.
- Improved: Ordering of case labels in high level switch statements.
- Improved: High level code output for increments of pointers to non-32 bit data.
- Improved: Removal of unnecessary parameters for self-recursive functions.
- Improved: Unit test coverage.
- Improved: Regression test coverage.
- Changed: Replaced old pentium (x86) decoder by x86 decoder using libcapstone for decoding instructions.
- Changed: Replaced old PPC decoder by x86 decoder using libcapstone for decoding instructions.
- Changed: Replaced old SSL parser by new GNU flex+bison SSL2 parser.
- Changed: Replaced old C signature parser by new GNU flex+bison C signature parser.
- Removed: HP SOM binary file loader.
- Removed: Palm OS binary loader.
- Removed: Broken MIPS support.
- Removed: Broken M68k support.
- Removed: Broken HP PA/RISC support.
- Removed: Ability to build libboomerang as a static library.
- Technical: Improved compilation times and memory usage while compiling.

v0.4.0-alpha (2018-11-11)
-------------------------
- Fixed: Crashes when decompiling SPARC binaries.
- Fixed: Crashes when decompiling Win32 binaries.
- Fixed: Crashes when loading corrupted ELF binaries.
- Fixed: Crashes when loading corrupted DOS binaries.
- Fixed: Crashes when loading corrupted Mach-O binaries.
- Fixed: Crashes when loading corrupted PE binaries.
- Fixed: Crash when supplying an invalid entry address using the -e or -E command line switches.
- Fixed: Crash when generating code for switch statements.
- Fixed: Crash when loading MIPS binaries.
- Fixed: Crash when loading HPPA binaries.
- Fixed: Crash when loading binaries without sections.
- Fixed: Crash when decoding backwards relative jumps.
- Fixed: Crash when decoding tail-self-recursive functions.
- Fixed: Crash when decoding x86 binaries containing a RETF instruction.
- Fixed: Crash when decompiling library thunks.
- Fixed: Crash when the instruction at the entry point is a jump instruction.
- Fixed: Crash when accessing a Phi reference in a removed Basic Block.
- Fixed: Crash when decompiling recursive functions containing switch statements or computed calls.
- Fixed: Crash when decompiling x86 binaries that contain a JO/JNO instruction.
- Fixed: Crash when analyzing specific kinds of switch statements.
- Fixed: Crash when trying to find main for binaries compiled with recent GCCs.
- Fixed: Crash when attempting decompilation using a malformed SSL specification file.
- Fixed: Crash when trying to read values of function pointers from BSS.
- Fixed: Crash when emitting high level code for function calls with member function pointers as arguments.
- Fixed: Potential crash after removing unused global variables.
- Fixed: Potential crash due to wrong decode of anulled branches (e.g. BG,a) when decoding SPARC binaries.
- Fixed: Disabled direct editing of file selection combobox in boomerang-gui.
- Fixed: Missing -= and -- operators in addition to += and ++ operators in high level code.
- Fixed: Empty conditional blocks in high level code in some cases.
- Fixed: Generation of bitwise not operators instead of logical not operators for boolean expressions.
- Fixed: Generation of assignments after branch statements in some cases.
- Fixed: Goto statements instead of break statements in high level code in some cases.
- Fixed: Wrong high level code output for loops containing break statements.
- Fixed: Wrong high level code output for post-tested loops where the false branch goes to the beginning of the loop.
- Fixed: Wrong assignments to overlapped registers on x86.
- Fixed: A large number of memory leaks.
- Improved: The x86 decoder now recognizes the 2-byte INT (0xCD) instruction.
- Improved: Log output formatting.
- Improved: Detection of statically imported library functions.
- Improved: Unit test coverage.
- Improved: Regression test coverage.
- Improved: The regression test script now produces a unified diff when detecting a regression.
- Improved: General high level code output quality.
- Feature: Added 'replay' console command to read console commands from a file.
- Feature: Added 'print dfg' console command to write the DFG of a function to a file.
- Feature: Added 'print use-graph' console command to write the Use Graph of a function to a file.
- Feature: Added C++ API.
- Feature: Added option to build shared or static libraries.
- Feature: Added '--decode-only' switch to only decode a binary.
- Changed: GUI update. Added settings wrt. decoding and decompilation to Settings Dialog.
- Changed: Renamed 'print-*' console command to a single 'print' command with arguments.
- Changed: Split old regression test suite into "real" regression tests and smoke tests (that only check for crashes or failures).
- Changed: Replaced '-k' command line option for interactive mode by '-i'.
- Changed: Replaced old '-Tc' and '-Td' switches by single '-nT' switch to disable Type Analysis.
- Removed: Constraint-based type analysis.
- Removed: Ability to read/write XML files, to be replaced by new save format.
- Performance: Slightly increased performance of code generation.
- Performance: Slightly increased performance of instruction decoding.
- Technical: Dropped boost as a dependency.
- Technical: Reformatted code base to be consistent; correct code style is now enforced.
- Technical: Added option to auto-generate Doxygen documentation using CMake.
- Technical: Allow compilation using GCC, Clang and Visual Studio (MSVC) compilers.
- Technical: Removed unused files from the repository.
- Technical: Split project into libboomerang (core library), boomerang-cli (command line interface) and boomerang-gui (GUI frontend).
- Technical: Upgraded code base to C++17.
- Technical: Added support for installer and/or binary package generation using CPack.
- Numerous other small changes and fixes.
