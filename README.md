# NTOS/2
OS2API is an OS/2 emulation layer for NT. It emulates over 110 DOSCALL functions. It consists of a library that is linked into your OS/2 program.

### How to compile and use OS2API.LIB
The order of the include diretories is important.
  First the standard include directory (WATCOM\H)
  Then the os/2 toolkit (WATCOM\H\OS2)
  Then win32 SDK (WATCOM\H\NT)
Example: I:\WATCOM\H;I:\WATCOM\H\OS2;I:\WATCOM\H\NT

For improved speed you may consider copying the OS/2 header files and modifying
the calling convention. Watcom's standard calling convention is faster than
_System.

Compile all *.cpp files (except test.cpp) and put them into a library.

When you compile you OS/2 application remember to call initFileTable(),
initProcess() and initMemory(). An example is in test.cpp. The OS/2 source
files will probably not discover that they are in fact running under NT.
