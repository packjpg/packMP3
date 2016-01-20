# Project: packMP3
# Makefile created by Matthias Stirner 01/30/2012
# Working with GCC 4.6.0

CC      = gcc
CPP     = g++
RC      = windres -O coff
RM      = del
CFLAGS  = -I. -DDEV_BUILD -O3 -Wall -pedantic -funroll-loops -ffast-math -fsched-spec-load -fomit-frame-pointer
LDFLAGS = -s -static-libgcc -static-libstdc++
DEPS    = aricoder.h bitops.h huffmp3.h huffmp3tbl.h pmp3tbl.h pmp3bitlen.h Makefile
OBJ     = aricoder.o bitops.o huffmp3.o packmp3.o
RES     = icons.res
BIN     = packMP3

%.o: %.cpp $(DEPS)
	$(CPP) -c -o $@ $< $(CFLAGS)
	
%.res: %.rc
	$(RC) $< $@

$(BIN): $(OBJ) $(RES)
	$(CPP) -o $@ $^ $(LDFLAGS)

clean:
	$(RM) *.o
