# vim: set noexpandtab:

CC := clang-cl

CFLAGS  :=  -m32 /nologo /machine:x86
LDFLAGS :=  /nologo /machine:x86

PROGRAMS := metsvc.exe metsvc-server.exe
SCRIPTS := install.bat

SOURCES := $(patsubst %.exe,%.cpp,$(PROGRAMS))
OBJECTS := $(patsubst %.exe,%.obj,$(PROGRAMS))

GENERATED := vc??.pdb

build: $(PROGRAMS)

metsvc.exe: metsvc.cpp metsvc.h
	$(CC) $(CFLAGS) $< /link $(LDFLAGS) /OUT:$@ ws2_32.lib advapi32.lib
	
metsvc-server.exe: metsvc-server.cpp metsvc.h
	$(CC) $(CFLAGS) $< /link $(LDFLAGS) /OUT:$@ ws2_32.lib

clean:
	rm -f $(PROGRAMS) $(OBJECTS) $(GENERATED)

.PHONY: build install clean
